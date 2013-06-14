---
title: Modules &raquo; m_chanhistory
layout: default
---

## Description

Provides a channel mode which sends a configurable amount of channel backlog to new `JOIN`s to a channel.

## Configuration Tags

This module implements no configuration directives.

## Commands

This module implements no commands.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Format | Description
---- | ------ | -----------
H | `+H <X>:<T>` | Shows the last `<X>` lines sent within the last `<T>` seconds to any newly joining users. `<X>` has a hard limit of `50`.

See the [Special Notes](chanhistory.md#special-notes) on the rational for the hard limit.

Examples:

* Set `#foo` to show the last `20` lines sent within 5 minutes to newly joining users:
 * `/MODE #food +H 20:300`
* Set `#bar` to show the last `10` lines within 10 minutes to newly joining users:
 * `/MODE #bar +H 10:600`

## Extended Bans

This module implements no extended bans.

## Special Notes

This module is hard-coded to cap the maximum number of lines at `50`. If the cap didn't exist, a network with a large
number channels using [m_chanhistory](chanhistory.md) could overwhelm the IRCd server, slowing it down unnecessarily.
