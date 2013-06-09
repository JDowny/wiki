---
title: Modules &raquo; m_blockcolor
layout: default
---

## Description

This module allows blocking any messages containing color-codes sent to a channel. This differs from [m_stripcolor](wiki/Modules/stripcolor.md)
in that this fully blocks any message containing color codes from being sent to the channel, while [m_stripcolor](wiki/Modules/stripcolor.md)
merely removes the color-codes from the message before passing it to the channel.

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
c | `+c` | Blocks any message containing color from being sent to the channel.

## Extended Bans

Letter | Format | Description
------- | ----------- | ---------
c | `c:nick!user@host` | Blocks any message containing color from users matching the mask from being sent to the channel.

## Special Notes

The actual numeric sent when messages are blocked is the numeric `404`. This is the same numeric used for `Cannot send 
to this channel` although the string is different so many clients will display it correctly, the ones that do not will 
still react in an appropriate manner. 
