# Trees, Forest, Trusts

{% embed url="https://tryhackme.com/room/winadbasics" %}

The image illustrations below are adapted from the TryHackMe's Windows AD Basics room.

### Tree

A tree is used to split multiple subdomains within a root domain namespace

* The root domain is known as the parent domain, while the subdomains are the child domains (can be managed independently separate from other child domains)
* By default, the parent child relationship creates an _implicit bidirectional (two-way) trust relationship_.

**Example**

Given the parent/root domain `thm.local` , we can split the management of two different child domain: `uk.thm.local` and `us.thm.local`&#x20;

* Each of the child domains will be able to separately manager their own components such as computers, users, GPOs, OUs, etc

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### Forest

A forest is used to split multiple root domain namespaces, each with their own tree structure.&#x20;

**Example**

Given that a new root domain `mht.local` with different management needs (separate users, groups, GPOs, OUs, etc.) joins the company. The union of several trees with different namespaces can be formed to create a forest.&#x20;

* Within the `mht.local` root domain, there exists the `eu.mht.local` and `asia.mht.local` child domains

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>



### Trust relationships

...

