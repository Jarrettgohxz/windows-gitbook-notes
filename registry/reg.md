# reg.exe

### query

```powershell
C:\> reg query [registry_path]
```

### save

The `reg save` command can be used to save the content of the registry key (`HKLM\SYSTEM`) to a file named `system.hive` in the `C:\users\jarrett` directory.

**Example**

`HKLM\system` refers to the SYSTEM registry hive, which contains system-wide configuration settings (under `HKEY_LOCAL_MACHINE\SYSTEM`).

```powershell
C:\> reg save hklm\system C:\Users\jarrett\system.hive
```

The  command below is similar to the one above, but instead with the `SAM` (Security Accounts Manager) registry hive, and to the destination file of `sam.hive` instead.

```powershell
C:\> reg save hklm\sam C:\Users\jarrett\sam.hive
```

For the above two commands to work (working with `hklm\system` and `hklm\sam`), the current user must have certain privileges. Specifically, the `SeBackupPrivilege` and `SeRestorePrivilege.`

```powershell
C:\> whoami /priv
PRIVILEGES INFORMATION
----------------------

Privilege Name                Description                    State
============================= ============================== ========
SeBackupPrivilege             Back up files and directories  ...
SeRestorePrivilege            Restore files and directories  ...
...
```





