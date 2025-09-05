# Get-ChildItem

{% embed url="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-childitem?view=powershell-7.5" %}

**Basic command**:

```powershell
Get-ChildItem -Path "path_to_search"
```

Filter files with name:

```powershell
PS> Get-ChildItem -Path "path_to_search" -Recurse -Filter "*string*" | Select-Object FullName

# Eg. search in the C:\ directory, for the filename that contains TEST
PS> Get-ChildItem -Path C:\ -Recurse -Filter "*TEST*" | Select-Object FullName
```

Reveal hidden files using the `-force` flag (eg. system files):

```powershell
Get-ChildItem -Path "path_to_search" -Recurse -Force -ErrorAction SilentlyContinue

# Eg.
Get-ChildItem -Path "C:\Users\user\AppData\Local\Microsoft\Windows\INetCache\IE" -Recurse -Force -ErrorAction SilentlyContinue
```
