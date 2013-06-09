---
title: Modules &raquo; m_jumpserver
layout: default
---

## Description

Provides opers With the `/JUMPSERVER` command which can be used to bounce clients to another server which support the 
`RPL_REDIR` numeric.

## Configuration Tags

This module does not implement any configuration directives.

Provide thorough examples.

## Commands

`/JUMPSERVER <newserver> <newport> <+/-flags> [:reason]` - Sets or unsets jumpserver mode.

If no parameters are given, jumpserver mode is cancelled, if it is currently set.

If parameters are given, a server address must be given for <newserver> and a server port must be given for <newport>. 
Zero or more status flags should be given for `flags`, from the list below (if you do not wish to specify any flags 
just place a `+` in this field): 

`a` - Redirect all users immediately (except for opers) and cause them to quit with the given reason.
`n` - Redirect any new users who connect and cause them to quit during registration.
    
You may use `+` and `-` to set or unset these flags in the command, the default flags are `-a+n`, which will just 
redirect new users. 

The `reason` parameter is optional, and if not provided defaults to `Please use this server/port instead` (the default 
given in various numeric lists) 

Example: `/JUMPSERVER newplace.chatspike.net 6697 +na :Please go to different.irc.server`

## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

Be sure not to accidentally disconnect if flag +`n` is given, or you may be unable to get back onto your IRC server! 
All `JUMPSERVER` settings are applied locally only.

Jumpserver will jump users to any server you specify whether it's usable or not and whether it's part of your network or not.

### Important Note

This numeric is only supported by a subset of IRC clients, notably mIRC. **Other clients will ignore the numeric and may**
**hammer your server with reconnects.** You have been warned! 
