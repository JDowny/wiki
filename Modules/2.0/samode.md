---
title: Modules &raquo; m_samode
layout: default
---

## Description

**S**ervices **A**dministrator **Mode**. Allows an oper to set modes on a channel without being a channel operator.

## Configuration Tags

To use this command an oper must have `SAMODE` specified in either their o:line's `<class:commands>` tag or the 
`<oper:commands>` tag.

## Commands

`/SAMODE <channel> <mode(s)> [parameters for modes]` ( **oper-only** )

Gives `<channel>` `<mode(s)>`

Examples:

* Set channel `#test` +`m`:
 * `/SAMODE #test +m`
* Set a ban on `lamer!*@*` in channel `#foo`:
 * `/SAMODE #foo +b lamer~*@*`
* Set an [Invite Exception](inviteexception.md) on `*!*@goodchanop` in channel `#bar`:
 * `/SAMODE #bar +I *!*@goodchanop`
* Remove mode `s` on channel `#baz`:
 * `/SAMODE #baz -s`
* Set modes +`i`, -`C` ([m_noctcp](noctcp.md)) and +`t` on channel `#private`:
 * `/SAMODE #private +it-C`


## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

Shows up as the server setting the mode:

`-> kenny.chatspike.net sets modes: +o-b Brain SnoFox!*@*`

As with other `SA*` commands, misuse of this command may be seen as abusive by network users. The reader is advised
to be conservative in their usage.
