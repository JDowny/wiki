---
title: Modules &raquo; m_stripcolor
layout: default
---

## Description

Strips color codes used by clients such as KVIRC, mIRC, XChat, etc.

## Configuration Tags

This module implements no configuration directives.

## Commands

This module implements no commands.

## User Modes

Mode | Oper-Only | Description
---- | --------- | -----------
S | No | Strips color from all incoming private messages. Does not include channel messages.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Format | Description
------- | ----------- | ---------
S | +S | Strips color from all channel messages.

## Extended Bans

Letter | Format | Description
------- | ----------- | ---------
S | `S:<nick!user@host>` | Strips color codes from the messages of users who match the mask.

## Special Notes

Note that color codes includes bold, underline and other text-control codes.
