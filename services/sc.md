# sc

### View the service configuration

```powershell
C:\> sc qc [service_name]

# eg.
C:\> sc qc testservicename
[SC] QueryServiceConfig SUCCESS

SERVICE_NAME: testservicename
        TYPE               : 10  WIN32_OWN_PROCESS
        START_TYPE         : 2   AUTO_START
        ERROR_CONTROL      : 0   IGNORE
        BINARY_PATH_NAME   : [path_to_exec_payload].exe
        LOAD_ORDER_GROUP   :
        TAG                : 0
        DISPLAY_NAME       : Test Service Name
        DEPENDENCIES       :
        SERVICE_START_NAME : [user_account]
```

### Configure the service

Assuming that we have enough permissions to configure a particular service, the following command can be used to update the configurations for the service binary path and account name:&#x20;

> Take note of the space after the equals (`=`) sign for each option

```powershell
C:\> sc config [service_name] binPath= [path_to_NEW_exec_payload].exe obj= [NEW_user_account]
```

{% embed url="https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/sc-config" %}
sc config documentation
{% endembed %}
