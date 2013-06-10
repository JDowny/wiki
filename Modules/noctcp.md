---
title: Modules &raquo; m_noctcp
layout: default
---

## Description

Blocks `CTCP` to a channel.

## Configuration Tags

This module does not implement any configuration directives.

## Commands

This module implements no commands.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Format | Description
------- | ----------- | ---------
C | `+C` | Blocks all `CTCP` to a channel.

## Extended Bans

Letter | Format | Description
------- | ----------- | ---------
C | `C:nick!user@host` | Blocks all `CTCP` from users matching the mask.

## Special Notes

Not to be confused with the [m_blockcolor](wiki/Modules/blockcolor.md) module which blocks colour codes, this module 
will filter all `CTCP` messages except for `CTCP ACTION`, which is in fact used to create `/ME` messages.
