---
title: Modules &raquo; m_tline
layout: default
---

## Description

Allows an oper to issue a command to count the number of users matched by a host or IP mask, before adding a real ban 
or exception. 

## Configuration Tags

This module does not implement any configuration directives.

Provide thorough examples.

## Commands

`/TLINE <host or IP mask>` - Returns the number of local and global clients matched, the percentage of clients matched
and how they were matched (by either IP or hostname).

**This command is oper-only, and requires an oper to have** `TLINE` **as a permission in their configuration block**
**to use it.**

## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

None.
