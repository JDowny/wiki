---
title: Modules &raquo; module_list
layout: default
---

# List of all official Inspircd 2.0 modules

Module Name | umode | cmode | extban | SNOMASK | Commands | Description
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
[m_halfop](halfop.md) | - | `h` | - | - | - | ( **DEPRECATED** ) Provides channel half-operators
[m_helpop](.md) | `h` | - | - | - | `HELPOP` | Provides a help system, defined through config directives
[m_hidechans](hidechans.md) | `I` | - | - | - | - | Hides the channels a user is in
[m_hideoper](hideoper.md) | `H` | - | - | - | - | Opers can hide their operator status
[m_hostchange](hostchange.md) | - | - | - | - | - | Provides a different style of host-cloaking than [m_cloaking](cloaking.md)
[m_httpd](httpd.md) | - | - | - | - | - | Provides a local HTTP server for hosting XML/HTML status reports. Useful with other modules
[m_httpd_acl](httpd_acl.md) | - | - | - | - | - | Provides access control lists to [m_httpd](httpd.md) and other modules that depend upon it.
[m_httpd_config](httpd_config.md) | - | - | - | - | - | Provides a method to view server config via HTTP
[m_httpd_stats](httpd_stats.md) | - | - | - | - | - | Provides basic server stats via [m_httpd](httpd.md)
[m_ident](ident.md) | - | - | - | - | - | Provides traditional `IDENT` ([RFC 1413](http://tools.ietf.org/html/rfc1413) lookups on connecting users.
[m_inviteexception](inviteexception.md) | - | `I` | - | - | - | Provides a channel list mode to exempt masks from needing an `INVITE` to join a channel
[m_joinflood](joinflood.md) | - | `j` | - | - | - | Provides a channel mode to limit `JOIN` rate
[m_jumpserver](jumpserver.md) | - | - | - | - | `JUMPSERVER` | Oper command implementing the `JUMPSERVER` mechanism through the `RPL_REDIR` numeric
[m_kicknorejoin](kicknorejoin.md) | - | `J` | - | - | - | Provides a channel mode to block "auto-rejoin on kick"
[m_knock](knock.md) | - | `K` | - | - | `KNOCK` | Provides `KNOCK` and a channel mode to block the command
[m_ldapauth](ldapauth.md) | - | - | - | - | - | Authenticate users against a LDAP server
[m_ldapoper](ldapoper.md) | - | - | - | - | - | Authetnicate opers against a LDAP server
[m_lockserv](.md) | - | - | - | - | `LOCKSERV` `UNLOCKSERV` | Oper command to temporarily close and open a server to new connections
[m_maphide](maphide.md) | - | - | - | - | Modifies `MAP`/`LINKS` | Replaces `MAP` and `LINKS` with a config-defined URL
[m_md5](md5.md) | - | - | - | - | - | Provides MD5 hashing to other modules (such as [m_cloaking](cloaking.md)
[m_messageflood](messageflood.md) | - | `f` | - | - | - | Provides a channel mode to prevent `PRIVMSG`/`NOTICE` floods
[m_mssql](mssql.md) | - | - | - | - | - | Allows SQL modules to use a Microsoft SQL database
[m_muteban](muteban.md) | - | - | `m` | - | - | Provides an extban to mute users matching a mask on a channel
[m_mysql](mysql.md) | - | - | - | - | - | Allows SQL modules to use a MySQL database
[m_namedmodes](namedmodes.md) | - | `Z` | - | - | - | Allows the display, and set/unset of channel modes via long-form mode names
[m_namesx](namesx.md) | - | - | - | - | Extends `NAMES` | Adds the `NAMESX` multi-prefix `NAMES` feature
[m_nationalchars](nationalchars.md) | - | - | - | - | - | Allows national characters in nicknames and custom case-mapping network-wide
[m_nickflood](nickflood.md) | - | `F` | - | - | - | Provides a channel mode limiting the rate of nick changes per-person
[m_nicklock](nicklock.md) | - | - | - | - | `NICKLOCK` `NICKUNLOCK` | Oper command to switch and lock a user's nick to a new nickname
[m_noctcp](noctcp.md) | - | `C` | `C` | - | - | Provides a way for channels to block `CTCP` sent to channels
[m_nokicks](nokicks.md) | - | `Q` | `Q` | - | - | Blocks `KICK`s from non-`u:line`'d or oper'd users
[m_nonicks](nonicks.md) | - | `N` | `N` | - | - | Provides a channel mode blocking nick changes in a channel
[m_nonotice](nonotice.md) | - | `T` | `T` | - | - | Provides a channel mode blocking `NOTICE`s to a channel
[m_nopartmsg](nopartmsg.md) | - | - | `p` | - | - | Extban blocking part message from matching clients
[m_ojoin](ojoin.md) | - | `Y` | - | - | `OJOIN` | Provides a method for opers to join channels on official network business
[m_operchans](operchans.md) | - | `O` | - | - | - | Provides a channel mode to mark channels 'oper-only'
[m_operjoin](operjoin.md) | - | - | - | - | - | Forces user to join config-defined channels on `OPER`
 

[](.md) | - | - | - | - | - | 
# List of all unofficial Inspircd 2.0 modules
