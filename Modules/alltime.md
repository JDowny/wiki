---
title: Modules &raquo; m_alltime
layout: default
---

## Description

Shows the time (with any delta, if applied) on all servers on the network. 

## Configuration Tags

This module implements no configuration directives.

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/ALLTIME` | Yes | N/A | Shows the time for every linked server on the network.


## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

Note that usage of this module if your network has more than one server is **highly** recommended, as many of
the most common problems with linked servers come from differing clocks. If the results returned by this command
are drastically different using [ntp](http://en.wikipedia.org/wiki/Network_Time_Protocol) or
[ntpdate](http://en.wikipedia.org/wiki/Ntpdate) to fix your server clocks is recommended. Please see your distro's
documentation for installation and usage of NTP.
