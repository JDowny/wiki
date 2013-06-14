---
title: Modules &raquo; m_uninvite
layout: default
---

## Description

Allows a user to rescind an `/INVITE` into a channel with `/UNINVITE`, instead of waiting for the invitee to `/JOIN`
and `/KICK`ing them.

## Configuration Tags

This module does not implement any configuration directives.

## Commands

`/UNINVITE <nick> <channel>`

Uninvite a user from a channel, same syntax as `/INVITE`.

## User Modes

This module does not implement any user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

The operation of `/UNINVITE` is identical to `/INVITE`, e.g., you can `/UNINVITE` anyone on a non +`i` channel, 
while you do not have ops (this is the **designed** behaviour of the module), however if the channel is +`i`, you 
require halfops (`h`) or higher to `/UNINVITE` a user. 
