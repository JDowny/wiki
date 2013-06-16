---
title: Modes
layout: default
---

# Channel Modes

### Core Channel Modes

Mode | Parameters | Function
---- | ---------- | --------	
b    | `<nick!user@host>`   | Listmode that prevents users matching the mask from joining. Accepts wildcards.
i    | *none*     | Prevents users who have not been `INVITE`'d from joining
k    | `<key>`    | Prevents users who does not know the `<key>` (password) from joining
l    | `<limit>`  | Prevents more than `<limit>` users from joining
m    | *none*     | Prevents users who do not have voice or higher from talking in it
n    | *none*     | Prevents users who have not joined the channel from talking in it
o    | `<nick>`   | Grants channel operator status to `<nick>`
p    | *none*     | Hides the channel from `/WHOIS`
s    | *none*     | Hides the channel from `/LIST` and `/WHOIS`
t    | *none*     | Restricts non-operators from changing the channel topic
v    | `<nick>`   | Grants voice status to `<nick>`

### Module Channel Modes

Mode | Parameters | Module | Function
---- | ---------- | ------ | --------
a    | `<nick>`   | [m_chanprotect](../../Modules/2.0/chanprotect.md) | Marks a user as a protected op
A    | *none*     | [m_allowinvite](../../Modules/2.0/allowinvite.md) | Allows any channel user to use `INVITE`
B    | *none*     | [m_blockcaps](../../Modules/2.0/blockcaps.md) | Blocks all CAPITAL letter messages
c    | *none*     | [m_blockcolor](../../Modules/2.0/blockcolor.md) | Blocks messages containing color codes
D    | *none*     | [m_delayjoin](../../Modules/2.0/delayjoin.md) | User will not appear in channel until they speak
e    | `<nick!user@host>` | [m_banexception](../../Modules/2.0/banexception.md) | Listmode that allows banned users matching the mask to join the channel. Accepts wildcards.
g    | `<globpattern>` | [m_chanfilter](../../Modules/2.0/chanfilter.md) | Listmode allowing chanops to filter channel messages
G    | *none*     | [m_censor](../../Modules/2.0/censor.md) | Fitlers config-defined bad words from messages
H    | `<lines>:<seconds>` | [m_chanhistory](../../Modules/2.0/chanhistory.md) | Shows recent activity to new joins
q    | `<nick>`   | [m_chanprotect](../../Modules/2.0/chanprotect.md) | Marks a user as a channel founder
u    | *none*     | [m_auditorium](../../Modules/2.0/auditorium.md) | Makes the channel's userlist invisible
w    | `<prefix>:<nick!user@host>` | [m_autoop](../../Modules/2.0/autoop.md) | Listmode allowing for basic channel ACL


# User Modes

### Core User Modes

Mode | Parameters  | Function
---- | ----------- | --------	
i    | *none*      | Prevents the user from appearing in `/WHO`
o    | *none*      | Marks the user as an IRC operator
s    | `<+/-><SNOMASK>` | Allows the user to receive server notices
w    | *none*      | Allows the user to receive WALLOPS

### Module User Modes

Mode | Module | Function
---- | ------ | --------
a    | [m_hideidle](../../Modules/2.0/hideidle.md)<sup>1</sup> | Hides a user's `IDLE` time from `WHOIS`
B    | [m_botmode](../../Modules/2.0/botmode.md)  | Marks a user as a bot
c    | [m_commonchans](../../Modules/2.0/commonchans.md) | Requires a client to share channels with the user to private message them
d    | [m_deaf](../../Modules/2.0/deaf.md) | User will not receive channel messages
D    | [m_privdeaf](../../Modules/2.0/extras/privdeaf.md)<sup>1</sup> | User will not recieve messages outside of channels
g    | [m_calleride](../../Modules/2.0/callerid.md) | Allows a user to screen private messages
G    | [m_censor](../../Modules/2.0/censor.md)    | Filters config-defined bad words from user's private messages
h    | [m_helpop](../../Modules/2.0/helpop.md) | Marks a user as available to help
H    | [m_hideoper](../../Modules/2.0/hideoper.md) | Hide's a user's operator status from non-operators
I    | [m_hidechans](../../Modules/2.0/hidechans.md) | Hides the channel a user is in from `WHOIS`
k    | [m_servprotect](../../Modules/2.0/servprotect.md) | Essentially, god mode
Q    | [m_invisible](../../Modules/2.0/extras/invisible.md)<sup>1</sup> | Allows the user to join a channel without appearing to users in it
R    | [m_services_account](../../Modules/2.0/services_account.md) | Client must be authenticated to services to message the user
S    | [m_stripcolor](../../Modules/2.0/stripcolor.md) | Strips color from incoming private messages
T    | [m_noctcp_user](../../Modules/2.0/extras/noctcp_user.md)<sup>1</sup> | Blocks `CTCP`s sent to the user
W    | [m_showwhois](../../Modules/2.0/showwhois.md) | Shows the user when and who `WHOIS`'s them
x    | [m_cloaking](../../Modules/2.0/cloaking.md) | Hides a user's real host

1) This is an 'extra' module **and is not compiled by default**.
