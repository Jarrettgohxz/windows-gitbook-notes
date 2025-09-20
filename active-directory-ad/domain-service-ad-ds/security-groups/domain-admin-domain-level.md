# Domain Admin (domain level)

{% embed url="https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/understand-security-groups#domain-admins" %}

> Members of the Domain Admins security group are authorized to administer the domain. By default, the Domain Admins group is a member of the Administrators group on all computers that join a domain, including the domain controllers.&#x20;

From the short description taken directly from the official documentation, we can understand the following key points:

1. Any member under the `Domain Admins`  group is a domain admin
2. Domain admins are automatically a member of the `Administrators` group on all computers that joins that particular domain

* this include the domain controller
