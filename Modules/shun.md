---
title: Modules &raquo; m_shun
layout: default
---

## Description

Provides the `/SHUN` command. Makes it impossible for a `/SHUN`'d client to use any command other than the ones allowed.
This is meant as one way to deal with persistent ban-evading users.

## Configuration Tags

`<shun enabledcommands="PING PONG QUIT PART JOIN" notifyuser="yes" affectopers="no">`

Attribute | Type | Description
--------- | ---- | -----------
affectopers | bool | Whether or not it's possible to `/SHUN` opers.
enabledcommands | string | The commands a `/SHUN`'d client can use. Note that without at least `/PING` and `/PONG` the `/SHUN`'d client will timeout and disconnect. The defaults are suggested as the compromise between sandboxing the `/SHUN`'d user and

# You may also configure which commands you wish a user to be able to
# perform. It should be noted that if a shunned user issues QUIT or PART
# then their message will be removed, as if they did not issue one.
#
# You can (optionally) let the user know that their command was blocked.
#
# You may also let SHUN affect opers (defaults to no).

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/SHUN <hostmask> <duration> <reason>` | Yes | N/A | Add a shun on 'hostmask', duration is a string like `5m2d` for five minutes and two days. The reason is shown in the list of shuns and in the snotices sent to opers.
`/SHUN <hostmask>` | Yes | N/A | Remove a shun on `<hostmask>`
`/STATS S` | Yes | N/A | List all `/SHUNS`


`-tiddles.chatspike.net-*** Om added 300 second shun on 'Omster!*@*' (Rawr)`

`-tiddles.chatspike.net-*** Om removed shun 'Omster!*@*', set 219 seconds ago with reason 'Rawr'`

<< stats S
>> :tiddles.chatspike.net 223 Om :*!*@lamers.com 1139134777 432000 Om Rawr
>> :tiddles.chatspike.net 219 Om s :End of /STATS report


## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

None.
