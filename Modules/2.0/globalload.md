---
title: Modules &raquo; m_[MODULE NAME]
layout: default
---

## Description

Provides opers with commands to load and unload modules network-wide.

## Configuration Tags

This module implements no configuration directives.

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/GLOADMODULE <filename.so> [server mask]` | Yes | N/A | Load a new module globally (network-wide) or on a specific server.
`/GUNLOADMODULE <filename.so> [server mask]` | Yes | N/A | Unload a module globally (network-wide) or on a specific server.
`/GRELOADMODULE <filename.so> [server mask]` | Yes | N/A | Unload and reload a module globally (network-wide) or on a specific server. 

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

**Be very careful with this command.** It is designed to allow easy loading and unload of modules which 
implement modes and commands, network-wide,or on specific servers without causing a desync. However, this module 
can be very easily abused, or used to cripple your network. Be sure you trust whoever you grant access to 
these commands! 
