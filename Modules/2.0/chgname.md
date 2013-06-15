---
title: Modules &raquo; m_chgname
layout: default
---

## Description

Provides opers with a command which can be used to change the real name (`GECOS`) of any connected user.

## Configuration Tags

This module implements no configuration directives.

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/CHGNAME <nick> <new GECOS>` | Yes | N/A | Changes the `GECOS` of `<nick>` to `<new GECOS>`. Returns an error if the provided `GECOS` is invalid.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

Once the name is changed there is no record of the previous name, and bans will *only* match against the new one. 
