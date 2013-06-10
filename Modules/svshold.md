---
title: Modules &raquo; m_svshold
layout: default
---

## Description

Provides SVSHOLD implementation for services. Allows `q:line` of a specific nick, allowing for services to do
easy nick enforcement.

## Configuration Tags

This module implements no configuration directives.

## Commands

`/SVSHOLD` ( **oper-only**)

**Please see [Special Notes](svshold.md#special-notes) before trying to use this command.**

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

While it is possible for an oper to use this command with `SVSHOLD` in their `o:line`, **this is not recommended**.
**This command is meant to be used by services only.** Misuse of this command can cause collisions, and possibly 
even desyncs. 

**YOU HAVE BEEN WARNED.**
