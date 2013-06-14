---
title: Modules &raquo; m_serverban
layout: default
---

## Description

Gives channel operators the ability to ban users from a specific server, preventing them from joining the channel.

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
------- | ----------- | ---------
s | `s:<server>` | Bans all users from the matching server.

## Special Notes

It's worth noting that most modern networks will not have any practical use for this module, as federated IRC networks
are largely a thing of the past. These days most networks are run under central control. This module will likely only
be useful for networks run in a way similar to EFnet.
