---
title: Modules &raquo; m_tline
layout: default
---

## Description

Allows an oper to issue a command to count the number of users matched by a host or IP mask, before adding a real ban 
or exception. 

## Configuration Tags

To use this command an oper must have `TLINE` specified in either their o:line's `<class:commands>` tag or the 
`<oper:commands>` tag.

Provide thorough examples.

## Commands

`/TLINE <host or IP mask>` ( **oper-only** )

Returns the number of local and global clients matched, the percentage of clients matched
and how they were matched (by either IP or hostname).

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
