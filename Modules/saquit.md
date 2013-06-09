---
title: Modules &raquo; m_saquit
layout: default
---

## Description

**S**ervices **A**dministrator **Quit**. Forcibly `/QUIT`s a user from the IRC network. Note that this client is
different from a `/KILL` in that the user's client will interpret the command as if the user had issued the `/QUIT`,
and thus it will not try to re-connect.

## Configuration Tags

This module does not implement any configuration directives.

## Commands

`/SAQUIT <nick> <reason>` ( **oper-only** )

Forces `<nick>` to `/QUIT` with `<reason>`

## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

As mentioned, this is slightly different from `/KILL`, it doesn't display any sort of path, it doesn't say the user 
was `/KILL`'d, and it overrides the `/QUIT` prefix specified in your config file, so in effect, you could issue a 
command such as:

`/SAQUIT Craig :Ping timeout: 121 seconds`

which will appear to the network as the following:

`*** Craig has quit (Ping timeout: 121 seconds)`

As with other `SA*` commands, misuse of this command may be seen as abusive by network users. The reader is advised to 
be conservative in their usage.
