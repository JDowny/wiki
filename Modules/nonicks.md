---
title: Modules &raquo; m_nonicks
layout: default
---

## Description	

Provides support for channel mode `+N` and extban `+b N`, which prevents nick changes in a channel.

## Configuration Tags

This module does not require any extra configuration, beyond the `<module>` tag to load it.

## Commands

This module implements no commands.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Description
---- | -----------
N | Set this mode to disallow any nick changes in the channel.

Example: `/mode #channel +N`

## Extended Bans

Mode | Description
---- | -----------
N | Disallows a user (or rather a hostmask) from changing their nick.

Example: `/mode #channel +b N:nick!user@host`

## Special Notes

If a user attempts a nick change in a channel where `+N` is set, the user will receive the following message:
> Can't change nickname while on *#channel* (+N is set)
