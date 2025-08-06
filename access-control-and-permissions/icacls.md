---
description: To display or modify discretionary access control lists (DACLs)
---

# icacls

### Display the DACLs of specified input

```powershell
C:\> icacls [dir]
C:\> icacls [executable_file].exe

# eg. for directory
C:\> icacls C:\filedir
c:\filedir NT AUTHORITY\SYSTEM:(I)(OI)(CI)(F)
              BUILTIN\Administrators:(I)(OI)(CI)(F)
              ...

# eg. for executable file
C:\> icacls c:\filedir\exec_file.exe
c:\filedir\exec_file.exe 
             NT AUTHORITY\SYSTEM:(I)(F)
             BUILTIN\Administrators:(I)(F)
             ...

```

Refer to the `icacls` documentation link below for information about each of the permission values:

{% embed url="https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/icacls" %}

### Modify the DACLs

**Eg**. Grant read-only access `(R)` to the `Everyone` group on the `bin.exe`file.

```powershell
C:\> icacls bin.exe /grant Everyone:R
```

