---
title: Modules &raquo; m_showwhois
layout: default
---

## Description

Provides usermode `W` allowing opers to see when they are `/WHOIS`'d by another user, and who it was performed by. 
It is possible to configure this module to allow **all** users to see when someone `/WHOIS`'s them and who performed it.

## Configuration Tags

Example: `<showwhois opersonly="yes" showfromopers="yes">`

`opersonly`

Set to `yes` to only allow ircopers to use this mode. Set to `no` to allow **all** users to use it.

`showfromopers`

Set to `no` to prevent the `/WHOIS` alert when an oper is the user doing the `/WHOIS` on the person with user mode `+W`
set.

## Commands

This module does not implement any commands.

## User Modes

Mode | Oper-Only | Description
---- | --------- | -----------
U | Yes* | Allows the user to see when somebody `/WHOIS`'s them, and who performed it.

* It is possible to allow non-opers to use this mode via the configuration directive `operonly`.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

None.
