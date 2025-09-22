# Overview

### Resources

1. Further readings

{% embed url="https://learn.microsoft.com/en-us/windows/win32/sysinfo/structure-of-the-registry" %}

{% embed url="https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2003/cc781906(v=ws.10)" %}

2. Windows registry hive

{% embed url="https://learn.microsoft.com/en-us/windows/win32/sysinfo/registry-hives" %}

3. Advanced information

{% embed url="https://learn.microsoft.com/en-us/troubleshoot/windows-server/performance/windows-registry-advanced-users" %}

### Basic overview of Windows registry

A central hierarchical database used to store information that is necessary to configure the system for one or more users, applications and hardware devices. It contains information that Windows continually references during operations, such as profiles for each user, applications installed on the machine, etc.

#### What is a registry hive?

> A _hive_ is a logical group of keys, subkeys, and values in the registry that has a set of supporting files loaded into memory when the operating system is started or a user logs in.

A new _hive_ is created each time a user logs on to a computer, with a separate file for the user profile known as the _user profile hive_. This user's hive contains specific registry information pertaining to the user's application settings, desktop, environment, network connections and printers. User profile hives are located under the **HKEY\_USERS** key.

The supporting files (that contains backup of its data) for all hives are stored in the `%SystemRoot%\System32\Config` folder, while it is stored in `%SystemRoot%\Profiles\Username` for **HKEY\_CURRENT\_USER**.

The following table displays the mapping of the supporting file locations to each registry hive:

> Note that some of the values displayed under the _supporting files_ may be outdated on modern Windows versions.

| Registry hive                     | Supporting files                                                       |
| --------------------------------- | ---------------------------------------------------------------------- |
| **HKEY\_LOCAL\_MACHINE\SAM**      | Sam, Sam.log, Sam.sav                                                  |
| **HKEY\_LOCAL\_MACHINE\Security** | Security, Security.log, Security.sav                                   |
| **HKEY\_LOCAL\_MACHINE\Software** | Software, Software.log, Software.sav                                   |
| **HKEY\_LOCAL\_MACHINE\System**   | System, System.alt, System.log, System.sav                             |
| **HKEY\_CURRENT\_CONFIG**         | System, System.alt, System.log, System.sav, Ntuser.dat, Ntuser.dat.log |
| **HKEY\_USERS\DEFAULT**           | Default, Default.log, Default.sav                                      |
| **HKEY\_CURRENT\_USER**           | Ntuser.dat, Ntuser.dat.log                                             |

#### Retrieving information for a particular hive

We can use a few methods to retrieve information for a particular hive:

1. Registry editor
2. `reg.exe`

{% code overflow="wrap" %}
```powershell
reg query <hive> /s ...
```
{% endcode %}

3. Supporting files location

> This method will not work, and will simply return an error message: "The process cannot access the file because it is being used by another process." This is because the files are not allowed to be read and accessed by any users while the Windows operating system is running.

{% code overflow="wrap" %}
```powershell
dir /s /b %SystemRoot%\System32\Config\<hive_supporting_filename>
dir /s /b %SystemRoot%\Profiles\Username\<hive_supporting_filename>
```
{% endcode %}

#### Example

Given that we want to retrieve information about the **HKEY\_LOCAL\_MACHINE\SAM** hive:

**Using `reg.exe`**

```powershell
reg query HKEY_LOCAL_MACHINE\SAM /s

# save to separate file
reg save HKEY_LOCAL_MACHINE\SAM <local_file_path_to_save>
```

