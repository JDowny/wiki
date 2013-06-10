---
title: Modules &raquo; m_SVSHOLD
layout: default
---

## Description

Provides SVSHOLD implementation for services. Allows QLine of a specific nick to eg. do easy nick enforcing. 

## Configuration Tags

This module does not implement any configuration directives.

Provide thorough examples.

## Commands

`/SVSHOLD` ( **oper-only**)

**Please see [Special Notes](svshold.md#special-notes) before trying to use this command.**

## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

While it is possible for an oper to use this command with `SVSHOLD` in their o:line, **this is not recommended**.
**This command is meant to be used by services only.** Misuse of this command can cause collisions, and possibly 
even desyncs. YOU HAVE BEEN WARNED.
