# Get-ADObject, GetADGroup, Get-ADObject, GetADDomain, Get-ADOrganizationalUnit

{% embed url="https://jarrettgxz-sec.gitbook.io/penetration-testing-ethical-hacking-concepts/windows-active-directory/enumeration/powershell" %}

### Get-ADObject

```powershell
PS> Get-ADObject -Filter "CN -eq '<CN_NAME_TO_SEARCH>'" -Properties *
```
