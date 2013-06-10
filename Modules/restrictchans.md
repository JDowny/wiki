---
title: Modules &raquo; m_restrictchans
layout: default
---

## Description

Restricts channel creation to only opers. This is distrinct from channel **registration**; this module prevents
non-opers from joining (and thus creating) channels that do not already exist. Channel registration is provided
through a services package.

## Configuration Tags

You may allow specific channels to be created even by nonopers by using the following type of configuration tag:

`<allowchannel name="#channelone">`
`<allowchannel name="#channeltwo">`

Attribute | Type | Description
--------- | ---- | -----------
name | string | The name of the channel to allow users to create.

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

You probably **do not** want to load this module on a public network.
