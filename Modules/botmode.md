---
title: Modules &raquo; m_botmode
layout: default
---

## Description

This module allows bots to set a mode on themselves making them easy to identify.

## Configuration Tags

This module implements no configuration directives.

## Commands

This module implements no commands.

## User Modes

Mode | Oper-Only | Description
---- | --------- | -----------
B | No | Mode to mark bots. Some services packages will use this mode to ignore users with it, preventing bot loops.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

This mode doesn't really do anything, and is largely based upon users telling their bots to set it on themselves.

One possible way of making using this easier is to use [m_conn_umodes](conn_umodes.md) along with a connection class
specifically set aside for bots to set umode +`B` on any clients connecting using the class.
