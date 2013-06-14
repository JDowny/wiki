---
title: Modules &raquo; m_nicklock
layout: default
---

## Description

Forcibly changes a user's nickname, and locks the new nickname (cannot be changed by the user) until the user quits IRC.

## Configuration Tags

To use these commands an oper must have `NICKLOCK` and/or `NICKUNLOCK` specified in either their o:line's 
`<class:commands>` tag or the `<oper:commands>` tag to use the respective commands.

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/NICKLOCK <nick> <newnick>` | Yes | N/A | Changes the nickname of user `<nick>` to `<newnick>`. `<newnick>` is locked, meaning the user cannot change it themselves. This lasts until the user quits IRC.
`/NICKUNLOCK <nick>` | Yes | N/A | Unlocks the nickname of `<nick>`

### Examples: 

* Change and lock the nickname of `luser` to `lamer`:
 * `/NICKLOCK luser lamer`
* Unlock the nickname of user `lamer` (formerly `luser`):
 * `/NICKUNLOCK lamer`

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

If you attempt to change the nickname of a user who is already locked, for example using `/SANICK` or, if you manage to 
somehow issue a second `/NICKLOCK` (this should not be possible unless something is **very** messed up!), 
there will be a nickname collision as the module will deny its own nickchange. The nickname collision is there to 
prevent loops and desyncs. **Be both careful and conservative with your use of this command!**
