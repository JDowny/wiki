---
title: Modules &raquo; m_nonicks
layout: default
---

## Description	

Allows a channel operator to disallow nickname changes in their channel.

## Configuration Tags

This module does not require any extra configuration, beyond the `<module>` tag to load it.

## Commands

This module implements no commands.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Format | Description
------- | ----------- | ---------
N | `+N` | Disallow nickname changes on the channel.

## Extended Bans

Letter | Format | Description
------- | ----------- | ---------
N | `N:<nick!user@host>` | Disallows any user matching the mask from changing their nick.

Examples: 

* Disallow `lamer!*@*` from changing nicknames on `#foo`:
 * `/MODE #foo +b N:lamer!*@*`
* Disallow `*!*@crappy.ISP.*` from changing nicknames on `#bar`:
 * `/MODE #bar +b N:*!*@crappy.ISP.*`

## Special Notes

If a user attempts a nick change in a channel where `N` is set, the user will receive the following message:

`Can't change nickname while on *[#channel]* (+N is set)`
