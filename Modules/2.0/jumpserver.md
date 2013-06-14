---
title: Modules &raquo; m_jumpserver
layout: default
---

## Description

Provides opers with the `/JUMPSERVER` command which can be used to bounce clients that support the `RPL_REDIR` numeric
to another server.

## Configuration Tags

This module implements no configuration directives.

## Commands

`/JUMPSERVER [ <newserver> <newport> <+/-flags> [:reason] ]` - Sets or unsets jumpserver mode.

If no parameters are given, jumpserver mode is cancelled, if it is currently set.

If setting, rather than unsetting, `/JUMPSERVER` three parameters MUST be provided:

* `<newserver>` - A server to redirect new connections to (Can be either IP address (`10.1.2.3`) or DNS name (`irc.server.tld`))
* `<newport>` - A port on the new server to connect to (`6697`, `6667`, etc.)
* `<flags>` - Zero or more flags to set options on the redirect. To specify no flags, use `+` for `flags`. The available flags are as follows:
 * `a` - Redirect all users immediately (except for opers) and cause them to quit with the given reason.
 * `n` - Redirect any new users who connect and cause them to quit during registration.
 * Using `+` and `-` sets and unsets these flags. The default flags are `-a+n`, which will only redirect new users. 

* The `reason` parameter is optional, and if not provided defaults to `Please use this server/port instead` (the default 
given in various numeric lists) 

Examples:

* Redirecting all **new and existing** connections to `irc.server.tld` on port `6697` with the message `Please go to irc.server.tld`:
 * `/JUMPSERVER irc.server.tld 6697 +na :Please go to irc.server.tld`
* Disabling `/JUMPERSERVER`:
 * `/JUMPSERVER`

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

Be sure not to accidentally disconnect if flag +`n` is given, or you may be unable to get back onto your IRC server! 
All `JUMPSERVER` settings are applied locally only.

Jumpserver will jump users to any server you specify whether it's usable or not and whether it's part of your network or not.

### Important Note

This numeric is only supported by a subset of IRC clients, notably mIRC. **Other clients will ignore the numeric and may
hammer your server with reconnects.** You have been warned! 
