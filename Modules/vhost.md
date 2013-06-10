---
title: Modules &raquo; m_vhost
layout: default
---

## Description

Allows a server admin to define `<vhost>` tags in their configuration file which allow authenticated access to 
virtual hosts via username and password. 

## Configuration Tags

To use this module you must add the following tags to your Configuration file:

`<vhost user="username" pass="password" host="this.is.the.vhost">`

If a user issues the `/VHOST` command and matches any given username and password pair, they will be given the 
vhost specified in the `<vhost>` tag. `<username>` and `<password>` may **not** contain spaces and the host must 
be a valid hostname (only containing characters valid for a DNS name), but is not required to resolve.

Provide thorough examples.

## Commands

`/VHOST <username> <password>`

Attempt to authenticate for a vhost, as specified by the server admin. 

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
