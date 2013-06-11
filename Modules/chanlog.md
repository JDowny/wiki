---
title: Modules &raquo; m_chanlog
layout: default
---

## Description

This module is used to send `SNOMASK` output to channels. It can be used to allow network staff to centrally 
monitor and discuss network activity.

## Configuration Tags

`<chanlog snomasks="AKkOoxfgJj" channel="#opers">`

Attribute | Type | Description
--------- | ---- | -----------
channel | string | The channel that you want the server notices sent to.
snomasks | string | The `SNOMASK`s that you want sent to the channel.

It's possible to have multiple `<chanlog>` tags to copy `SNOMASK`s to different channels.

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

None.
