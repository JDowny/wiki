---
title: Modules &raquo; m_censor
layout: default
---

## Description

Allows filtering of text from private and channel messages and notices, based on a set of patterns defined in the 
Configuration files. Unlike [m_filter](filter.md), this module is designed for users to control their channels 
where [m_filter](filter.md) is designed for admins to control entire IRC servers. 

## Configuration Tags

<badword text="ass" replace="buns">
<badword text="shit" replace="poo">
<badword text="bitch" replace="bich">
<badword text="fuck" replace="m'kay">

Attribute | Type | Description
--------- | ---- | -----------
text | string | The bad text to find and replace
replace | string | The text to substitute when bad text is found.

The patterns used are straight search and replace operations which match against any `PRIVMSG` or `NOTICE` command 
from oper and user alike (no exceptions) to the channel or user that has mode `G` set upon it. The text 
given will be replaced, and replacement does not diffrentiate between word boundaries, e.g. the example given 
above would replace `shitake mushrooms` with `pooake mushrooms`. You have been warned! 


## Commands

This module implements no commands.

## User Modes

Mode | Oper-Only | Description
---- | --------- | -----------
G | No | Activates the configured text filters on the messages a user receives.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Format | Description
---- | ------ | -----------
G | `+G` | Activates the configured text filters on a channel.

## Extended Bans

This module implements no extended bans.

## Special Notes

### Performance

Please note that search and replace operations are faster to match than regular expressions (such as those used 
in unrealircd, etc), however a large number (e.g. a hundred or more) of them can still impede performance. In 
addition, the more users you have, the less patterns you will be able to have without crippling your irc server. 
Filtering is always done locally, so if you have 2000+ users per server, consider other alternatives where possible. 
