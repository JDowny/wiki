---
title: Modules &raquo; m_delayjoin
layout: default
---

## Description

Channel mode `D` delays showing `/JOIN` messages until the user speaks. If they `/QUIT` or `/PART` before speaking,
their `/JOIN` message will not be shown. Helps cut down on noise in large channels in a more user-friendly way
than Auditorium mode (`u`).

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
D | +A | Hides `/JOIN`s until the user speaks.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

None.
