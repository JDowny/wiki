---
title: Modules &raquo; m_messageflood
layout: default
---

## Description

Allows channel operators/halfoperators to set a mode on their channel which prevents message/`NOTICE` 
flooding (spamming/scrolling) in a channel on the server side. 

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
---- | ------ | -----------
f | `+f [*]<lines>:<seconds>` | When a user types more than `<lines>` lines in `<seconds>` seconds, they're `KICK`'d by the server. If the mode prefixed with `*`, the user is banned in addition to being `KICK`'d.

Examples:

* Kickban a flooding user from `#foo` after `6` lines in `10` seconds
 * `/MODE #foo +f *6:10`
* Kick a flooding user from `#bar` after `2` lines in `6` seconds 
 * `/MODE #bar +f 2:6`

## Extended Bans

This module implements no extended bans.

## Special Notes

None.
