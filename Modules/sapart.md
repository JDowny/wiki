---
title: Modules &raquo; m_sapart
layout: default
---

## Description

**S**ervices **A**dministrator **Part**. Forcibly `/PART`s a user from a channel. 

Note that, unlike a `/KICK`, the user's client will not try to rejoin the channel, as it will respond to `/SAPART` 
the same as it would a user-issued `/PART`.


## Configuration Tags

This module does not implement any configuration directives.

## Commands

`/SAPART <nick> <channel>` ( **oper-only** )

Forces `<nick>` to part `<channel>`

## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

As with other `SA*` commands, misuse of this command may be seen as abusive by network users. The reader is advised
to be conservative in their usage.
