---
title: Modules &raquo; m_connectban
layout: default
---

## Description

Provides per-IP connection throttling. Any IP that excessively connects within an hour is `z:line`'d, and their 
reconnect count resets to `0`. 

## Configuration Tags

`<connectban threshold="10" duration="10m" ipv4cidr="32" ipv6cidr="128">`

Attribute | Type | Description
--------- | ---- | -----------
duration | string | The duration of the `z:line`. Takes typical time formatting (i.e. `1y2w3d4m5s`).
ipv4cidr | int | The [CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing) range to use when counting connections. `32` is a single IP address.
ipv6cidr | int | The [CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing) range to use when counting connections. `128` is a single IP address.
threshold | int | The threshold of how many connections from the same IP to allow per hour before being zlined.

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

The `cidr` options are included to help with abusive ISPs.
