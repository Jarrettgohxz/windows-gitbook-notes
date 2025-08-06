# Domain Service (AD DS)

> The core of any Windows Domain is the Active Directory Domain Service (AD DS). This service acts as a catalogue that holds the information of all of the "objects" that exist on your network. Amongst the many objects supported by AD, we have users, groups, machines, printers, shares and many others

{% embed url="https://tryhackme.com/room/winadbasics" %}

### Basic knowledge

_**What is a security principle?**_

> An entity that can be authenticated by the operating system, such as a user account, a computer account or the security groups for these accounts.

Refer to the link below for more information:

{% embed url="https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/understand-security-principals" %}

### Objects&#x20;

{% stepper %}
{% step %}
### Users

* One of the most common object types in Active Directory.
* Part of a _security principal_&#x20;
* May be used to represent two types of entities

a) _People_

> Persons in the organization that requires access to network, such as employees, etc.

b) _Services_

> Users to run services such as ISS, MSSQL, etc. These users will only possess the relevant privileges needed to run their specific service


{% endstep %}

{% step %}
### Machine

* A machine object will be created for each computer that joins the Active Directory domain
* Also considered as _security principals_
* Follows a specific naming scheme, where the machine account name is the computer's name followed by a dollar sign

Eg. The machine named DC01 will have an account called `DC01$`


{% endstep %}
{% endstepper %}

