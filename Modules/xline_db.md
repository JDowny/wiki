---
title: Modules &raquo; m_xline_db
layout: default
---

## Description

Module that puts `x:line`s into a file database that is persistent across server restarts. 

## Configuration Tags

This module implements no configuration directives.

## Commands

This module implements no commands.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

Stores all `*:line`s (`G`/`Z`/`K`/`R` and any others added by modules) in a file `xline.db` which is re-loaded on 
restart. This is useful for two reasons: 

* It keeps the bans, making it more difficult for users to evade them
* On bigger networks, server connections will take less time as there will be a fewer bans to apply (since most bans will already be applied pre-link).
