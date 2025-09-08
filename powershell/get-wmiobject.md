# Get-WmiObject

{% embed url="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-wmiobject?view=powershell-5.1" %}

> Gets instances of Windows Management Instrumentation (WMI) classes or information about the available classes.

### Examples

#### 1. Win32\_Printer

```powershell
PS> Get-WmiObject Win32_Printer -ComputerName <name>

# alias
PS> GWMI Win32_Printer -ComputerName <name>
```
