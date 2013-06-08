---
title: Modules &raquo; m_stripcolor
layout: default
---

## Description

Strips color codes used by clients such as KVIRC, mIRC, XChat, etc.

## Configuration Tags

This module does not implement any configuration directives.

## Commands

This module does not implement any commands.

## User Modes

Mode | Oper-Only | Description
---- | --------- | -----------
S | No | Strips color from all incoming `PRIVMSG`'s

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Format | Description
------- | ----------- | ---------
S | +S | Strips color from all channel messages.

## Extended Bans

This module does not implement any extended bans.

`or`

Letter | Format | Description
------- | ----------- | ---------
A | A:nick!user@host | A is for Apple. Delicious!
b | b:[seconds]:[pound] | b is for barbeque. Food.
B | B:account | B is for Bear. Oh shit!
C | C#foobar | C is for C'mon, Compile!!!

## Special Notes

None.
