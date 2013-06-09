---
title: Modules &raquo; m_sanick
layout: default
---

## Description

**S**ervices **A**dministrator **Nick**. Forcibly changes a user's nickname.

## Configuration Tags

This module does not implement any configuration directives.

## Commands

`/SANICK <nick> <newnick>` ( **oper-only** )

Change the nickname of user `<nick>` to `<newnick>`

## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

Excessive abuse of this command, as with most IRCds and Service Administrator commands, can lead to collisions. 
**PLEASE USE CAUTION!**

Note, though, that because this command is designed for oper use, it will *not* cause desyncs on the network as `SVSNICK`
can on other ircds. **Always** use this oper form of the command if you wish to change a nickname. Also note that 
services and servers are still able to force nickchanges without this module being loaded. They use an internal 
server-to-server version of this command which is a part of the core (and is only usable by servers). 

As with other `SA*` commands, misuse of this command may be seen as abusive by network users. The reader is advised
to be conservative in their usage.
