---
title: Modules &raquo; m_chanprotect
layout: default
---

## Description

Provides channel modes `q` and `a` (founder and protection) and optionally the 'prefixes' that come with them on the
channel.

**Please note** that m_chanprotect is **deprecated** and will be phased out in future versions in favor of 
[m_customprefix](customprefix.md)

## Configuration Tags

    <chanprotect noservices="no"
    deprotectself="no"
    deprotectothers="no"
    qprefix="~"
    aprefix="&">

`noservices`

If your network does not have services and is unlikely to ever have services, then set `noservices` to `yes` in your 
`chanprotect` tag. When this option is set the first person into any channel is silently given the channel mode `q` in 
the same way they are given the channel mode `o` for channel operator status. This is because otherwise with no U:Lined 
servers to give out `q`, both `q` and `a` would be useless.

`deprotectself`

If `deprotectself` is `yes`, any user with `q` or `a` may remove the `q` or `a` from themselves. The default 
setting is `no`, which stops even the founder taking away their founder status without using 
services.

`deprotectothers`

If `deprotectothers` is `yes`, any user with `q` or `a` may remove `q` or `a` from other users. The default setting
is to not enable this feature, so that only `q` may remove `a`, and nothing but services may remove `q`.

`qprefix`

Allows configuration of which character to use for the `q` prefix on channels. If no prefix is specified, this mode has 
no prefix. Remember that this is only cosmetic, and the `q` channel mode does **not** confer channel operator status, 
meaning that channel mode `o` (or `h` if `m_halfop` is enabled) must also be set on the user for them to be able to 
perform `/KICK`, place bans, etc.

`aprefix`

Allows configuration of which character to use for the `a` prefix on channels. If no prefix is specified, this mode has 
no prefix. Remember that this is only cosmetic, and the `a` channel mode does **not** confer channel operator status, 
meaning that channel mode `o` (or `h` if `m_halfop` is enabled) must also be set on the user for them to be able to 
perform `/KICK`, place bans, etc.

## Commands

This module does not implement any commands.

## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Format | Description
------- | ----------- | ---------
q | `+q nickname` | Marks a user as channel founder. Cannot be `/KICK`'d, de-op'd or de-protect'd except by services.
a | `+a nickname` | Marks a user as protected. Cannot be `/KICK`'d or de-op'd except by founders. Cannot be de-protect'd
except by founders or services.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

Note that channel modes `q` and `a` **do** infer channel mode `o`, meaning that a user who is either +`a` or +`q` 
has **all the privileges of** +`o`.

Any changes made to the above configuration options requires a reload of the module (unload, then load again) to take 
effect. 
