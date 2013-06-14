---
title: Modules &raquo; m_denychans
layout: default
---

## Description

Allows you to specify channels which users, and optionally opers, cannot join.

## Configuration Tags

`<badchan name="#*opers*" allowopers="yes" reason="You're not an oper!" redirect="#lamers">`

Attribute | Type | Description
--------- | ---- | -----------
allowopers | bool | Whether or not the `<badchan>` directive should affect opers.
name | string | The channel to deny access to, wildcards permitted.
reason | string | The reason given when a user or unauthorised oper is denied joining the channel.
redirect | string | ( **optional** ) The channel to redirect a user or unauthorised oper when they attempt to join the forbidden channel. 


You may have as many <badchan> tags as you like. Using an `<include>` directive is suggested for large numbers
of `<badchan>` tags.

## Commands

This module implements no commands.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

**Note**: Denied channels are local, if you want a channel to be denied globally you **must** configure it on **all** servers. 
