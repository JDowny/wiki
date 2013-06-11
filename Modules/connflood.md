---
title: Modules &raquo; m_connflood
layout: default
---

## Description

This module adds support for connection throttling. Connects will be throttled once the connections per second 
goes over a given threshold value. 

## Configuration Tags

`<connflood seconds="30" maxconns="3" timeout="30" quitmsg="Throttled" bootwait="10">`

Attribute | Type | Description
--------- | ---- | -----------
bootwait | int | The amount of seconds to wait on booting before activating this module. This prevents the initial flood of clients on boot from accidentally triggering the module. 
maxconns | int | Amount of connections to accept before throttling occurs
quitmsg | string | The reason to use when quitting clients which have been throttled on connect
seconds | int | Amount of seconds to let the maxconns value build up for, before flushing it back to zero, so in effect 'maxconns' connections within 'seconds' seconds triggers throttling
timeout | int | The amount of time to throttle connections for, if and when throttling is triggered. The value of 'seconds' is added to this value before it is used.

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

This module monitors connections locally. For global protection of your network you must load this module on 
each server. For this reason, there are no settings for this module to detect netsplits as it will not attempt 
to throttle remote connections. 
