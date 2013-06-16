---
title: STATS in Inpspircd
layout: default
---

# List of `STATS` in Inspircd

## Core

Letter | Description
------ | -----------
e | Show e-lines (local ban exemptions)
E | Show socket engine events
g | Show g-lines (host bans)
i | Show connect class permissions
k | Show k-lines (local host bans)
l | Show all client connections with information (sendq, commands, bytes, time connected)
L | Show all client connections with information and IP address
m | Show command statistics, number of times commands have been used
o | Show a list of all valid oper usernames and hostmasks
O | Show opertypes and the allowed user and channel modes it can set
p | Show open client ports, and the port type (ssl, plaintext, etc)
P | Show online opers and their idle times
q | Show q-lines (nick mask bans)
T | Show bandwidth/socket statistics
u | Show server uptime
Y | Show connection classes
z | Show memory usage statistics
Z | Show z-lines (IP mask bans)

## Modules

Letter | Module | Description
------ | ------ | -----------
c | [m_spanningtree](../../Modules/2.0/spanningtree.md) | Show link blocks
C | [m_cban](../../Modules/2.0/cban.md) | Show channel bans
d | [m_dnsbl](../.../Modules/2.0/dnsbl.md) | Show configured DNSBLs and related statistics
G | [m_geoip](../../Modules/2.0/geoip.md) | Show how many local users are connected from each country according to GeoIP
H | [m_shun](../../Modules/2.0/shun.md) | Show shuns
R | [m_rline](../../Modules/2.0/rline.md) | Show R-lines (regular expression bans)
s | [m_filter](../../Modules/2.0/filter.md) | Show filters
S | [m_services_account](../../Modules/2.0/services_account.md) | Show currently held registered nicknames
U | [m_spanningtree](../../Modules/2.0/spanningtree.md) | Show U-lined servers
