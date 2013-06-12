---
title: Modules &raquo; m_deaf
layout: default
---

## Description

Provides a user mode which blocks all channel messages for the user. Private messages and `NOTICE`s aren't affected.

## Configuration Tags

This module implements no configuration directives.

## Commands

This module implements no commands.

## User Modes

Mode | Oper-Only | Description
---- | --------- | -----------
d | No | Blocks all channel messages and `NOTICE`s to the user.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

This mode will change how messages are routed between servers. If for example you have a channel with six users 
across six different servers, but all the users on the first of the six servers have `d` set on themselves, the 
message will not be routed to that server. This can provide a degree of bandwidth saving.

This mode can be useful for bots that do not need to receive channel messages.
