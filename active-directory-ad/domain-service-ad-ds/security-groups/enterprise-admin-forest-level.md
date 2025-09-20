# Enterprise Admin (forest level)

{% embed url="https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/understand-security-groups#enterprise-admins" %}

> The Enterprise Admins group exists only in the root domain of an Active Directory forest of domains.

> By default, the only member of the group is the Administrator account for the forest root domain. This group is automatically added to the Administrators group in every domain in the forest, and it provides complete access to configuring all domain controllers. Members in this group can modify the membership of all administrative groups. Members of the default service administrator groups in the root domain can modify Enterprise Admins membership. This group is considered a service administrator account.

From the short description taken directly from the official documentation, we can understand the following key points:

1. A user under the `Enterprise Admins` group is an enterprise admin
2. An enterprise admin is an administrator for the forest root domain
3. An enterprise admin has complete access to configuring all domain controllers under the forest
