---
title: Modules &raquo; m_vhost
layout: default
---

## Description

Allows a server admin to define `<vhost>` tags in their configuration file which allow authenticated access to 
virtual hosts via username and password. 

## Configuration Tags

This module uses the following configuration tag:

`<vhost user="username" pass="password" host="this.is.the.vhost">`

One tag per vhost, with no limit on the number of tags. As always, large amounts of these tags can be placed in a 
seperate file and included with an `<include>` directive.

Any user (oper or not) issuing the `/VHOST` command and matching a given `<username>` and `<password>` pair will be given the 
vhost specified in the `<vhost>` tag. `<username>` and `<password>` may **not** contain spaces. `<host>` **must** 
be a valid hostname (only containing characters valid for a DNS name), but is **not** required to resolve.

## Commands

`/VHOST <username> <password>`

Attempt to authenticate for a vhost.

## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

None.
