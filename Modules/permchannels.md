---
title: Modules &raquo; m_[MODULE NAME]
layout: default
---

## Description

Adds the ability to mark channels as 'permanent', meaning they will not be destroyed after the last user leaves.
Permanent channels will have their modes and topics preserved. [m_permchannels](permchannels.md) does NOT save
list modes (`bew`).

## Configuration Tags

You can optionally add a configuration parameter to this module to create certain channels on startup:

`<permchannels channel="#opers" modes="is" topic="Opers only.">`

Attribute | Type | Description
--------- | ---- | -----------
channel | string | The channel you want to create
modes | string | The modes you want the ircd to set on the channel when it's created (this includes oper-only channel modes)
topic | string | What you want the IRCd to set the topic to

`<permchanneldb filename="conf/permchannels.conf">`

Attribute | Type | Description
--------- | ---- | -----------
filename | string | Sets the location of the permchannels database file. As usual this is relative to the Inspircd `run` directory.

**Note**: While `<permchanneldb>` allows for channel topics and modes to be preserved through restarts, this does **not** preserve list modes (`bew`)!

## Commands

This module implements no commands.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Format | Description
------- | ----------- | ---------
P| `+P | Sets the `permanent` flag on a channel, meaning its information will be preserved even if no users are in it.

## Extended Bans

This module implements no extended bans.

## Special Notes

