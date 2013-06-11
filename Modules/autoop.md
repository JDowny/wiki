---
title: Modules &raquo; m_autoop
layout: default
---

## Description

Adds basic channel access controls with a new list mode. Functions similar to some services packages.

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
---- | ------ | -----------
w | `+w <q/a/o/h/v>:<nick!host@user>` | List mode that allows setting basic channel access privilegs using masks.

## Extended Bans

This module implements no extended bans.

## Special Notes

This is meant as a rudimentary implementation of IRCd-side services, and **will** conflict with some services packages
in some situations.

Example:

    channel op sets services flag SECURE on #foobar
    channel op sets +w o:luser!*@*
    luser joins channel
    autoop tries to op luser, services immediately deops luser
    
Using this module in combination with a services package is **not** recommended. You have been warned.
