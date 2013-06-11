---
title: Modules &raquo; m_sslmodes
layout: default
---

## Description

Adds a channel mode that makes it so only users connected using SSL (either via GnuTLS or OpenSSL currently) 
may join the channel.

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
------- | ----------- | ---------
z | `+z` | Only users connected via SSL may join the channel.

## Extended Bans

This module implements no extended bans.

## Special Notes

You cannot set +`z` if there are any non-SSL users in the channel. `STARTTLS` **is** considered SSL for the purposes
of this module.
