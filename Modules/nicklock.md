---
title: Modules &raquo; m_nicklock
layout: default
---

## Description

Forcibly changes a user's nickname, and locks the new nickname (cannot be changed by the user) until the user quits IRC.

## Configuration Tags

This module does not implement any configuration directives.

## Commands

* `/NICKLOCK <nick> <newnick>`
 * Changes the nickname of user `<nick>` to `<newnick>`. `<newnick>` is locked, meaning the user cannot change it themselves. This lasts until the user quits IRC.
* `/NICKUNLOCK <nick>`
 * Unlocks the nickname of `<nick>`.

### Examples: 

* Change and lock the nickname of `luser` to `lamer`:
 * `/NICKLOCK luser lamer`
* Unlock the nickname of user `lamer` (formerly `luser`):
 * `/NICKUNLOCK lamer`

## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

If you attempt to change the nickname of a user who is already locked, for example using `/SANICK` or, if you manage to 
somehow issue a second `/NICKLOCK` (this should not be possible unless something is **very** messed up!), 
there will be a nickname collision as the module will deny its own nickchange. The nickname collision is there to 
prevent loops and desyncs. **Be both careful and conservative with your use of this command!**
