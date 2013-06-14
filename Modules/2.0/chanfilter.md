---
title: Modules &raquo; m_chanfilter
layout: default
---

## Description

This module provides a channel list mode which allows channel operators to choose words to filter from their channel.
If any user (including channel ops) sends a line matching the wildcard pattern to the channel, the server will 
filter out their line, sending them the following message: 

`#foobar Your message contained a censored word, and was blocked`

This mode is distinct from channel mode `G` in that the channel operator specifies the pattern to block.

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
---- | ------ | -----------
g | `+g <wildcard pattern to block` | List mode which allows a channel operator to specify a pattern that will block matching messages from being sent to the channel.

Examples:

* Block any message containing `foo` from `#testing`:
 * `/MODE #testing +g *foo*`
* Block any messages beginning with `bar` from `#baz`:
 * `/MODE #baz +g bar*`
* Delete block on `foo` from `#testing`:
 * `/MODE #testing -g *foo*`

## Extended Bans

This module implements no extended bans.

## Special Notes

Note that some clients can be easily confused by modes such as this as they do not read the `005` numeric 
correctly and know how many parameters to accept. If you are unsure of wether your client is able to deal with 
this mode, never set them along with other modes in the same line such as `o` or `b`. 

### Performance

**WARNING**: It is theoretically possible for a malicious channel operator to set a large amount of `g` patterns in
a large channel and impact server performance. Administrators with large networks are advised to use **caution** in
implementing this module.
