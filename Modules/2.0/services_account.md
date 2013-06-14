---
title: Modules &raquo; m_services_account
layout: default
---

## Description

This module is designed to give several new modes for use with services packages. It varies from other IRCd 
implementations in that instead of representing identified users with umode `r`, it represents logged in users 
with an account name (`AC`), which is similar in operation to ircu based ircds such as asuka.

A services package which supports [m_services_account](services_account.md) ([Atheme](atheme.org), for example) may 
set an account name on a user, in which case that account name remains until they disconnect, or log out. 

## Configuration Tags

This module implements no configuration directives.

## Commands

This module implements no commands.

## User Modes

Mode | Oper-Only | Description
---- | --------- | -----------
R | No | User must be authenticated to a valid services account to `PRIVMSG` the user with `R` set.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

Mode | Format | Description
---- | ------ | -----------
M | `+M` | Users must be authenticated to a valid services account to `PRIVMSG` or `NOTICE` the channel.
R | `+R` | Users must be authetnicated to a valid services account to `JOIN` the channel.

## Extended Bans

Letter | Format | Description
------ | ------ | -----------
M | `M:<accountname>` | Users with the account name `<accountname>` cannot speak in channel.
R | `R:<accountname>` | Users with the account name `<accountname>` cannot `JOIN` the channel.
U	| `U:<nick!user@host>` | Unregistered users matching the mask `<nick!user@host>` cannot `JOIN` the channel. Registered users that match the mask may still `JOIN` the channel.

## Special Notes

This works in an identical manner to ircu, in that the account name stays with the user even if they change nicks, 
unlike the old m_services umode `r` which the server will remove if the user changes their nick.

When a user with an account name attached to them is `WHOIS`'d, the following numeric will be sent to represent their 
logged in status:

`:twisted.oscnet.org 330 w00t w00t w00t :is logged in as`

This is identical to ircu-based ircds.

For services packages to support this feature, they must send `METADATA` to the network of type `accountname` (See 
the [protocol docs](PLACEHOLDER)). Currently, only one package, [Atheme](atheme.org), supports this feature (NOTE: 
this writeup is several years old, has this change?).

### Additional Information

This adds the numeric `330` - `User is logged in as`

This adds the user state `IDENTIFIED`
