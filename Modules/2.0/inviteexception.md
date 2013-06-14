---
title: Modules &raquo; m_inviteexception
layout: default
---

## Description

This module provides the `I` (Invite exception) channel list mode, which takes a `nick!ident@host` mask as its 
parameter, if you match an entry on a channel's `I` list then you can join the channel when it is +`i` (invite only), 
without being `/INVITE`'d. 

## Configuration Tags

This module implements no configuration directives.

## Commands

This module implements no commands.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Format | Description
------- | ----------- | ---------
I | `+I nick!user@host` | Allows users that match a mask on the list to bypass channel mode `i` without needing an `/INVITE`.

## Extended Bans

This module implements no extended bans.

## Special Notes

Channel list mode refers to a mode type similar to +`b`, where you can set it multiple times on a single channel
(as long as you provide unique parameters for each instance).

Hosts match against the real host, IP and the vhost of the user joining (i.e. if they have a vhost set via `/CHGHOST`)
