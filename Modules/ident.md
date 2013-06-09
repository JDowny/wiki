---
title: Modules &raquo; m_[MODULE NAME]
layout: default
---

## Description

Allows [RFC 1413](http://www.ietf.org/rfc/rfc1413.txt) lookups on users connecting to your server. Without this module 
loaded no users are checked against identd.

Please see Special Notse about using ident in the modern internet.

## Configuration Tags

`<ident timeout="5">`

The timeout value is the number of seconds to wait for an ident response. This is a total waiting time, which is the 
combined time to connect, send the request, and retrieve the result and then close the socket, as all operations for 
ident are nonblocking to prevent disruption of service to the network.

`<connect useident="no">`

Adds the optional 'useident' config option to turn ident requests off for specific connect blocks in your config. 
The default if not specified is that ident requests will be carried out.

**Note**: This should *not* be a new tag, but instead added to your existing `<connect>` tag(s). 


## Commands

This module does not implement any commands.

## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

Ident lookups are provided through this module for compatibility only. It is **strongly** recommended that ident is not 
relied upon in the modern internet. For more information please see [this article](http://web.archive.org/web/20050828200336/http://www.clock.org/~fair/opinion/identd.html).
