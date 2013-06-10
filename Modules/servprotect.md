---
title: Modules &raquo; m_servprotect
layout: default
---

## Description

Provides support for Austhex style +`k` / UnrealIRCD +`S` services mode. Intended to make tampering with services
more difficult for opers and users.

## Configuration Tags

This module implements no configuration directives.

## Commands

This module implements no commands.

## User Modes

Mode | Oper-Only | Description
---- | --------- | -----------
k | N/A | Makes a user unkillable and un-kickable except by `q:lines`. This mode is impossible for any user, oper or even `q:line` to set or unset after server introduction.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

This mode cannot be set or unset after client introduction even by a server or a uline. This mode may only be 
set by client introduction (e.g. the server to server `UID` command) making it impossible to abuse as a 
'god mode' by IRC operators and making it impossible for someone to take this mode away from a service in order 
to `/KILL` it. 
