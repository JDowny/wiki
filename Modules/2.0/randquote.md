---
title: Modules &raquo; m_randquote
layout: default
---

## Description

Provides user with a random quote on connect. (UltimateIRCd style)

## Configuration Tags

With this module, the following tag is required in the config:

`<randquote file="/path/to/quotes.file">`

Attribute | Type | Description
--------- | ---- | -----------
file | string | The path to your quotes file (usually called `randquotes.conf`)

An example Quotes file is in the InspIRCd `conf` directory, called `inspircd.quotes.example`

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/RANDQUOTE` | No | N/A | Provides a random quote to connected users. 

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

Random Fact: [m_randquote](randquote.md) was created by Craig "FrostyCoolSlug" McLure and was InspIRCds first 
functional module with our API.
