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

## User Modes

This module does not implement any user modes.

## SNOMASK

This module does not implement any server notice masks.

## Channel Modes

Mode | Description
---- | -----------
A | Set this mode to allow anyone to `/invite` users to your channel (not just ops). | No

Example: `/mode #channel +A`

## Extended Bans

Mode | Description
---- | -----------
A | Extended Ban `A:nick!user@host` -- Set this on specific users to disallow them from sending `/INVITE`s to your channel (for example, if the user is abusing `/INVITE`). 

Example: `/mode #channel +b A:nick!user@host`

## Special Notes

None.
