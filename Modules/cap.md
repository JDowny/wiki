---
title: Modules &raquo; m_cap
layout: default
---

## Description

This module implements the `CAP` capabilities extension as seen in many other IRC servers as a more sane replacement 
for `PROTOCTL` which also works before client registration. This module is required for `STARTTLS` support, `SASL` 
support, and adds extra facilities to other modules such as `NAMESX`.

## Configuration Tags

This module implements no configuration directives.

## Commands

See this [IETF draft](http://www.leeh.co.uk/draft-mitchell-irc-capabilities-02.html) for a 
developer's reference on `CAP`.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

As mentioned in the description, multiple Inspircd modules require [m_cap](cap.md) to function.
