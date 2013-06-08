---
title: Modules &raquo; m_allowinvite
layout: default
---

## Description	

Provides support for channel mode `+A`, allowing `/invite` freely on a
channel (and extban A to allow specific users it)

## Configuration Tags

This module does not require any extra configuration, beyond the `<module>` tag to load it.

## Commands

This module does not implement any commands.

## Channel Modes

Mode | Description
---- | -----------
A | Set this mode to allow anyone to `/invite` users to your channel (not just ops).

Example: `/mode #channel +A`

## User Modes

This module does not implement any user modes.

## Extended Bans

Mode | Description
---- | -----------
A | Extended Ban A:nick!user@host -- Set this on specific users to disallow them from sending /invites to your channel (for example, if the user is abusing /invite). 

Example: `/mode #channel +b A:nick!user@host`
