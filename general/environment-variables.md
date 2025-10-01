# Environment variables

### Resources

{% embed url="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_environment_provider?view=powershell-7.5" %}

{% embed url="https://learn.microsoft.com/en-us/windows/deployment/usmt/usmt-recognized-environment-variables" %}

### 1. Working in the environment variables drive location

The environment variables drive is found at: `Env:`&#x20;

```powershell
PS C:\> Set-Location Env:
PS Env:\> ls
Name                           Value
----                           -----
__PSLockDownPolicy             0
ALLUSERSPROFILE                C:\ProgramData
APPDATA                        C:\Users\<user>\AppData\Roaming
...
```

### 2. View value of environment variable

> The **Environment** provider also exposes environment variables using a variable prefix of `$Env:`

```powershell
PS C:\> echo $Env:<env> 

# eg.
PS C:\> echo $Env:ProgramData
C:\ProgramData
```

### 3. List all environment variables

```powershell
PS C:\> Get-Item -Path Env:
PS  C:\> Get-ChildItem -Path Env:
```

Alternatively, we can view it from the `Env:` folder too (refer to section above).

