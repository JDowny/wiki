---
title: Modules &raquo; m_timedbans
layout: default
---

## Description

Allows channel operators to set timed bans which will expire once the duration is up. Timed bans appear as if set by
the user who placed and are removed by the server.

## Configuration Tags

This module implements no configuration directives.

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/TBAN <channel> <duration> <mask>` | No | Yes | Sets a timed ban on `<mask>` for `<duration>`

Availabe time formats: `1w2d3h4m6s`

Alternatively duration can be specified purely in seconds.

All `/TBAN`s appear in the ban list as regular bans and may be safely removed before they expire.

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
