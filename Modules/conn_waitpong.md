---
title: Modules &raquo; m_conn_waitpong
layout: default
---

## Description

Sends a `PING` message with a random string to every client which connects, the client must then reply with the correct 
`PONG` before it can connect.

## Configuration Tags

`<waitpong sendsnotice="yes" killonbadreply="no">`

Attribute | Type | Description
--------- | ---- | -----------
killonbadreply | bool | Whether or not to kill the client if it sends the wrong reply string. Otherwise we just ignore that `PONG`.
sendsnotice | bool | Send a server notice to users telling them to `/RAW PONG <randomstring>` if they cannot connect.

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

This is meant to prevent most common/simple bots from being able to connect to the IRCd. This should not break most 
popular cilents, though administrators should test this module before implementing it on a public network.
