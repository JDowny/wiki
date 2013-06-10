---
title: Modules &raquo; m_watch
layout: default
---

## Description

Adds the `/WATCH` command, which is used by clients to maintain notify lists. The `/WATCH` command is a more 
efficient replacement for `/ISON` which consumes less bandwidth. 

## Configuration Tags

This module implements no configuration directives.

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/WATCH [ <C/L/S>/<+/-nickname> ]` | No | N/A | Adds or deletes a user from the issuer's watch list 

Examples:

* Add `luser` to the watchlist:
 * `/WATCH +luser`
* Remove `luser` from the watchlist:
 * `/WATCH -luser`

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

Usually this command is used directly by client software and not by users. The parameter `C` is an extension used by 
mIRC to clear the watch list (and therefore must be supported), and the parameter `S` is an extension also used by 
mIRC to query the watch list status.
