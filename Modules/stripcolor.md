---
title: Modules &raquo; m_stripcolor
layout: default
---

## Description

Strips color codes used by clients such as KVIRC, mIRC, XChat, etc.

## Configuration Tags

This module does not implement any configuration directives.

## Commands

This module does not implement any commands.

## User Modes

Mode | Oper-Only | Description
---- | --------- | -----------
S | No | Strips color from all incoming `PRIVMSG`'s (does not include channel `PRIVMSG`'s)

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Format | Description
------- | ----------- | ---------
S | +S | Strips color from all channel messages (`PRIVMSG`).

## Extended Bans

This module does not implement any extended bans.

## Special Notes

None.
