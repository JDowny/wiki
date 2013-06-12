---
title: Modules &raquo; m_cycle
layout: default
---

## Description

Cycles a channel (`PART`s and re-`JOIN`s), overriding restrictions that would stop a new user joining, such as 
User Limits and Channel Keys. 

## Configuration Tags

This module implements no configuration directives.

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/CYCLE <channel> [reason]` | Yes | N/A | `PART`s then re-`JOIN`s a user to a channel, bypassing any modes that would otherwise stop a new user from joining.

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
