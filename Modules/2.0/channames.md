---
title: Modules &raquo; m_channames
layout: default
---

## Description

Allow network administrators to change which characters are allowed in channel names.

## Configuration Tags

`<channames denyrange="2,3" allowrange="">`

Attribute | Type | Description
--------- | ---- | -----------
allowrange | string | What characters to allow
denyrange | string | What characters to deny

The above example will block IRC Control codes in channel names (Bold, color, reset, underline, reverse).

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

Space, bell, and comma will ALWAYS be disallowed in channel names due to the IRC protocol. 
