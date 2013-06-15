---
title: Modules &raquo; m_cgiirc
layout: default
---

## Description

Allows for changing the hosts of `CGI:IRC` clients from trusted sources when they connect. 

## Configuration Tags

`<cgiirc opernotice="yes">`

Attribute | Type | Description
--------- | ---- | -----------
opernotice | bool | Should opers be sent notices containing extra information when a CGI:IRC client connects.

    <cgihost type="pass" mask="www.mysite.com">  
    <cgihost type="webirc" password="yourpass" mask="127.0.0.1">
    <cgihost type="ident" mask="otherbox.mysite.com">  
    <cgihost type="passfirst" mask="www.mysite.com">

Attribute | Type | Description
--------- | ---- | -----------
type | string | Indicates where the CGI:IRC module should get the client's real IP address from. [More information here](http://cgiirc.org/docs/)
password | string | If the `type` is `webirc`, you must set a password for the webirc client to send to the IRCd to authenticate itself before it can change user IPs
mask | string | The IP or host to accept the CGI:IRC connection from

Note that each CGI:IRC instance must have a `<cgihost>` tag.

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

Note that this module will usually initiate a second DNS lookup for each user connecting from `CGI:IRC`. This 
should not cause too much of a performance loss, however if this increases resource usage more than you would 
like, it is recommended you do not use this module.

Also, if you are using other modules which are setting hosts, like [m_conn_umodes](conn_umodes.md) (`x` for cloak) 
or [m_hostchange](hostchange.md) you might want to arrange the load order of these modules according to your needs. 
