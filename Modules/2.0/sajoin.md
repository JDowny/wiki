---
title: Modules &raquo; m_sajoin
layout: default
---

## Description

**S**ervices **A**dministrator **Join**. Forces a client to join a channel.

## Configuration Tags

To use this command an oper must have `SAJOIN` specified in either their o:line's `<class:commands>` tag or the 
`<oper:commands>` tag.

## Commands

`/SAJOIN <nick> <channel>` ( **oper-only** )

Forces `<nick>` to join `<channel>`.

## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

**Note**: This command will walk the `/SAJOIN`'d user through any bans or modes that would otherwise restrict them
from joining. Use with caution.

As with other `SA*` commands, misuse of this command may be seen as abusive by network users. The reader is advised
to be conservative in their usage.
