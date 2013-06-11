---
title: Modules &raquo; m_swhois
layout: default
---

## Description

Allows you to specify extra data to be sent in a user's `/WHOIS` as a `320` numeric. 

## Configuration Tags

Attribute | Type | Description
--------- | ---- | -----------
`<type:swhois>` | string | When an oper opers-up then they will be given the string as a `SWHOIS`.
`<oper:swhois>` | string | When an oper opers-up they will be given the string as a SWHOIS`. See [note below](swhois.md#special-notes) on what takes precedence. 

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/SWHOIS <user> <swhois> [more swhois]` | Yes | N/A | Lets an oper set the `SWHOIS` field of `<user>` to `<swhois>` (all parameters after `<user>` will be used). 

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

When you specify `<type:swhois>` and `<oper:swhois>`, the `<oper>` block takes precedence over the `<type>` block .
