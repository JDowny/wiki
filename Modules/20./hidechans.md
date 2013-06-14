---
title: Modules &raquo; m_hidechans
layout: default
---

## Description

Provides a mode for opers to hide the channels they're in from non-opers when `/WHOIS`'d.

## Configuration Tags

This module does not implement any configuration directives.

## Commands

This module does not implement any commands.

## User Modes

Mode | Oper-Only | Description
---- | --------- | -----------
I | Yes | Hides the channels the user is in from non-opers on `/WHOIS`.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

This module is designed for use by network service bots, so that when users WHOIS the bot, huge channel lists are 
not sent to the user, however it can be used by non-opers and non-ulined clients simply as a privacy tool.
