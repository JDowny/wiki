---
title: Modules &raquo; m_namesx
layout: default
---

## Description

This module extends the `NAMES` command to implement the `NAMESX` protocol enhancements (See the special notes 
section below for implementation details useful to client developers). 

## Configuration Tags

This module implements no configuration directives.

## Commands

Extends the `NAMES` command to provide multi-prefix support. See the special notes below. 

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

Listed here are the technical details of the NAMESX protocol extensions. The original text (cite codemastr) can 
be read on the forums for the klient IRC client.

"This is something we toyed around with [...] and never really implemented because we couldn't muster up 
client support. However, for some reason, x-chat 2.60 and mIRC 6.17 decided to add support for our spec even 
though we never even implemented it and to my knowledge no other server implements it. [...] it solves the 
long standing mode desync issue in IRC illustrated as follows:

User1 joins
User1 is set +ov
User2 joins, sees @User1 in nick list
User1 sets -o 

From `User1`'s perspective, it is `+User1`. However, `User2` is unaware that `User1` is voiced (the `NAMES` only 
showed `@User1`), so his nicklist just says `User1`.

The solution is to send all prefixes in `NAMES`, so it would show `@+User1`. Naturally, that would break 
clients that don't support it. To deal with this, there is a `005` token called `NAMESX`. This indicates that 
the server is capable of sending multiple prefixes. But we also need to know the client understands this. So to 
do this, upon receiving a `005` token of `NAMESX` the client sends back:

`PROTOCTL NAMESX`

This tells the server that the client supports this feature and hence the extended `NAMES` reply will be used. 
If `PROTOCTL NAMESX` is not received, the server will just use the normal system. [...]

mIRC also does the same thing for `005 UHNAMES` (and `PROTOCTL UHNAMES`) to indicate that it supports `n!u@h` in 
a `NAMES` reply. The idea is to eliminate the `WHO` request that clients send when first joining channels. As of yet, I 
know of no servers implementing this feature."

Obviously, the part about knowing no servers implementing this feature is now invalid, as multiple servers 
support `NAMESX`. 
