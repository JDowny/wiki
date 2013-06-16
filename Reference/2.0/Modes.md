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
C    | *none*     | [m_noctcp](../../Modules/2.0/noctcp.md) | Blocks `CTCP` to the channel
d    | `<seconds>` | [m_delaymsg](../../Modules/2.0/delaymsg.md) | User cannot speak in channel until `<seconds>` have elapsed
D    | *none*     | [m_delayjoin](../../Modules/2.0/delayjoin.md) | User will not appear in channel until they speak
e    | `<nick!user@host>` | [m_banexception](../../Modules/2.0/banexception.md) | Listmode that allows banned users matching the mask to join the channel. Accepts wildcards.
f    | `[*]<lines>:<second>` | [m_messageflood](../../Modules/2.0/messageflood.md) | Limits the rate users can message the channel at
F    | `<nicks>:<second>` | [m_nickflood](../../Modules/2.0/nickflood.md) | Limits the rate users can change nicks at
g    | `<globpattern>` | [m_chanfilter](../../Modules/2.0/chanfilter.md) | Listmode allowing chanops to filter channel messages
G    | *none*     | [m_censor](../../Modules/2.0/censor.md) | Fitlers config-defined bad words from messages
h    | `<nick>`   | [m_halfop](../../Modules/2.0/halfop.md) | Marks a user as a half-operator
H    | `<lines>:<seconds>` | [m_chanhistory](../../Modules/2.0/chanhistory.md) | Shows recent activity to new joins
I    | `<nick!user@host>` | [m_inviteexception](../../Modules/2.0/inviteexception.md) | Listmode allowing a user to bypass cmode `i`
j    | `<joins>:<second>` | [m_joinflood](../../Modules/2.0/joinflood.md) | Limits the rate users can join at
J    | `<seconds>` | [m_kicknorejoin](../../Modules/2.0/kicknorejoin.md) | User cannot rejoin after a `KICK` until `<seconds>` have elapsed
K    | *none*     | [m_knock](../../Modules/2.0/knock.md) | Users may not `KNOCK` on the channel
L    | `<#channel>` | [m_redirect](../../Modules/2.0/redirect.md) | Channel to redirect a user to once `l`'s limit has been reached
M    | *none*     | [m_services_account](../../Modules/2.0/services_account.md) | Only users authenticated to services may speak
N    | *none*     | [m_nonicks](../../Modules/2.0/nonicks.md) | Users may not change nickname in channel
O    | *none*     | [m_operchans](../../Modules/2.0/operchans.md) | Only operators may join the channel
P    | *none*     | [m_permchannels](../../Modules/2.0/permchannels.md) | Marks a channel as permanent
q    | `<nick>`   | [m_chanprotect](../../Modules/2.0/chanprotect.md) | Marks a user as a channel founder
q    | `<nick!user@host>`<sup>1</sup> | [m_quietban](../../Modules/2.0/extras/quietban.md) | Listmode that prevents matching users from speaking
Q    | *none*     | [m_nokicks](../../Modules/2.0/nokicks.md) | Only `ULINE`s can `KICK`
R    | *none*     | [m_services_account](../../Modules/2.0/services_account.md) | Only users authenticated to services may join
S    | *none*     | [m_stripcolor](../../Modules/2.0/stripcolor.md) | Strips color from all messages
T    | *none*     | [m_nonotice](../../Modules/2.0/nonotice.md) | Users may not `NOTICE` the channel
u    | *none*     | [m_auditorium](../../Modules/2.0/auditorium.md) | Makes the channel's userlist invisible
w    | `<prefix>:<nick!user@host>` | [m_autoop](../../Modules/2.0/autoop.md) | Listmode allowing for basic channel ACL
y    | *none*     | [m_operprefix](../../Modules/2.0/operprefix.md) | Marks a channel user as a network operator
Y    | *see mod page* | [m_ojoin](../../Modules/2.0/ojoin.md) | Marks a user as an operator on official network business
z    | *none*     | [m_sslmodes](../../Modules/2.0/sslmodes.md) | Only users using SSL may join
Z    | *see mod page* | [m_namedmodes](../../Modules/2.0/namedmodes.md) | See module page for explanation

1) This is an 'extra' module **and is not compiled by default**.

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
a    | [m_hideidle](../../Modules/2.0/extras/hideidle.md)<sup>1</sup> | Hides a user's `IDLE` time from `WHOIS`
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
L    | [m_redirect](../../Modules/2.0/redirect.md) | Prevents a user from being redirected by cmode `L`
Q    | [m_invisible](../../Modules/2.0/extras/invisible.md)<sup>1</sup> | Allows the user to join a channel without appearing to users in it
R    | [m_services_account](../../Modules/2.0/services_account.md) | Client must be authenticated to services to message the user
S    | [m_stripcolor](../../Modules/2.0/stripcolor.md) | Strips color from incoming private messages
T    | [m_noctcp_user](../../Modules/2.0/extras/noctcp_user.md)<sup>1</sup> | Blocks `CTCP`s sent to the user
W    | [m_showwhois](../../Modules/2.0/showwhois.md) | Shows the user when and who `WHOIS`'s them
x    | [m_cloaking](../../Modules/2.0/cloaking.md) | Hides a user's real host

1) This is an 'extra' module **and is not compiled by default**.
