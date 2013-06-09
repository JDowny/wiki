---
title: Modules &raquo; m_halfop
layout: default
---

## Description

Provides channel half-operators (`h`) and the 'prefix' attached to users with the mode.

## Configuration Tags

This module does not implement any configuration directives.

## Commands

This module does not implement any commands.

## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Format | Description
------- | ----------- | ---------
h | `+h nickname` | Marks a user as a channel halfop. `h` users may set some channel modes (including `v` on users). 
`h` users may also kick users ranked below them (`v` and non-moded users). A `h` user may remove their own status.


## Extended Bans

This module does not implement any extended bans.

## Special Notes

With InspIRCd 2.0 halfops may kick other halfops when using this module. 
