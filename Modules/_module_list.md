---
title: Modules &raquo; module_list
layout: default
---

# List of all official Inspircd 2.0 modules

Module Name | User Modes | Channel Modes | extbans | SNOMASKs | Commands | Description
----------- | ---------- | ------------- | ------------- | -------- | -------- | -----------
[m_abbreviation](abbreviation.md) | - | - | - | - | - | Allows commands to be abbreviated
[m_alias](alias.md) | - | - | - | - | - | Allows aliasing commands to other commands. (i.e. `/NS` to `/PRIVMSG NICKSERV`
[m_allowinvite](allowinvite.md) | - | `A` | `A` | - | - | Allows commands to be abbreviated
[m_alltime](alltime.md) | - | - | - | - | `ALLTIME` | Shows [Epoch time](http://en.wikipedia.org/wiki/Unix_time) for every server on the network
[m_auditorium](auditorium.md) | - | `u` | - | - | - | Allows for "Auditorium" channels, where the only visible user is yourself (useful for mass conferencing)
[m_autoop](autoop.md) | - | `w` | - | - | - | Provides a list mode that allows for simple channel access lists
[m_banexception](banexception.md) | - | - | - | - | - | Provides a list mode that allows ops to exempt `nick!user@host` masks for existing bans
[m_banredirect](banredirect.md) | - | - | `#channel` | - | - | Allows bans to redirect users to another channel
[m_blockamsg](blockamsg.md) | - | - | - | - | - | Blocks usage of `AMSG` and `AME`
[m_blockcaps](blockcaps.md) | - | `B` | `B` | - | - | Blocks all caps messages to a channel
[m_blockcolor](blockcolor.md) | - | `c` | `c` | - | - | Block messages to a channel containing color control codes
[m_botmode](botmode.md) | `B` | - | - | - | - | Provides a mode to mark a user as a bot in `WHOIS`
[m_callerid](callerid.md) | `g` | - | - | - | `ACCEPT` | Allows a user whitelist-based control over who can `PRIVMSG` them
[m_cap](cap.md) | - | - | - | - | `CAP` | Implements the `CAP` capabilities extension
[m_cban](cban.md) | - | - | - | - | `CBAN` | Lets opers disallow channels on the network
[m_censor](censor.md) | `G` | `G` | - | - | - | Provides network-wide censoring of words/patterns via a user/channel mode
[m_cgiirc](cgiirc.md) | - | - | - | - | - | Adds support for CGI-IRC automatic host changing on connect
[m_chancreate](chancreate.md) | - | - | - | `jJ` | - | Adds an oper SNOMASK that logs channel creation
[m_chanfilter](chanfilter.md) | - | `g` | - | - | - | Provides an equivalent to `G` ([m_censor](censor.md)) wher instead channel operators choose the word list
[m_chanhistory](chanhistory.md) | - | `H` | - | - | - | Provides a configurable amount of channel history to newly joining users
[m_chanlog](chanlog.md) | - | - | - | - | - | Allows SNOMASKs to be sent to a channel
[m_channames](channames.md) | - | - | - | - | - | Implements config tags which allow changing characters allowed in channel names
[m_channelban](channelban.md) | - | - | `j` | - | - | EXtban that will prevent a user from joining a channel if they're in a specified second channel.
[m_chanprotect](chanprotect.md) | - | `qa` | - | - | - | ( **DEPRECATED** ) Adds support for channel 'owners' and 'protected' ops
[m_check](check.md) | - | - | - | - | `CHECK` | Provides a tool to lookup user, channel or host information
[m_chghost](chghost.md) | - | - | - | - | `CHGHOST` | Oper command which can change the host of any connected user
[m_chgident](chgident.md) | - | - | - | - | `CHGIDENT` | Oper command which can change the ident of any connected user
[m_chgname](chgname.md) | - | - | - | - | `CHGNAME` | Oper command which can change the name (`GECOS`) of any connected user
[m_cloaking](cloaking.md) | `x` | - | - | - | - | Provides a method for making hostnames private
[m_clones](clones.md) | - | - | - | - | `CLONES` | Oper command providing a list of users above a certain number of connections
[m_close](close.md) | - | - | - | - | `CLOSE` | Oper command allowing incomplete new connections to be closed
[m_commonchans](commonchans.md) | `c` | - | - | - | - | User mode requiring a user to share a channel with the client `c` is set on to `PRIVMSG` them
[m_conn_join](conn_join.md) | - | - | - | - | - | Forces users to join one or more channels on connection
[m_conn_umodes](conn_umodes.md) | - | - | - | - | - | Sets or removes user modes from clients on connect
[m_conn_waitpong](conn_waitpong.md) | - | - | - | - | - | Requires clients to send a matching `PONG` to a server `PING` containing a random string before they can finish connecting
[m_connectban](connectban.md) | - | - | - | - | - | Provides per-IP connection throttling
[m_connflood](connflood.md) | - | - | - | - | - | Throttles connections if server is connect-flooded
[m_customprefix](customprefix.md) | - | - | - | - | - | Allows configuring channel user modes with custom prefixes and ranks
[m_customtitle](customtitle.md) | - | - | - | - | `TITLE` | Adds a command to auth for a vanity `SWHOIS` line as well as a vhost. Config defined
[m_cycle](cycle.md) | - | - | - | - | `CYCLE` | `PART`s and `JOIN`s a channel, bypassing any modes blocking new `JOIN`s
[m_dccallow](dccallow.md) | - | - | - | - | `DCCALLOW` | Adds the `DCCALLOW` command and configuration options to block files with wildcard masks
[m_deaf](deaf.md) | `d` | - | - | - | - | Adds a user mode to stop receipt of channel messages
[m_delayjoin](delayjoin.md) | - | `D` | - | - | - | Users will not appear in the channel until they speak
[m_delaymsg](delaymsg.md) | - | `d` | - | - | - | Users cannot message the channel until a set number of seconds have elapsed
[m_denychans](denychans.md) | - | - | - | - | - | Blocks users from using config-defined channels
[m_devoice](devoice.md) | - | - | - | - | `DEVOICE` | Allows users to devoice themselves in a channel
[m_dnsbl](dnsbl.md) | - | - | - | - | - | Provides DNS-blacklist lookups on connecting users
[m_exemptchanops](exemptchanops.md) | - | - | - | - | - | Allows channels to exempt user levels from different modes
[m_filter](filter.md) | - | - | - | - | `FILTER` | Advanced message-filtering for spam/virus protection
[m_gecosban](gecosban.md) | - | - | `r` | - | - | Adds an extban for user real names
[m_geoip](geoip.md) | - | - | - | - | - | Allows blocking connections according to country codes (~98% accuracy)
[m_globalload](globalload.md) | - | - | - | - | `GLOADMODULE` `GUNLOADMODULE` `GRELOADMODULE` | Opers can load or unload Inspircd modules network-wide
[m_globops](globops.md) | - | - | - | `g` | `GLOBOPS` | Opers can mass-message all users with SNOMASK `g`
[m_halfop](halfop.md) | - | `h` | - | - | - | Provides channel half-operators ( **DEPRECATED** )

[](.md) | - | - | - | - | - | 
# List of all unofficial Inspircd 2.0 modules
