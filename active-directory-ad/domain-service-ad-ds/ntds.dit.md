# ntds.dit

{% embed url="https://www.semperis.com/blog/ntds-dit-extraction-explained/" %}

{% embed url="https://medium.com/@harikrishnanp006/understanding-ntds-dit-the-core-of-active-directory-faac54cc628a" %}

The New Technology Directory Services Information Tree (**NTDS.DIT)**, is the database for Active Directory Domain Services (AD DS), which stores directory data of all objects in the domain, including user, groups, computers, etc.

### Where is the ntds.dit file found?

The `ntds.dit` file can be found in `%systemroot\NTDS\ntds.dit`.  The value of `%systemroot%` can be found with the command (refer to [docs](https://jarrettgxz-sec.gitbook.io/windows/general/environment-variables)):

```powershell
C:\> echo $Env:systemroot
```

The directory is commonly: `C:\Windows\NTDS\ntds.dit``.`  &#x20;

#### Important note

By default, the `ntds.dit` file is **stored only on the domain controller.** We can utilize tools such as `ntdsutil.exe` to dump the ntds files (with administrator access to the DC).

{% embed url="https://jarrettgxz-sec.gitbook.io/penetration-testing-ethical-hacking-concepts/windows-active-directory/credentials-harvesting/new-technologies-directory-services-ntds" %}

### Common exploitation techniques

{% embed url="https://jarrettgxz-sec.gitbook.io/penetration-testing-ethical-hacking-concepts/windows-active-directory/credentials-harvesting/new-technologies-directory-services-ntds" %}





