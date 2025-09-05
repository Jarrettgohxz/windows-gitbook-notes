# Get-Alias

{% embed url="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/get-alias?view=powershell-7.5" %}

> Gets the aliases for the current session

### Examples

```powershell
PS> Get-Alias gwmi
PS> Get-Alias -Definition Get-Wmiobject

# both commands listed above outputs the same results

CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           gwmi -> Get-WmiObject

```

* `-Definition` : Gets the aliases for the specified item. Enter the name of a cmdlet, function, script, file, or executable file.

