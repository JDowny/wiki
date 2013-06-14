---
title: Modules &raquo; m_remove
layout: default
---

## Description	

This module allows channel ops (`o`, `h`) to forcepart users from a channel, the user leaves with a 
`Remove by [nick]: [message]` (appears as a `/PART`), and a server `NOTICE` is sent to the channel so you 
can distinguish people parting with artificial `Remove by [nick]` messages. The forceparted user also gets a 
server `NOTICE` telling them they were removed. 

## Configuration Tags

This moduel implements no configuration directives.

## Commands

`/REMOVE <nick> <channel> [message]`

Forceparts the user from the channel, requires halfops or higher.

`/FPART <channel> <nick> [message]`

This behaves identically to `/REMOVE`, the only difference is that
that `<channel>` and `<nick>` parameters are switched around to match
`/KICK`'s syntax. Also, `/REMOVE` is a builtin mIRC command which
caused trouble for some users. This feature was added in the 1.1
branch.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

When channel modes `haq` are enabled, then you may force part anyone with a equal or
lower 'level' than you, and if you are `a` or `q` you do not require
`o` to use `/REMOVE`. (Note that this is different from other channel op commands, as `aq` do not imply channel ops)

For example:

* UserA has modes `o`
* UserB has modes `oa` (effectively `a`)
* UserC has modes `v`
* UserD has modes `q`

In this example:

* UserA can only `/FPART` UserC as they are the only user with the same or lower level.
* UserB can `/FPART` UserA and UserC, UserB's `o` is ignored, as `a` is 'higher' than it.
* UserC can `/FPART` nobody, you must be at least a halfop (`h`) to `/FPART` a user.
* UserD can `/FPART` anyone on the channel, even though they don't have `o` or `a`.
