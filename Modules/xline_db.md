---
title: Modules &raquo; m_xline_db
layout: default
---

## Description

Module that puts `X:Lines` into a file database that is persistent across server restarts. 

## Configuration Tags

This module does not implement any configuration directives.

## Commands

This module does not implement any commands.

## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

Stores all `*:Lines` (`G`/`Z`/`K`/`R` and any others added by modules) in a file `xline.db` which is re-loaded on 
restart. This is useful for two reasons: it keeps the bans so users may not evade them, and on bigger networks, server 
connections will take less time as there will be a fewer bans to apply (since most bans will already be applied 
pre-link).
