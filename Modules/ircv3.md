
title: Modules &raquo; m_IRCv3
layout: default
---

## Description

The IRCv3 module provides the following IRCv3.1 extensions:
  `extended-join`, `away-notify` and `account-notify`.
These are optional enhancements to the client-to-server protocol. 

An extension is only active for a client when the client specifically requests it, so this module needs m_cap to work.
 
[Further information on these extensions can be found at the IRCv3 working group website](http://ircv3.atheme.org/)

## Configuration Tags

The following block can be used to control which extensions are enabled:

`<ircv3 accoutnotify="on" awaynotify="on" extendedjoin="on">`

## Commands

This module implements no commands.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extbans

This module implements no extended bans.

## Special Notes

### Requires

`m_cap.so`
