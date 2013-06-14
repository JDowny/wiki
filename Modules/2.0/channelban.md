---
title: Modules &raquo; m_channelban
layout: default
---

## Description

Allows a channel operator to block a user from their channel if the user trying to join is in another channel specified
in the extended ban.

## Configuration Tags

This module implements no configuration directives.

## Commands

This module implements no commands.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

Letter | Format | Description
------ | ------ | -----------
j | `j:<#channel>` | If a joining user is in `<#channel>` they won't be able to join the channel the extban is set on.

Examples:

* Block users from `#foo` from joining `#bar`:
 * `/MODE #bar +b j:#foo`

## Special Notes

None.
