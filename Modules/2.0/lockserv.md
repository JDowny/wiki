---
title: Modules &raquo; m_lockserv
layout: default
---

## Description

Allows an operator to temporarily close, then re-open, a server to new connections.

## Configuration Tags

This module implements no configuration directives.

## Commands

`/LOCKSERV` - Allows an operator to lock a server against all new connections, notifying users connecting afterwards
that the server is temporarily closed, and to try again later.

`/UNLOCKSERV` - Open the server back up to new connections.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

If your server is locked and you got disconnected, do a `REHASH` from shell and the server will be open again. 
