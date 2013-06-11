---
title: Modules &raquo; m_callerid
layout: default
---

## Description

Provides users with a way of controlling who `PRIVMSG`s them using a user mode and command.

## Configuration Tags

`<callerid maxaccepts="16" operoverride="no" tracknick="no" cooldown="60">`






Atribute | Type | Description
--------- | ---- | -----------
cooldown | int | Minimum number of seconds between users receiving notifications of private messages (not the actual message) from users not on their accept list. 
maxaccepts | int | The maximum number of nicks that can be on a user's accept list.
operoverride | bool | Controls whether opers (ALL opers) can send messages to users that have mode +g set and do not have the oper on the accept list.
tracknick | bool | Controls whether users that change their nick are tracked (remain on accept lists when changing nick).

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/ACCEPT <+/-><nick> [ <+/-><nick2> <+/-><nick3> etc. ]` | No | N/A | Tells the IRCd to allow/block `PRIVMSG`s from `<nick>`
`/ACCEPT <*>` | No | N/A | Shows your current `/ACCEPT` list.

See the [Special Notes](callerid.md#special-notes) for some usage examples.

## User Modes

Mode | Oper-Only | Description
---- | --------- | -----------
g | no | The user setting this mode must explicitly tell the IRCd to allow incoming `PRIVMSG`s using `/ACCEPT`, otherwise they will be blocked and the user will be informed that the user sending the `PRIVMSG` is attempting to `PRIVMSG` them.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

If this module is loaded, the `/ACCEPT` command can be used to manage an accept list even without having user mode `g` 
set, so that when setting user mode `g`, an accept list will already be in place. 

The `/ACCEPT` command can process more than one instruction in a single command. For example, using a command such 
as `/ACCEPT nick1, +nick2, *, -nick3, -nick4` would add `nick1` and `nick2` to your accept list, display your 
`/ACCEPT` list, and then remove `nick3` and `nick4` from your accept list. 
