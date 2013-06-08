---
title: Modules &raquo; m_banredirect
layout: default
---

## Description	

Allows an extended ban (`+b`) syntax redirecting banned users to another channel. The extension allows channel bans
in the format `+b nick!ident@host#channel`, where `#channel` is where a user matching the ban will be redirected to when
they attempt to join the channel the ban is set on. This doesn't affect normal `nick!ident@host` bans which can
be set as normal. 

## Configuration Tags

This module does not require any extra configuration, beyond the `<module>` tag to load it.

## Commands

This module does not implement any commands.

## User Modes

This module does not implement any user modes.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

The module does not introduce a new extban mode, but allows suffixing a target channel to the ban hostmask.

## Special Notes

This supports partial banmask expansion (e.g. `/mode #channel +b Bob` actually applying a banmask of `Bob!*@*`) 
like the core does. The behavior should be the same as the core.

When this module is unloaded it will reset all bans *with* redirections to bans *without* the redirection. So on unload 
you'll see a load of mode changes something like:

`22:04 -!- ServerMode/#channel1 [-b+b *!*@*.mibbit.com#mibbets *!*@*.mibbit.com] by test.server.net`

Also, if there are multiple bans matching a user the first one to be set will be the one which is applied. 
