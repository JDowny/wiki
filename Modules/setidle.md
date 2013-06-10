---
title: Modules &raquo; m_setidle
layout: default
---

## Description

Allows an oper to change their `IDLE` time shown in local `/WHOIS` results.

## Configuration Tags

This module does not implement any configuration directives.

## Commands

`/SETIDLE <duration>` ( **oper-only** )

Sets your idle time to duration. Duration may be specified in seconds, or in the following format: 
`1y2w3d4h5m6s` meaning one year, two weeks, three days, 4 hours, 5 minutes and 6 seconds. 
All fields in this format are optional. 

Examples:

* Set your `IDLE` time to five weeks:
 * `/SETIDLE 5w`
* Set your `IDLE` time to three days and ten minutes:
 * `/SETIDLE 3d10m`

## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

If you attempt to set an idle time greater than your signon time, your signon time will also be adjusted so that 
the figures make sense. 
