---
title: Modules &raquo; m_exemptchanops
layout: default
---

## Description

Allows a channel operator to exempt users from different channel modes based on channel privilege level.

## Configuration Tags

This module implements no configuration directives.

## Commands

This module implements no commands.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Format | Description
---- | ------ | -----------
X | `+X <permission>:<mode>`<sup>1</sup> | A list of channel exemptions and their required rank.

1) Mode is one of the prefix modes (like `qaohv`). Note that if you're using [m_customprefixes](customprefixes.md)
and have non-standard prefix modes, you would use the letters you've set in [m_customprefixes](customprefixes.md)
when setting channel mode `X`

### exemptchanops permissions

The following is a list of permissions that [m_exemptchanops](exemptchanops.md) can modify:

Permission | Module Required | Description
---------- | --------------- | -----------
topiclock | N/A | Permission required to change the topic if channel mode `t` is set.
auditorium-vis | [m_auditorium](auditorium.md) | Permission required to be visible in a channel with mode `u`
auditorium-see | [m_auditorium](auditorium.md) | Permission required to see full user list of a channel with mode `u`
blockcaps | [m_blockcaps](blockcaps.md) | Permission required to bypass channel mode `B`
blockcolor | [m_blockcolor](blockcolor.md) | Permission required to bypass channel mode `c`
censor | [m_censor](censor.md) | Permission required to bypass channel mode `G`
filter | [m_chanfilter](chanfilter.md) | Permission required to bypass channel mode `g`
flood | 
nickflood | [m_nickflood](nickflood.md) | Permission required to bypass channel mode `F`
noctcp | [m_noctcp](noctcp.md) | Permission required to bypass channel mode `C`
nonick | [m_nonicks](nonicks.md) | Permission required to bypass channel mode `N`
nonotice | [m_nonotice](nonotice.md) | Permission required to bypass channel mode `T`
regmoderated | [m_services_account](services_account.md) | Permission required to bypass channel mode `M`
stripcolor | [m_stripcolor](stripcolor.md) | Permission required to bypass channel mode channel mode `S`

## Extended Bans

This module implements no extended bans.

## Special Notes

None.
