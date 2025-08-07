# Distinguished Name (DN)

{% embed url="https://learn.microsoft.com/en-us/previous-versions/windows/desktop/ldap/distinguished-names" %}

| String     | Attribute type         |
| ---------- | ---------------------- |
| **DC**     | domainComponent        |
| **CN**     | commonName             |
| **OU**     | organizationalUnitName |
| **O**      | organizationName       |
| **STREET** | streetAddress          |
| **L**      | localityName           |
| **ST**     | stateOrProvinceName    |
| **C**      | countryName            |
| **UID**    | userid                 |

### Examples

#### (1)

```
OU=Admins,OU=Accounts,DC=test,DC=com
```

a. organizationUnitName (OU)

* `OU=Admins` : defines a Organizational Unit (OU) called `Admins`
* `OU=Accounts` :  defines the parent of the `Admins` OU. This means that `Admins`  is a child nested inside `Accounts`

b. domainComponent (DC)

* `DC=test` and `DC=com` which forms the domain name: `test.com`

#### (2)

```
CN=Users,DC=test,DC=com
```

a. commonName (CN)

* `CN=Users` : Common Name (CN)

b. domainComponent (DC)

* `DC=test` and `DC=com` which forms the domain name: `test.com`&#x20;

