---
title: Modules &raquo; m_banexception
layout: default
---

## Description

List mode that provides a way to exempt host masks (`nick!user@host`) from bans. Any user matching an exception mask
is exempt from any ban masks that otherwise would have prevented them from joining the channel. This mode also works
with extended bans.

## Configuration Tags

This module does not implement any configuration directives.

## Commands

This module does not implement any commands.

## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Format | Description
------- | ----------- | ---------
e | `+e <nick!user@host>` | Exempts the mask from any matching bans. Also works with extbans.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

None.
