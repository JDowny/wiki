---
title: Modules &raquo; m_abbreviation
layout: default
---

## Description

This module allows commands to be abbreviated using the syntax
`/BEGIN.` where `BEGIN` is the beginning of the command. For example,
the command `GLINE` could be used as `/gl.`, assuming no other
commands start with those same letters. 

## Configuration Tags

This module does not require any extra configuration, other than the
`<module>` tag to load it. 

## Commands

None, but allows existing commands to be abbreviated.

## User Modes

This module does not implement any user modes.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

If more than one command begins with the `BEGIN` text, a list of
matching commands will be given and no command will be executed.

This module will not allow abbreviation of aliases set by
[m_alias](/wiki/Modules/alias.html) as these are not actual
commands. If you wish to shorten an alias, make a shorter copy of that
alias.
