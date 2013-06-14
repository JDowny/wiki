---
title: Modules &raquo; m_[MODULE NAME]
layout: default
---

## Description

This module provides an 'auditorium mode' for channels. When a channel is set to auditorium mode, you can only see 
yourself (and optionally ops) on the nicklist, and `JOIN`s, `PART`s, `QUIT`s and `KICK`s are not shown. This saves 
bandwidth for **very** large (1k+ user) channels. 

## Configuration Tags

`<auditorium opvisible="no" opcansee="no" opercansee="yes">`

Attribute | Type | Description
--------- | ---- | -----------
opvisible | bool | Show channel ops to all users in the channel
opcansee | bool | Allow channel ops to see all `JOIN`s/`PART`s/`KICK`s in the channel
opercansee | bool | Allow opers with `channels/auspex` to see see all `JOIN`s/`PART`s/`KICK`s in the channel

Note: [m_exemptchanops](exemptchanops.md) can be used to adjust the level at which users become visible or
the level at which they can see the full member list of the channel.

## Commands

This module implements no commands.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Format | Description
---- | ------ | -----------
u | `+u` | Makes a channel's userlist, and makes all `JOIN`s/`PART`s/`KICK`s invisible.

## Extended Bans

This module implements no extended bans.

## Special Notes

None.
