---
title: Modules &raquo; m_inviteexception
layout: default
---

## Description

This module provides the `I` (Invite exception) channel list mode, which takes a `nick!ident@host` mask as its 
parameter, if you match an entry on a channel's `I` list then you can join the channel when it is +`i` (invite only), 
without being `/INVITE`'d. 

## Configuration Tags

This module does not implement any configuration directives.

## Commands

This module does not implement any commands.

## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Format | Description
------- | ----------- | ---------
I | `+I nick!user@host` | Allows users that match a mask on the list to bypass channel mode `i` without needing an `/INVITE`.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

Channel list mode refers to mode similar to +b, where you can set it multiple times on a single channel
(as long as you provide a unique hostmask to set)

Hosts match against the real host, IP and the fake host of the user joining (eg, if they have a fake vhost via /chghost)
