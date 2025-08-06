# whoami

**View all available options**

```powershell
whoami /?
```

### Examples

1. View groups for the current user

```powershell
whoami /groups
...
BUILTIN\Administrators                                        Alias            S-1-5-32-544   
...
```

The following output shows that the current user is an Administrator. However, the token settings will be kept to the standard user by default. Refer to the User Account Control (UAC) [notes ](https://jarrettgxz-sec.gitbook.io/windows/user-account-control-uac)for more information.
