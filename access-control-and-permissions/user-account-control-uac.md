# User Account Control (UAC)

{% embed url="https://learn.microsoft.com/en-us/windows/security/application-security/application-control/user-account-control/how-it-works" %}

> User Account Control (UAC) is a key part of Windows security. UAC reduces the risk of malware by limiting the ability of malicious code to execute with administrator privileges.

### User types

There are 2 types of user accounts, namely the _standard user_, and _administrator_.&#x20;

### Access token

When a user logs on, there will be an access token created. The process varies slightly between the 2 user types described above.

a) Standard user logon: Only the standard user access token will be created for the user.

b) Administrator logon: Two access tokens: standard user, and full administrator access tokens will be created for the user.

By default, all of the applications will be ran with the standard user access token (even for administrators). This is to reduce the risk of damage in the event of a malware infection. However, certain applications may require higher administrator privileges, and can be ran with the full administrator access token via a prompt.&#x20;

For more information on the specific prompts, refer to the official Microsoft documentation from the link above.&#x20;



