---
title: Modes
layout: default
---

# Channel Modes

### Core Channel Modes

Mode | Parameters | Function
---- | ---------- | --------	
b    | `<nick!user@host>`   | Prevents users matching the mask from joining. Accepts wildcards.
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
a    | [m_hideidle](hideidle.md)<sup>1</sup> | Hides a user's `IDLE` time from `WHOIS`
B    | [m_botmode](botmode.md)  | Marks a user as a bot
c    | [m_commonchans](commonchans.md) | Requires a client to share channels with the user to private message them
d    | [m_deaf](deaf.md) | User will not receive channel messages
D    | [m_privdeaf](privdeaf.md)<sup>1</sup> | User will not recieve messages outside of channels
g    | [m_calleride](callerid.md) | Allows a user to screen private messages
G    | [m_censor](censor.md)    | Filters config-defined bad words from user's private messages
h    | [m_helpop](helpop.md) | Marks a user as available to help
H    | [m_hideoper](hideoper.md) | Hide's a user's operator status from non-operators
I    | [m_hidechans](hidechans.md) | Hides the channel a user is in from `WHOIS`
k    | [m_servprotect](servprotect.md) | Essentially, god mode
Q    | [m_invisible](invisible.md)<sup>1</sup> | Allows the user to join a channel without appearing to users in it
R    | [m_services_account](services_account.md) | Client must be authenticated to services to message the user
S    | [m_stripcolor](stripcolor.md) | Strips color from incoming private messages
T    | [m_noctcp_user](noctcp_user.md)<sup>1</sup> | Blocks `CTCP`s sent to the user
W    | [m_showwhois](showwhois.md) | Shows the user when and who `WHOIS`'s them
x    | [m_cloaking](cloaking.md) | Hides a user's real host

1) This is an 'extra' module **and is not compiled by default**.
