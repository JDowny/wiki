---
title: Modules &raquo; m_dcc allo9w
layout: default
---

## Description

Adds a command for users to allow other users to `DCC` them.

## Configuration Tags

`<dccallow blockchat="yes" length="5m" action="block">`

Attribute | Type | Description
--------- | ---- | -----------
action | string | Default action to take if no action is specified can be `block` or `allow`
blockchat | bool | Whether to block DCC CHAT as well as DCC SEND
length | string | Default duration of entries in DCCALLOW list (uses standard duration format: `1y2w3d4m5s`)

`<banfile pattern="*.txt" action="allow">`

Attribute | Type | Description
--------- | ---- | -----------
action | string | Action to take if a user attempts to send a file that matches this pattern. Can be `block` or `allow`
pattern | string | Glob pattern to match files against

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/DCCALLOW <+/-> <nick> <duration>` | No | N/A | Allows DCC from `<nick>` for `<duration>`

Examples:

* List the nicknames in the `DCCALLOW` list:
 * `/DCCALLOW`
* Add `Brain` to your `DCCALLOW` list for the default time in the config:
 * `/DCCALLOW +Brain`
* Remove `Brain` from your `DCCALLOW` list:
 * `/DCCALLOW -Brain`
* Add `Brain` to your `/DCCALLOW` list until you quit:
 * `/DCCALLOW +Brain 0

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
