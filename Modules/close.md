---
title: Modules &raquo; m_close
layout: default
---

## Description

Adds a command for opers to close all unregistered connections to the server.

## Configuration Tags

This module implements no configuration directives.

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/CLOSE` | Yes | N/A | Closes all currently unregistered connections to the server.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

**Note**: `Unregistered connections` means all connections which have not fully connected to the IRC network 
(Sent preliminary `NICK`/`USER`/`PASS`), and has nothing to do with IRC services. 

This command can be useful for connection floods.
