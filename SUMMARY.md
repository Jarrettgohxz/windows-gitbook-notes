# Table of contents

* [Introduction](README.md)

## General

* [Users](general/users.md)
* [SAM database](general/sam-database.md)
* [Local Security Authority (LSA)](general/local-security-authority-lsa.md)

## SYSTEM PROCESSES

* [tasklist](system-processes/tasklist.md)
* [References](system-processes/references.md)
* [explorer.exe](system-processes/explorer.exe.md)
* [svchost.exe](system-processes/svchost.exe.md)
* [csrss.exe](system-processes/csrss.exe.md)
* [wininit.exe](system-processes/wininit.exe.md)
* [services.exe](system-processes/services.exe.md)
* [lsass.exe](system-processes/lsass.exe.md)
* [winlogon.exe](system-processes/winlogon.exe.md)
* [fontdrvhost.exe](system-processes/fontdrvhost.exe.md)
* [LogonUI.exe](system-processes/logonui.exe.md)
* [dwm.exe](system-processes/dwm.exe.md)
* [spoolsv.exe](system-processes/spoolsv.exe.md)
* [msdtc.exe](system-processes/msdtc.exe.md)

## Filesystem

* [NTFS](filesystem/ntfs.md)
* [Finding files](filesystem/finding-files.md)

## Services

* [sc](services/sc.md)

## Registry

* [Overview](registry/overview.md)
* [reg.exe](registry/reg.md)
* [Registry Editor (GUI)](registry/registry-editor-gui.md)

## Access control & Permissions

* [icacls](access-control-and-permissions/icacls.md)
* [User Account Control (UAC)](access-control-and-permissions/user-account-control-uac.md)

## Networking

* [Firewall](networking/firewall.md)

## Powershell

* [Get-ChildItem](powershell/get-childitem.md)
* [Get-Alias](powershell/get-alias.md)
* [Get-WmiObject](powershell/get-wmiobject.md)
* [Select-Object (select)](powershell/select-object-select.md)
* [Select-String (sls)](powershell/select-string-sls.md)
* [whoami](powershell/whoami.md)

## 🔍 Active Directory (AD)

* [Trees, Forest, Trusts](active-directory-ad/trees-forest-trusts.md)
* [Tiering](active-directory-ad/tiering.md)
* [Domain Controller (DC)](active-directory-ad/domain-controller-dc.md)
* [Distinguished Name (DN)](active-directory-ad/distinguished-name-dn/README.md)
  * [CN vs OU](active-directory-ad/distinguished-name-dn/cn-vs-ou.md)
* [Domain Service (AD DS)](active-directory-ad/domain-service-ad-ds/README.md)
  * [Security groups](active-directory-ad/domain-service-ad-ds/security-groups/README.md)
    * [Domain Admin (domain level)](active-directory-ad/domain-service-ad-ds/security-groups/domain-admin-domain-level.md)
    * [Enterprise Admin (forest level)](active-directory-ad/domain-service-ad-ds/security-groups/enterprise-admin-forest-level.md)
  * [Organizational Units (OUs)](active-directory-ad/domain-service-ad-ds/organizational-units-ous.md)
  * [Security groups vs OUs](active-directory-ad/domain-service-ad-ds/security-groups-vs-ous.md)
* [Authentication methods](active-directory-ad/authentication-methods/README.md)
  * [Kerberos](active-directory-ad/authentication-methods/kerberos.md)
  * [NetNTLM](active-directory-ad/authentication-methods/netntlm.md)
  * [LDAP](active-directory-ad/authentication-methods/ldap.md)
* [General](active-directory-ad/general/README.md)
  * [NTLM hash vs NetNTLM challenge-response hash](active-directory-ad/general/ntlm-hash-vs-netntlm-challenge-response-hash.md)
* [Active Directory Module](active-directory-ad/active-directory-module/README.md)
  * [Get-ADObject, GetADGroup, Get-ADObject, GetADDomain, Get-ADOrganizationalUnit](active-directory-ad/active-directory-module/get-adobject-getadgroup-get-adobject-getaddomain-get-adorganizationalunit.md)
  * [Get-ADGroupMember](active-directory-ad/active-directory-module/get-adgroupmember.md)
  * [Add-ADGroupMember](active-directory-ad/active-directory-module/add-adgroupmember.md)
  * [Set-ADAccountPassword](active-directory-ad/active-directory-module/set-adaccountpassword.md)
  * [Get-ADForest](active-directory-ad/active-directory-module/get-adforest.md)
