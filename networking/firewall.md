# Firewall

{% embed url="https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/netsh-advfirewall?tabs=consecadd%2Cfirewalladd%2Cmainmodeadd%2Cmonitordelete" %}

{% embed url="https://learn.microsoft.com/en-us/windows/security/operating-system-security/network-security/windows-firewall/configure-with-command-line?tabs=cmd" %}

### Basic examples

#### General

```powershell
C:\> netsh advfirewall firewall ?

Commands in this context:
?              - Displays a list of commands.
add            - Adds a new inbound or outbound firewall rule.
delete         - Deletes all matching firewall rules.
dump           - Displays a configuration script.
help           - Displays a list of commands.
set            - Sets new values for properties of a existing rule.
show           - Displays a specified firewall rule.

To view help for a command, type the command, followed by a space, and then
 type ?.

```

#### 1. View firewall rules

**View help menu**:

```powershell
netsh advfirewall firewall show rule ?

Usage: show rule name=<string>
      [profile=public|private|domain|any[,...]]
      [type=static|dynamic]
      [verbose]
```

```powershell
netsh advfirewall firewall show rule name=all dir=in
netsh advfirewall firewall show rule name=all dir=out
```

#### 2. Add firewall rules

**View help menu**:

```powershell
C:\> netsh advfirewall firewall add rule ?

Usage: add rule name=<string>
      dir=in|out
      action=allow|block|bypass
      [program=<program path>]
      [service=<service short name>|any]
      [description=<string>]
      [enable=yes|no (default=yes)]
      [profile=public|private|domain|any[,...]]
      [localip=any|<IPv4 address>|<IPv6 address>|<subnet>|<range>|<list>]
      [remoteip=any|localsubnet|dns|dhcp|wins|defaultgateway|
         <IPv4 address>|<IPv6 address>|<subnet>|<range>|<list>]
      [localport=0-65535|<port range>[,...]|RPC|RPC-EPMap|IPHTTPS|any (default=any)]
      [remoteport=0-65535|<port range>[,...]|any (default=any)]
      [protocol=0-255|icmpv4|icmpv6|icmpv4:type,code|icmpv6:type,code|
         tcp|udp|any (default=any)]
      [interfacetype=wireless|lan|ras|any]
      [rmtcomputergrp=<SDDL string>]
      [rmtusrgrp=<SDDL string>]
      [edge=yes|deferapp|deferuser|no (default=no)]
      [security=authenticate|authenc|authdynenc|authnoencap|notrequired 
         (default=notrequired)]
```

Eg. Add firewall rule to allow inbound TCP traffic to local port 80:

{% code overflow="wrap" %}
```powershell
netsh advfirewall firewall add rule name="<name>" dir=in action=allow protocol=TCP localport=80
```
{% endcode %}



