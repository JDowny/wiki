---
title: Modules &raquo; m_globops
layout: default
---

## Description

Provides opers with a command to send messages to all users with a specific SNOMASK.

## Configuration Tags

This module implements no configuration directives.

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/GLOBOPS <message>` | Yes | N/A | Send `<message>` to all users with SNOMASK `g`

## User Modes

This module implements no user modes.

## SNOMASK

SNOMASK | Oper-Only | Description
------- | --------- | -----------
g | ??? | Receive all messages sent with the `GLOBOPS` command.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

We have a report that [m_globops](globops.md) is required for Anope Services v1.7.21. (Reported while 
using InspIRCd 1.1.16) 
