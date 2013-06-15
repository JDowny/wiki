---
title: Modules &raquo; m_[MODULE NAME]
layout: default
---

## Description

Provides opers With a command to change any user's ident.

## Configuration Tags

This module implements no configuration directives.

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/CHGIDENT <nick> <new ident>` | Yes | N/A | Changes the ident of `<nick>` to `<new ident>`. Command will return an error if `<new ident>` is invalid.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

Once the ident is changed there is no record of the previous ident, and bans will *only* match against the new one. 
