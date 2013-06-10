---
title: Modules &raquo; m_[MODULE NAME]
layout: default
---

## Description

Describe the module here

## Configuration Tags

This module implements no configuration directives.

`or`

Ideally seperate module configuration and sub-tags added to pre-existing configuration directives. 
Provide thorough examples.

### Bears Configuration

Attribute | Type | Description
--------- | ---- | -----------
bears | bool | Are there bears? Choose wisely...
bearscream | string | What to scream at the bears when they come for you.
numbears | int | How many bears there are.

### Running From Bears

Attribute | Type | Description
--------- | ---- | -----------
run | bool | Will you run from the bears?
wheretorun | string | Where will you run to? Nowhere is safe.
runspeed | int | How fast can you run? A bear can hit 30mph flat-out...

## Commands

This module implements no commands.

`or`

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/BEARS <nick>` | Yes | N/A | Sends the bears to `<nick>`...
`/MAUL <channel> <nick>` | No | Yes | Publicly mauls `<nick>` in `<channel>`

## User Modes

This module implements no user modes.

`or`

Mode | Oper-Only | Description
---- | --------- | -----------
A | Yes | A is for Apple. Delicious!
b | No | b is for barbeque. Food.
B | Yes | B is for Bear. Oh shit!
C | Yes | C is for C'mon, Compile!!!

## SNOMASK

This module implements no server notice masks.

`or`

SNOMASK | Oper-Only | Description
------- | --------- | -----------
A | Yes | A is for Apple. Delicious!
b | No | b is for barbeque. Food.
B | Yes | B is for Bear. Oh shit!
C | Yes | C is for C'mon, Compile!!!

## Channel Modes

This module implements no channel modes.

`or`

Mode | Format | Description
------- | ----------- | ---------
A | `+A` | A is for Apple. Delicious!
b | `+b <seconds>:<pound>` | b is for barbeque. Food.
B | `+B <password>` | B is for Bear. Oh shit!
C | `+C <#foobar>` | C is for C'mon, Compile!!!

## Extended Bans

This module implements no extended bans.

`or`

Letter | Format | Description
------- | ----------- | ---------
A | `A:<nick!user@host>` | A is for Apple. Delicious!
b | `b:<seconds>:<pound>` | b is for barbeque. Food.
B | `B:<account>` | B is for Bear. Oh shit!
C | `C<#foobar>` | C is for C'mon, Compile!!!

## Special Notes

None.

`or`

Use this section to describe advanced|special usage, and/or provide tips and tricks.
