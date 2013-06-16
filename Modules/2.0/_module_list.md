---
title: Modules &raquo; module_list
layout: default
---

# List of all official Inspircd 2.0 modules

Module Name | umode | cmode | extban | SNOMASK | Commands | Description
----------- | ---------- | ------------- | ------------- | -------- | -------- | -----------
[m_abbreviation](abbreviation.md) | - | - | - | - | - | Allows commands to be abbreviated
[m_alias](alias.md)           | - | - | - | - | - | Allows aliasing commands to other commands. (i.e. `/NS` to `/PRIVMSG NICKSERV`
[m_allowinvite](allowinvite.md) | - | `A` | `A` | - | - | Allows commands to be abbreviated
[m_alltime](alltime.md)       | - | - | - | - | `ALLTIME` | Shows [Epoch time](https://en.wikipedia.org/wiki/Unix_time) for every server on the network
[m_auditorium](auditorium.md) | - | `u` | - | - | - | Allows for "Auditorium" channels, where the only visible user is yourself (useful for mass conferencing)
[m_autoop](autoop.md)         | - | `w` | - | - | - | Provides a list mode that allows for simple channel access lists
[m_banexception](banexception.md) | - | - | - | - | - | Provides a list mode that allows ops to exempt `nick!user@host` masks for existing bans
[m_banredirect](banredirect.md) | - | - | `#channel` | - | - | Allows bans to redirect users to another channel
[m_blockamsg](blockamsg.md)   | - | - | - | - | - | Blocks usage of `AMSG` and `AME`
[m_blockcaps](blockcaps.md)   | - | `B` | `B` | - | - | Blocks all caps messages to a channel
[m_blockcolor](blockcolor.md) | - | `c` | `c` | - | - | Block messages to a channel containing color control codes
[m_botmode](botmode.md)       | `B` | - | - | - | - | Provides a mode to mark a user as a bot in `WHOIS`
[m_callerid](callerid.md)     | `g` | - | - | - | `ACCEPT` | Allows a user whitelist-based control over who can `PRIVMSG` them
[m_cap](cap.md)               | - | - | - | - | `CAP` | Implements the `CAP` capabilities extension
[m_cban](cban.md)             | - | - | - | - | `CBAN` | Lets opers disallow channels on the network
[m_censor](censor.md)         | `G` | `G` | - | - | - | Provides network-wide censoring of words/patterns via a user/channel mode
[m_cgiirc](cgiirc.md)         | - | - | - | - | - | Adds support for CGI-IRC automatic host changing on connect
[m_chancreate](chancreate.md) | - | - | - | `jJ` | - | Adds an oper SNOMASK that logs channel creation
[m_chanfilter](chanfilter.md) | - | `g` | - | - | - | Provides an equivalent to `G` ([m_censor](censor.md)) wher instead channel operators choose the word list
[m_chanhistory](chanhistory.md) | - | `H` | - | - | - | Provides a configurable amount of channel history to newly joining users
[m_chanlog](chanlog.md)       | - | - | - | - | - | Allows SNOMASKs to be sent to a channel
[m_channames](channames.md)   | - | - | - | - | - | Implements config tags which allow changing characters allowed in channel names
[m_channelban](channelban.md) | - | - | `j` | - | - | EXtban that will prevent a user from joining a channel if they're in a specified second channel.
[m_chanprotect](chanprotect.md) | - | `qa` | - | - | - | ( **DEPRECATED** ) Adds support for channel 'owners' and 'protected' ops
[m_check](check.md)           | - | - | - | - | `CHECK` | Provides a tool to lookup user, channel or host information
[m_chghost](chghost.md)       | - | - | - | - | `CHGHOST` | Oper command which can change the host of any connected user
[m_chgident](chgident.md)     | - | - | - | - | `CHGIDENT` | Oper command which can change the ident of any connected user
[m_chgname](chgname.md)       | - | - | - | - | `CHGNAME` | Oper command which can change the name (`GECOS`) of any connected user
[m_cloaking](cloaking.md)     | `x` | - | - | - | - | Provides a method for making hostnames private
[m_clones](clones.md)         | - | - | - | - | `CLONES` | Oper command providing a list of users above a certain number of connections
[m_close](close.md)           | - | - | - | - | `CLOSE` | Oper command allowing incomplete new connections to be closed
[m_commonchans](commonchans.md) | `c` | - | - | - | - | User mode requiring a user to share a channel with the client `c` is set on to `PRIVMSG` them
[m_conn_join](conn_join.md)   | - | - | - | - | - | Forces users to join one or more channels on connection
[m_conn_umodes](conn_umodes.md) | - | - | - | - | - | Sets or removes user modes from clients on connect
[m_conn_waitpong](conn_waitpong.md) | - | - | - | - | - | Requires clients to send a matching `PONG` to a server `PING` containing a random string before they can finish connecting
[m_connectban](connectban.md) | - | - | - | - | - | Provides per-IP connection throttling
[m_connflood](connflood.md)   | - | - | - | - | - | Throttles connections if server is connect-flooded
[m_customprefix](customprefix.md) | - | - | - | - | - | Allows configuring channel user modes with custom prefixes and ranks
[m_customtitle](customtitle.md) | - | - | - | - | `TITLE` | Adds a command to auth for a vanity `SWHOIS` line as well as a vhost. Config defined
[m_cycle](cycle.md)           | - | - | - | - | `CYCLE` | `PART`s and `JOIN`s a channel, bypassing any modes blocking new `JOIN`s
[m_dccallow](dccallow.md)     | - | - | - | - | `DCCALLOW` | Adds the `DCCALLOW` command and configuration options to block files with wildcard masks
[m_deaf](deaf.md)             | `d` | - | - | - | - | Adds a user mode to stop receipt of channel messages
[m_delayjoin](delayjoin.md)   | - | `D` | - | - | - | Users will not appear in the channel until they speak
[m_delaymsg](delaymsg.md)     | - | `d` | - | - | - | Users cannot message the channel until a set number of seconds have elapsed
[m_denychans](denychans.md)   | - | - | - | - | - | Blocks users from using config-defined channels
[m_devoice](devoice.md)       | - | - | - | - | `DEVOICE` | Allows users to devoice themselves in a channel
[m_dnsbl](dnsbl.md)           | - | - | - | - | - | Provides DNS-blacklist lookups on connecting users
[m_exemptchanops](exemptchanops.md) | - | - | - | - | - | Allows channels to exempt user levels from different modes
[m_filter](filter.md)         | - | - | - | - | `FILTER` | Advanced message-filtering for spam/virus protection
[m_gecosban](gecosban.md)     | - | - | `r` | - | - | Adds an extban for user real names
[m_geoip](geoip.md)           | - | - | - | - | - | Allows blocking connections according to country codes (~98% accuracy)
[m_globalload](globalload.md) | - | - | - | - | `GLOADMODULE` `GUNLOADMODULE` `GRELOADMODULE` | Opers can load or unload Inspircd modules network-wide
[m_globops](globops.md)       | - | - | - | `g` | `GLOBOPS` | Opers can mass-message all users with SNOMASK `g`
[m_halfop](halfop.md)         | - | `h` | - | - | - | ( **DEPRECATED** ) Provides channel half-operators
[m_helpop](.md)               | `h` | - | - | - | `HELPOP` | Provides a help system, defined through config directives
[m_hidechans](hidechans.md)   | `I` | - | - | - | - | Hides the channels a user is in
[m_hideoper](hideoper.md)     | `H` | - | - | - | - | Opers can hide their operator status
[m_hostchange](hostchange.md) | - | - | - | - | - | Provides a different style of host-cloaking than [m_cloaking](cloaking.md)
[m_httpd](httpd.md)           | - | - | - | - | - | Provides a local HTTP server for hosting XML/HTML status reports. Useful with other modules
[m_httpd_acl](httpd_acl.md)   | - | - | - | - | - | Provides access control lists to [m_httpd](httpd.md) and other modules that depend upon it.
[m_httpd_config](httpd_config.md) | - | - | - | - | - | Provides a method to view server config via HTTP
[m_httpd_stats](httpd_stats.md) | - | - | - | - | - | Provides basic server stats via [m_httpd](httpd.md)
[m_ident](ident.md)           | - | - | - | - | - | Provides traditional `IDENT` ([RFC 1413](https://tools.ietf.org/html/rfc1413) lookups on connecting users.
[m_inviteexception](inviteexception.md) | - | `I` | - | - | - | Provides a channel list mode to exempt masks from needing an `INVITE` to join a channel
[m_joinflood](joinflood.md)   | - | `j` | - | - | - | Provides a channel mode to limit `JOIN` rate
[m_jumpserver](jumpserver.md) | - | - | - | - | `JUMPSERVER` | Oper command implementing the `JUMPSERVER` mechanism through the `RPL_REDIR` numeric
[m_kicknorejoin](kicknorejoin.md) | - | `J` | - | - | - | Provides a channel mode to block "auto-rejoin on kick"
[m_knock](knock.md)           | - | `K` | - | - | `KNOCK` | Provides `KNOCK` and a channel mode to block the command
[m_ldapauth](ldapauth.md)     | - | - | - | - | - | Authenticate users against a LDAP server
[m_ldapoper](ldapoper.md)     | - | - | - | - | - | Authetnicate opers against a LDAP server
[m_lockserv](.md)             | - | - | - | - | `LOCKSERV` `UNLOCKSERV` | Oper command to temporarily close and open a server to new connections
[m_maphide](maphide.md)       | - | - | - | - | Modifies `MAP`/`LINKS` | Replaces `MAP` and `LINKS` with a config-defined URL
[m_md5](md5.md)               | - | - | - | - | - | Provides [MD5](https://en.wikipedia.org/wiki/Md5) hashing to other modules (such as [m_cloaking](cloaking.md)
[m_messageflood](messageflood.md) | - | `f` | - | - | - | Provides a channel mode to prevent `PRIVMSG`/`NOTICE` floods
[m_mssql](mssql.md)           | - | - | - | - | - | Allows SQL modules to use a Microsoft SQL database
[m_muteban](muteban.md)       | - | - | `m` | - | - | Provides an extban to mute users matching a mask on a channel
[m_mysql](mysql.md)           | - | - | - | - | - | Allows SQL modules to use a MySQL database
[m_namedmodes](namedmodes.md) | - | `Z` | - | - | - | Allows the display, and set/unset of channel modes via long-form mode names
[m_namesx](namesx.md)         | - | - | - | - | Extends `NAMES` | Adds the `NAMESX` multi-prefix `NAMES` feature
[m_nationalchars](nationalchars.md) | - | - | - | - | - | Allows national characters in nicknames and custom case-mapping network-wide
[m_nickflood](nickflood.md)   | - | `F` | - | - | - | Provides a channel mode limiting the rate of nick changes per-person
[m_nicklock](nicklock.md)     | - | - | - | - | `NICKLOCK` `NICKUNLOCK` | Oper command to switch and lock a user's nick to a new nickname
[m_noctcp](noctcp.md)         | - | `C` | `C` | - | - | Provides a way for channels to block `CTCP` sent to channels
[m_nokicks](nokicks.md)       | - | `Q` | `Q` | - | - | Blocks `KICK`s from non-`u:line`'d or oper'd users
[m_nonicks](nonicks.md)       | - | `N` | `N` | - | - | Provides a channel mode blocking nick changes in a channel
[m_nonotice](nonotice.md)     | - | `T` | `T` | - | - | Provides a channel mode blocking `NOTICE`s to a channel
[m_nopartmsg](nopartmsg.md)   | - | - | `p` | - | - | Extban blocking part message from matching clients
[m_ojoin](ojoin.md)           | - | `Y` | - | - | `OJOIN` | Provides a method for opers to join channels on official network business
[m_operchans](operchans.md)   | - | `O` | - | - | - | Provides a channel mode to mark channels 'oper-only'
[m_operjoin](operjoin.md)     | - | - | - | - | - | Forces user to join config-defined channels on `OPER`
[m_operlevels](operlevels.md) | - | - | - | - | - | Provides oper types and rankings
[m_operlog](operlog.md)       | - | - | - | - | - | Provides a way to log all oper commands
[m_opermodes](opermodes.md)   | - | - | - | - | - | Provides a way to add and remove modes from a user on `OPER`
[m_opermotd](opermotd.md)     | - | - | - | - | `OPERMOTD` | Shows a message to users on `OPER`
[m_operprefix](operprefix.md) | - | `y` | - | - | - | Provides a way to give IRC operators a channel prefix in all of their channels
[m_override](override.md)     | - | - | - | `G` | - | Provides a method for opers to override modes and commands
[m_passforward](passforward.md) | - | - | - | - | - | Forwards provided server password to nickserv on connect
[m_password_hash](password_hash.md) | - | - | - | - | `MKPASSWD` | Provides a way to store passwords as secure hashes
[m_permchannels](permchannels.md) | - | `P` | - | - | - | Provides support for permanent channels
[m_pgsql](pgsql.md)           | - | - | - | - | - | Allows SQL modules to use a PostgreSQL database via the SQLv2 API
[m_randquote](randquote.md)   | - | - | - | - | `RANDQUOTE` | Provides a method to show users a random quote on connect
[m_redirect](redirect.md)     | - | `L` | - | - | - | Provides a cmode to forward users to another channel once the limit set by cmode `l` is reached
[m_regex_glob](regex_glob.md) | - | - | - | - | - | Provides [glob](https://en.wikipedia.org/wiki/Glob_%28programming%29) matching for other modules
[m_regex_pcre](regex_pcre.md) | - | - | - | - | - | Provides [Perl-Compatible Regular Expression](https://en.wikipedia.org/wiki/Pcre) matching for other modules
[m_regex_posix](regex_posix.md) | - | - | - | - | - | Provides [POSIX Regular Expression](https://en.wikipedia.org/wiki/Regular_expression#POSIX_basic_and_extended) matching for other modules
[m_regex_tre](regex_tre.md)   | - | - | - | - | - | Provides [TRE Regular Expression](https://en.wikipedia.org/wiki/TRE_%28computing%29) matching for other modules
[m_regonlycreate](regonlycreate.md) | - | - | - | - | - | Provides a method to only allow registered users to create channels on the network
[m_remove](remove.md)         | - | - | - | - | `REMOVE` `FPART` | Provides alternatives to `KICK`
[m_restrictchans](restrictchans.md) | - | - | - | - | - | Blocks non-opers from creating channels on the network
[m_restrictmsg](restrictmsg.md) | - | - | - | - | - | Prevents all `PRIVMSG`/`NOTICE` except those to/from opers
[m_ripemd160](.md)            | - | - | - | - | - | Provides [RIPEMD-160](https://en.wikipedia.org/wiki/RIPEMD160) hashing for other modules
[m_rline](rline.md)           | - | - | - | - | `RLINE` | Provides a way for opers to place regex-based network bans
[m_sajoin](sajoin.md)         | - | - | - | - | `SAJOIN` | Oper command forcing a user to `JOIN` a channel
[m_samode](samode.md)         | - | - | - | - | `SAMODE` | Oper command forcing a mode change on a user
[m_sanick](sanick.md)         | - | - | - | - | `SANICK` | Oper command forcing a nick change on a user
[m_saquit](saquit.md)         | - | - | - | - | `SAQUIT` | Oper command forcing a user to `QUIT`
[m_sasl](sasl.md)             | - | - | - | - | `AUTHENTICATE` | Provides support for [Simple Authentication and Security Layer](https://en.wikipedia.org/wiki/Simple_Authentication_and_Security_Layer)
[m_satopic](satopic.md)       | - | - | - | - | `SATOPIC` | Oper command forcing a topic change on a channel
[m_securelist](securelist.md) | - | - | - | - | - | Blocks `LIST` for a number of seconds after connect, breaking many common spam bots
[m_seenicks](seenicks.md)     | - | - | - | `nN` | - | Provides a SNOMASK showing opers nick changes on the network
[m_serverban](serverban.md)   | - | - | `s` | - | - | Provides an extban blocking users on a specific server from joining a channel
[m_services_account](services_account.md) | `R` | `MR` | `MRU` | - | - | Implements an `IDENTIFIED` state for network services
[m_servprotect](servprotect.md) | `k` | - | - | - | - | Provides support for a services mode (essentially: god mode)
[m_sethost](sethost.md)       | - | - | - | - | `SETHOST` | Oper command allowing an oper to change their own host
[m_setident](setident.md)     | - | - | - | - | `SETIDENT` | Oper command allowing an oper to change their own ident
[m_setidle](setidle.md)       | - | - | - | - | `SETIDLE` | Oper command allowing an oper to change their own idle time
[m_setname](setname.md)       | - | - | - | - | `SETNAME` | Command allowing any user to change their own real name (`GECOS`)
[m_sha256](sha256.md)         | - | - | - | - | - | Provides [SHA-256](https://en.wikipedia.org/wiki/SHA-2) hashing for other modules
[m_showwhois](showwhois.md)   | `W` | - | - | - | - | Oper mode to show when and who `WHOIS`'s the oper
[m_shun](shun.md)             | - | - | - | - | `SHUN` | Oper command to block input from specified users
[m_silence](silence.md)       | - | - | - | - | `SILENCE` | Command providing server-side version of `IGNORE`
[m_spanningtree](spanningtree.md) | - | - | - | - | `RCONNECT` `RSQUIT` | Provides support for linking servers in a [spanning tree](https://en.wikipedia.org/wiki/Spanning_tree). A linking module is required to connect to services or other servers
[m_ssl_gnutls](ssl_gnutls.md) | - | - | - | - | - | ( **RECOMMENDED** ) Provides support for using [SSL](https://en.wikipedia.org/wiki/Secure_Socket_Layer) in connections
[m_ssl_openssl](ssl_openssl.md) | - | - | - | - | - | ( **DEPRECATED** ) Provides support for using [SSL](https://en.wikipedia.org/wiki/Secure_Socket_Layer) in connections
[m_sslinfo](sslinfo.md)       | - | - | - | - | `SSLINFO` | Provides a method to force opers to use [SSL](https://en.wikipedia.org/wiki/Secure_Socket_Layer), allows users to authenticate each other using [SSL](https://en.wikipedia.org/wiki/Secure_Socket_Layer) fingerprints and more
[m_sslmodes](.md)             | - | `z` | - | - | - | Provides a way for channels to require users to be using [SSL](https://en.wikipedia.org/wiki/Secure_Socket_Layer) to join
[m_sqlauth](sqlauth.md)       | - | - | - | - | - | Provides a way to use a SQL database to validate incoming connections
[m_sqlite3](sqlite3.md)       | - | - | - | - | - | Allows SQL modules to use a SQLite database
[m_sqloper](sqloper.md)       | - | - | - | - | - | Allows using an SQL database to store oper credentials
[m_stripcolor](stripcolor.md) | `S` | `S` | `S` | - | - | Adds a channel/user mode and extban to strip color from messages
[m_svshold](svshold.md)       | - | - | - | - | `SVSHOLD` | Implements `SVSHOLD` for services packages
[m_swhois](swhois.md)         | - | - | - | - | `SWHOIS` | Oper command to add a `SWHOIS` line to a user
[m_timedbans](timedbans.md)   | - | - | - | - | `TBAN` | Provides a command for channel operators to set timed bans
[m_tline](tline.md)           | - | - | - | - | `TLINE` | Oper command to test the reach of a `x:line`
[m_uhnames](uhnames.md)       | - | - | - | - | - | IRCd extension to send user host in `NAMES` reply
[m_uninvite](uninvite.md)     | - | - | - | - | `UNINVITE` | Provides a way to cancel `INVITE`s
[m_userip](userip.md)         | - | - | - | - | `USERIP` | Oper command to return the IP of a user
[m_vhost](vhost.md)           | - | - | - | - | `VHOST` | Provides a way for users to authenticate for a config-defined vhost
[m_watch](watch.md)           | - | - | - | - | `SVSWATCH` `WATCH` | Provides a system to alert users when another user connects
[m_xline_db](xline_db.md)     | - | - | - | - | - | Persistent storage for `x:lines` across server restarts


# List of all unofficial Inspircd 2.0 modules

Module Name | umode | cmode | extban | SNOMASK | Commands | Description
----------- | ---------- | ------------- | ------------- | -------- | -------- | -----------
[m_antibear](.md)   | - | - | - | - | - | Sends a numeric on connect which cripples common type of spambot
[m_antibottler](.md) | - | - | - | - | - | Changes the ident of connecting [Bottler](http://blotter.sourceforge.net/) clients to `bottler`
[m_antirandom](.md) | - | - | - | - | - | Attempts to block bots using randomly set `nick!user@host GECOS` from connecting
[m_changecap](.md)  | - | - | - | - | `CHANGECAP` | Command allowing channel operators to change capitalization of a channel name
[m_conn_banner](.md) | - | - | - | - | - | Displays static text to every user before registration
[m_custompenalty](.md) | - | - | - | - | - | Allows customizing the penalty levels of commands
[m_findxline](.md)  | - | - | - | - | `FINDXLINE` | Oper command allowing searching `x:line`s
[m_hash_gnutls](.md) | - | - | - | - | - | Implements hash function using GNUTLS API
[m_hideidle](.md)   | `a` | - | - | - | - | Provides umode hiding `IDLE` and signon time from non-opers
[m_invisible](.md)  | `Q` | - | - | - | - | Oper mode allowing an oper to join a channel without being seen by the joined channel
[m_invitenotify](.md) | - | - | - | - | - | Notifies a channel that a user has been `INVITE`'d to it
[m_ircxusernames](.md) | - | - | - | - | - | Provides support for [IRCX](https://en.wikipedia.org/wiki/IRCX) usernames
[m_join0](.md)      | - | - | - | - | Modifies `JOIN` | Joining `0` `PART`s all channels
[m_joinpartsno](.md) | - | - | - | `eEpP` | - | Provides SNOMASK showing all user `JOIN`s/`PART`s from all channels
[m_namedstats](.md) | - | - | - | - | Modifies `STATS` | Similar to [m_namedmodes](namedmodes.md); allows querying `STATS` with names in additon to letters
[m_noctcp_user](.md) | `T` | - | - | - | - | Provides a mode blocking `CTCP`s sent to a user
[m_pretenduser](.md) | - | - | - | - | `PRETENDUSER` | Oper command allowing opers to issue commands as another user
[m_privdeaf](.md)   | `D` | - | - | - | - | Provides a method for users to ignore all non-channel messages
[m_quietban](.md)   | - | `q` | - | - | - | WARNING: THIS MODULE IS INCOMPATIBLE WITH [m_chanprotect](chanprotect.md) Provides a list mode preventing users from speaking in channel
