---
title: Modules &raquo; m_gecosban
layout: default
---

## Description

Provides a channel ban using `GECOS`/real name field.

## Configuration Tags

This module implements no configuration directives.

## Commands

This module implements no commands.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

Letter | Format | Description
------ | ------ | -----------
r | `r:<glob mask>` | `<glob mask>` is matched against the real name every all users trying to join the channel. On match the user will be blocked from joining the channel.

## Special Notes

None.
