---
title: Modules &raquo; m_setname
layout: default
---

## Description

This module allows users to modify their GECOS whilst connected to IRC. 

## Configuration Tags

This module implements no configuration directives.

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/SETNAME <name>` | No | N/A | Changes the issuer's GECOS to `<name>`

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

Note: While other `/SET*` commands are oper-only, this one is not. Any user can use `/SETNAME` if the module is loaded.
