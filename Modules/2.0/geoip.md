---
title: Modules &raquo; m_geoip
layout: default
---

## Description

Describe the module here

## Configuration Tags

The actual allow/ban actions are done by connect classes, **not** by the GeoIP module. An complete example connect 
class banning people from russia or turkey:

`<connect deny="*" geoip="TR,RU">`

As usual `<connect>` tags denying specific users or connections **must** go **before** the general allow-all `<connect>`
tags

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

**This module is an 'extra' module. This means that by default it is not compiled when you type make to build your IRCd.**
To enable this module follow [these](installation#extras) steps.

### Requires

[The GeoIP database](http://www.maxmind.com/)

Note that on most GNU/Linux distributions this can be installed with your package manager. Check your distribution's
documentation for more information.
