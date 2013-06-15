---
title: Modules &raquo; m_helpop
layout: default
---

## Description

The Helpop module adds support for the `HELPOP` command, which allows users to get help on IRCd commands. 

## Configuration Tags

WRITE ME

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/HELOP <text>` | No | N/A | Provides information on the command `<text>`

Examples:

* Get help with the `TOPIC` command:
 * `/HELPOP topic`
* Get a list of all available helpop topics:
 * `/HELPOP index`

## User Modes

Mode | Oper-Only | Description
---- | --------- | -----------
h | Yes | Marks a user as available for help.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

