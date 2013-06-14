---
title: Modules &raquo; m_passforward
layout: default
---

## Description

This module allows automatic identification to the Nickname management service on the IRC network. It works by 
taking the `PASS` command sent on connection, and forwarding the `PASS` given to the Nickname service. 

## Configuration Tags

    <passforward
    nick="NickServ"
    forwardmsg="NOTICE $nick :*** Forwarding PASS to $nickrequired"
    cmd="PRIVMSG $nickrequired :IDENTIFY $pass">

Attribute | Type | Description
--------- | ---- | -----------
nick | string | The nickname of the services client to forward `PASS` to.
forwardmsg | string | The message to send to users when we forward their password to Nickserv. `$nick` is the nickname of the connecting user, `$nickrequired` is the same as `nick`; the services client we're forwarding the login information to.
cmd | string | The format Nickserv needs the authentication string in. `$nickrequired` is the same as `nick`; the services client we're sending the login information to.

## Commands

This module implements no commands.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

None.
