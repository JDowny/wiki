---
title: Modules &raquo; m_blockamsg
layout: default
---

## Description

This module attempts to block usage of the clientside `AMSG` and `AME` commands.

This module will probably never be 100% perfect, it guesses behaviour of clients and a moderately clever client 
script could bypass it altogether. However it does completely block a standard `AMSG` from mIRC, and a standard 
`AMSG` from XChat will only be seen on one of the channels it would otherwise have been sent to.

## Configuration Tags

`<blockamsg delay="3" action="killopers">`

Attribute | Type | Description
--------- | ---- | -----------
delay | int |  How many seconds between two messages to force them to be recognised as unrelated.
action | string | Any of `notice`, `noticeopers`, `silent`, `kill` or `killopers`. Define how to take action when a user uses `AMSG` or `AME`

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

None.
