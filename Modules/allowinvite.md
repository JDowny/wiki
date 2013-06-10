---
title: Modules &raquo; m_allowinvite
layout: default
---

## Description	

Provides support for channel mode `A`, allowing `/INVITE` freely on a
channel (and extban `A` to allow only specific host masks free use of `/INVITE`)

## Configuration Tags

This module implements no configuration directives.

## Commands

This module implements no commands.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Format | Description
------- | ----------- | ---------
A | `+A` | Allows any channel member to `/INVITE` a user to the channel.

Example: 

* Set `#foobar` +`A`
 * `/mode #channel +A`

## Extended Bans

Letter | Format | Description
------- | ----------- | ---------
A | `A:<nick!user@host>` | This blocks users that match the mask from using `/INVITE` on the channel, even if the channel is +`A`.

Examples:

* Block the nickname `lamer` from inviting people to `#baz` even though `#baz` is +`A`:
 * `/MODE #baz +b A:lamer!*@*`
* Block anyone from `*!*@crapISP` from inviting people to `#best` even though `#best` is +`A`:
 * `/MODE #best +b A:*!*@crapISP`
* Allow the nickname `gooduser` to invite people to `#testing` even though `#testing` is -`A`:
 * `/MODE #testing +e A:gooduser!*@*`
* Allow anyone from `*!*@172.18.12.192` to invite people to `#RFC1918` even though `#RFC1918` is -`A`:
 * `/MODE #RFC1918 +e A:*!*@172.18.12.192`

## Special Notes

None.
