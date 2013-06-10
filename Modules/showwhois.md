---
title: Modules &raquo; m_showwhois
layout: default
---

## Description

Provides usermode `W` allowing opers to see when they are `/WHOIS`'d by another user, and who performed it. 
It is possible to configure this module to allow **all** users to see when someone `/WHOIS`'s them and who performed it.

## Configuration Tags

`<showwhois opersonly="yes" showfromopers="yes">`

Attribute | Type | Description
--------- | ---- | -----------
opersonly | bool | Set to `yes` to only allow ircopers to use this mode. Set to `no` to allow **all** users to use it.
showfromopers | bool | Set to `no` to prevent the `/WHOIS` alert when an oper is the user doing the `/WHOIS` on the person with user mode `+W`
set.

## Commands

This module implements no commands.

## User Modes

Mode | Oper-Only | Description
---- | --------- | -----------
U | Yes<sup>1</sup> | Allows the user to see when somebody `/WHOIS`'s them, and who performed it.

1) It is possible to allow non-opers to use this mode via the configuration directive `operonly`.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

None.
