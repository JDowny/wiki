---
title: Modules &raquo; m_conn_umodes
layout: default
---

## Description

This module allows the setting or removing of user modes on a user when they connect based on 
the `<connect:allow>` tag the user matches.

## Configuration Tags
<connect 
[removed] 
modes="+x">

Attribute | Type | Description
--------- | ---- | -----------
modes | string | Modes to add or remove from the user on connect.

This should not be a new tag, but instead added to your existing `<connect>` tag(s). For a list of user modes see 
[Usermode List](PLACEHOLDER) For more `<connect>` configuration options see [Connect Configuration](PLACEHOLDER).

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
