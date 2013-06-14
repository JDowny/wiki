---
title: Modules &raquo; m_banredirect
layout: default
---

## Description	

Creates an extban that allows redirecting banned users to another channel. The extension allows channel bans
where a user matching the ban will be redirected the channel in the extban when they attempt to join the channel 
the extban is set on. This doesn't affect regular `nick!ident@host` bans which can be set as normal. 

## Configuration Tags

This module implements no configuration directives.

## Commands

This module implements no commands.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

The module does not introduce a new extban mode, but allows suffixing a target channel to the ban hostmask.

Letter | Format | Description
------- | ----------- | ---------
*<sup>1</sup> | `[*:]<nick!user@host><#channel>` | Allows redirecting a banned user to another channel. Can be combined with any other extbans.

1) This extban can be combined with any other extban, though using in combination with another extban is **not** required.

## Special Notes

This supports partial banmask expansion (e.g. `/mode #channel +b Bob` actually applyies a banmask of `Bob!*@*`) 
like the core does. The behavior should be the same as the core.

When this module is unloaded it will reset all bans *with* redirections to bans *without* the redirection. So on unload 
you'll see a load of mode changes something like:

`22:04 -!- ServerMode/#channel1 [-b+b *!*@*.mibbit.com#mibbets *!*@*.mibbit.com] by test.server.net`

Also, if there are multiple bans matching a user the first one to be set will be the one which is applied. 
