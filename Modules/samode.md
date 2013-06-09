---
title: Modules &raquo; m_[MODULE NAME]
layout: default
---

## Description

**S**ervices **A**dministrator **Mode**. Allows an oper to set modes on a channel without being a channel operator.

## Configuration Tags

This module does not implement any configuration directives.

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

**Note**: Opers using this command in channels where they are not channel operators, without being asked, will likely
be considered abusive by the channel's users. Use with care.
