---
title: Modules &raquo; m_permchannels
layout: default
---

## Description

Adds the ability to mark channels as 'permanent', meaning they will not be destroyed after the last user leaves.
Permanent channels will have their modes and topics preserved.

## Configuration Tags

Only opers with the `channels:set-permanent` privilege in their oper `<class>` can set channels as `P`.

You can add configuration parameters to this module to create channels on startup. This is **not** required, however,
and channel mode `P` can be added to a channel while the IRCd is running. Note that if the IRCd is restarted, unless
`<perchanneldb>` is being used, channels that `P` is set on will **not** be preserved.

`<permchannels channel="#opers" modes="iPs" topic="Opers only.">`

Attribute | Type | Description
--------- | ---- | -----------
channel | string | The channel you want to create
modes | string | The modes you want the ircd to set on the channel when it's created (this includes oper-only channel modes)<sup>1</sup>
topic | string | What you want the IRCd to set the topic to

1) Note that if you don't set `P` on a channel in a `<permchannels>` tag, though the channel will be created on startup,
it will **not** be preserved after the last user leaves it.

`<permchanneldb filename="conf/permchannels.conf">`

Attribute | Type | Description
--------- | ---- | -----------
filename | string | Sets the location of the permchannels database file. As usual this is relative to the Inspircd `run` directory.<sup>1</sup>

1) **This file must exist before Inspircd is run if it is included!!!** You can create it in most GNU/Linux distributions with `touch [path to inspircd run directory]/conf/permchannels.conf`

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
P<sup>1</sup> | `+P` | Sets the `permanent` flag on a channel, meaning its information will be preserved even if no users are in it.

1) Note that this channel mode is **oper-only**.

## Extended Bans

This module implements no extended bans.

## Special Notes

Channels with the `P` mode will remain open even after everyone else has left the channel, and 
therefore keep things like modes, ban lists and topic (once again, this does **not** hold true for restarts! 
list modes (`bew`) **WILL** be lost!). Permanent channels -may- need support from your Services package to function properly 
with them. 
