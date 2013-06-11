---
title: Modules &raquo; m_customprefix
layout: default
---

## Description

Allows custom prefix modes to be created. This can be used to achieve a desired ranking system. Note that this 
module deprecates [m_chanprotect](chanprotect.md) and [m_halfop](halfop.md).

## Configuration Tags

`<customprefix name="founder" letter="q" prefix="~" rank="50000" ranktoset="50000">`
`<customprefix name="admin" letter="a" prefix="&" rank="40000" ranktoset="50000">`
`<customprefix name="halfop" letter="h" prefix="%" rank="20000" ranktoset="30000">`
`<customprefix name="halfvoice" letter="V" prefix="-" rank="1" ranktoset="20000">`

Attribute | Type | Description
--------- | ---- | -----------
name | string | The name of the mode, **must be unique from other modes**
letter | string | The letter used for this mode. **Required**.
prefix | string | The prefix used for nicks with this mode. Not required.
rank | int | A numeric rank for this prefix, defining what permissions it gives; `VOICE_VALUE` is `10000`, `HALFOP_VALUE` is `20000`, `OP_VALUE` is `30000`
ranktoset | int | The numeric rank required to set/unset this mode. Defaults to `rank`.
depriv | bool |  Can you remove the mode from yourself? **Defaults to** `yes`. 

## Commands

This module implements no commands.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

With this module you can make almost any letter into a channelmode that has to represent a prefix. **Make sure you 
don't use channelmodes that are being used by other modules!**

## Extended Bans

This module implements no extended bans.

## Special Notes

Some clients may not recognise the prefixes which you have defined.
