---
title: Modules &raquo; m_userip
layout: default
---

## Description

Adds the `/USERIP` command, which will show the ident and ip address of one or more connected users. 

## Configuration Tags

An oper must have `USERIP` specified in either their o:line's `<class:commands>` tag or the `<oper:commands>` tag.

## Commands

`/USERIP <nick> [<nick2> <nick3> <nick4> <nickX>]` ( **oper-only** )

Looks up the IP of one or more users.

## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

The output for this command is identical to `/USERHOST`, except IP addresses are given instead of hostnames. 
Because this command can expose real IP addresses it is for operator use only. 
