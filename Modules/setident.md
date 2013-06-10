---
title: Modules &raquo; m_setident
layout: default
---

## Description

Allows opers to modify their ident while connected to the IRCd.

## Configuration Tags

This module implements no configuration directives.

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/SETIDENT <ident>` | Yes | N/A | Changes the issuers ident to `<ident>` or returns an error if the new ident is invalid.

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
