---
title: Modules &raquo; m_halfop
layout: default
---

## Description

Provides channel half-operators (`h`) and the 'prefix' attached to users with the mode.

**Please note that m_halfop is deprecated and will be phased out in future versions in favor of 
[m_customprefix](customprefix.md)**

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
h | `+h <nickname>` | Marks a user as a channel halfop. Halfops may set some channel modes (including `v` on users). Halfops may also kick users ranked below them (`v` and non-moded users). A halfop may remove their own status.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

With InspIRCd 2.0 halfops may kick other halfops when using this module. 
