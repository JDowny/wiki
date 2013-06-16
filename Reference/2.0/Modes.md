---
title: Modes
layout: default
---

# Channel Modes

### Core Channel Modes

Mode | Parameters | Function
---- | ---------- | --------	
b    | `[glob]`   | Prevents users matching the nick!user@host `<glob>` from joining
i    | *none*     | Prevents users who have not been invited from joining
k    | `<key>`    | Prevents users who does not know the `<key>` (password) from joining
l    | `<limit>`  | Prevents more than `<limit>` users from joining
m    | *none*     | Prevents users who do not have voice or higher from talking
n    | *none*     | Prevents users who have not joined the channel from talking
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
s    | `<snomask>` | Allows the user to receive server notices
w    | *none*      | Allows the user to receive WALLOPS

### Module User Modes
