---
title: Modules &raquo; m_md5
layout: default
---

## Description

This module is a service provider module, which means it has no real directly-usable functions of its own, however it 
provides an essential service which can be used by other modules. This module provides MD5 hashing facilities to other 
modules such as [m_cloaking](cloaking.md) and [m_oper_hash](oper_hash.md). 

## Configuration Tags

This module does not implement any configuration directives.

Provide thorough examples.

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

This module **must** be loaded before any modules which depend on it, otherwise they will be unable to find it. 
