---
title: Modules &raquo; m_check
layout: default
---

## Description

Allows opers to look up advanced information on channels, hostmasks or IP addresses, in 
a similar way to `WHO` but in more detail. 

## Configuration Tags

To use this command an oper must have `CHECK` specified in either their o:line's `<class:commands>` tag or 
the `<oper:commands>` tag.

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/CHECK <#channel>` | Yes | N/A | List all users upon a channel, the channel's modes, topics, the clone counts, and the privileges of all users upon that channel.
`/CHECK <hostmask>` | Yes | N/A | List all users and their clone counts matching the given hostmask.
`/CHECK <ip>` | Yes | N/A | List all users which share the given IP address, along with their clone counts.
`/CHECK <nick>` | Yes | N/A | Shows all the data for a specific user, including modes, logon time, what port they are connecting through, and what connection class they are using. 

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

This is designed to emulate the Asuka IRCd's `/CHECK` command, however there are a number of enhancements over their 
implementation in this module.
