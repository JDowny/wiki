---
title: Modules &raquo; m_blockcaps
layout: default
---

## Description

Provides a channel mode to block messages in ALL CAPS sent to the channel.

## Configuration Tags

`<blockcaps percent="50" minlen="5" capsmap="ABCDEFGHIJKLMNOPQRSTUVWXYZ! ">`

Attribute | Type | Description
--------- | ---- | -----------
capsmap | string | A list of chars to be considered CAPS, this was you can add CAPS for your language. Also you can add things like ! and space to further lock down on caps usage.
minlen | int | The minimum length (in characters) a line must be for the line to be considered for blocking.
percent | int | What percentage of the message must be caps before the message will be blocked.

## Commands

This module implements no commands.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Format | Description
---- | ------ | -----------
B | `+B` | Blocks messages IN ALL CAPS sent to the channel.

## Extended Bans

Letter | Format | Description
------ | ------ | -----------
B | `B:<nick!user@host>` | Blocks messages IN ALL CAPS from users that match the mask.

## Special Notes

The actual numeric sent when messages are blocked is the numeric `404`. This is the same numeric used for 
`Cannot send to this channel` although the string is different so many clients will display it correctly, the
ones that do not will still react in an appropriate manner. 
