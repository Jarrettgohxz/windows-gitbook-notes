# LDAP

Even though LDAP is not a Windows-specific protocol, it can be used with Active Directory for authentication.&#x20;

The following outlines the overall steps in the LDAP authentication process for a given LDAP client that wishes to authenticate with a server, with help from an image illustration taken directly from the [TryHackMe's Breaching AD](https://tryhackme.com/room/breachingad) room:

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

The notes below attempts to bridge the understanding of how LDAP authentication is used in an Active Directory (AD) environment. In a LDAP authentication process, two devices are involved:

1. LDAP client
   * _**"Network Connected Printer"**_ in the image illustration above
2. LDAP directory server are involved
   * _**"Domain Controller"**_ in the image illustration above

**Important terms**

There exists a few terminologies used in LDAP that I would like to clarify before moving on:

1. Distinguised Name (DN)
   * A unique identifier for each entry in the LDAP directory
   * eg. `cn=Jarrett Gxz,ou=Tech,dc=random,dc=com` refer to the [following](https://learn.microsoft.com/en-us/previous-versions/windows/desktop/ldap/distinguished-names) to understand what each element means
2. LDAP bind request
   * This request is used to authenticate a client with a server before performing further operations
3. LDAP search operation
   * This request can be used to locate and retrieve information that are stored within the directory
   * In this example, it is used to find the DN of the user

**LDAP authentication process**

> Note that the "User" device shown in the illustration is not directly involved in the LDAP authentication process, but simply supplies its credentials to the printer acting as the LDAP client and intermediary machine to handle the process

1. The process starts with obtaining the Distinguished Name (DN), via a **DN resolution function**. This maps to steps 2, 3, 4 and 5 in the illustration, where the printer (acting as the client) uses its own credentials to create a **LDAP bind request** to authenticate with the server, before performing a **LDAP search operation** to find the user and retrieve the DN
2. Next, the printer (client) will initiate another bind request with the obtained user's DN and password. This maps to steps 6 and 7 in the image, where the credentials are passed to the "Domain Controller" (LDAP directory server), before retrieving a response to indicate if the credentials are valid or not



{% embed url="https://tryhackme.com/room/breachingad" %}

{% embed url="https://calcomsoftware.com/ldap-authentication-and-security-signing-binding-and-configuration/" %}
