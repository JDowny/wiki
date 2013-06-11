---
title: Modules &raquo; m_shun
layout: default
---

## Description

Provides the `/SHUN` command. Makes it impossible for a `/SHUN`'d client to use any command other than the ones allowed.
This is meant as possible method of dealing with persistent ban-evading users.

## Configuration Tags

`<shun enabledcommands="PING PONG QUIT PART JOIN" notifyuser="yes" affectopers="no">`

Attribute | Type | Description
--------- | ---- | -----------
affectopers | bool | Whether or not it's possible to `/SHUN` opers.
enabledcommands | string | The commands a `/SHUN`'d client can use. Note that without at least `/PING` and `/PONG` the `/SHUN`'d client will timeout and disconnect. The defaults are suggested as a compromise between sandboxing the `/SHUN`'d user and allowing the pretense of normal functionality.
notifyusers | bool | Whether or not to notify users their command was blocked.

It should be noted that if a shunned user issues `/QUIT` or `/PART` then their message will be removed, as if they 
did not issue one.

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/SHUN <hostmask> <duration> <reason>` | Yes | N/A | Add a shun on 'hostmask', duration is a string like `5m2d` for five minutes and two days. The reason is shown in the list of shuns and in the snotices sent to opers.
`/SHUN <hostmask>` | Yes | N/A | Remove a shun on `<hostmask>`
`/STATS S` | Yes | N/A | List all `/SHUN`s

* SNOTICE for a new `/SHUN`:
 * `-tiddles.chatspike.net-*** Om added 300 second shun on 'Omster!*@*' (Rawr)`
* SNOTICE for a removed `/SHUN`:
 * `-tiddles.chatspike.net-*** Om removed shun 'Omster!*@*', set 219 seconds ago with reason 'Rawr'`
* `/STATS S`:
 * `/STATS S`
 * `:tiddles.chatspike.net 223 Om :*!*@lamers.com 1139134777 432000 Om Rawr`
 * `:tiddles.chatspike.net 219 Om s :End of /STATS report`

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
