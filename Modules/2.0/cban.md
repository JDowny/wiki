---
title: Modules &raquo; m_cban
layout: default
---

## Description

Allows temporary or permenant bans making the banned channels unusable. The reason supplied in the command will be 
displayed to users who try to join banned channels.

## Configuration Tags

This module implements no configuration directives.

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/CBAN <channel> [ <duration> :<reason> ] ` | Yes | N/A | Bans `<channel>` for `<duration>`, giving `<reason>` when a user tries to join it.

* Add a `CBAN` for `#channel` lasting 3 hours, 4 minutes and 5 seconds:
 * `/CBAN #channel 3h4m5s :reason`
* Add a permanent `CBAN` on `#lamers`:
 * `/CBAN #lamers 0s :lamers`
* Remove CBAN on `#channel`:
 * `/CBAN #channel`
* List all CBANs 
 * `/STATS C`

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

Note that this module does not use any timers in order to increase performance, this doesn't affect the 
operation of the module but on a low activity network the expiry notices may not be sent anywhere near the time 
they expire. This is purely a cosmetic issue. 
