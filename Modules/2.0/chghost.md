---
title: Modules &raquo; m_chghost
layout: default
---

## Description

Provides opers With a command to change any users' vhost

## Configuration Tags

**Optional**: If you want to use special chars for hostnames you can specify your own custom list of chars with 
the `<hostname>` tag:

`<hostname charmap="abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ.-_/0123456789">`

Attribute | Type | Description
--------- | ---- | -----------
charmap | string | A list of chars accepted as valid by the `CHGHOST` and `SETHOST` commands. Also note that the list is **case-sensitive**.

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/CHGHOST <nick> <new host>` | Yes | N/A | Changes the vhost of any connected user

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

The hostname given must be a valid hostname and may not contain any illegal characters.

Note that internally the network still knows the user's real hostname and uses it for many internal functions 
still such as `KLINE`/`GLINE` matching. 
