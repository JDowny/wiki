---
title: Modules &raquo; m_spanningtree
layout: default
---

## Description

Allows for linking of servers using a traditional [spanning tree](http://en.wikipedia.org/wiki/Spanning_tree_%28mathematics%29) 
like those seen in most irc servers. 

This module is vital for linking to other servers in a network, or for linking services programs etc. 

However, if you never intend to link to anything ( *including services* ) then you do not need to load `m_spanningtree`.

## Configuration

### Listening for Server Connections

We need to listen on a port for server connections, rather than client connections. Create a `<bind>` tag to servers:

`<bind address="" port="7000-7004" type="servers" transport="gnutls">`

Attribute | Type | Description
--------- | ---- | -----------
address | string | Specifies which address ports bind to. Leaving this field blank binds the port to all available IP addresses.
port | string | The port number to bind to. You may specify a port range here, i.e. `6667-6669,7000,7001`. If you do this, the server will count each port within your range as a seperate binding, making the above example equivalent to five seperate bind tags. A failure on one port in the range does **not** prevent the entire range from being bound, just that one port number.
transport | string | If you have either of the SSL modules ([m_ssl_gnutls](ssl_gnutls.md) or [m_ssl_openssl](ssl_openssl.md)) loaded you may make use of this optional value. Setting it to `openssl` or `gnutls` indicates that the port should **only** accept connections using the given transport name. Transports are layers which sit on top of a socket and change the way data is sent and received, i.e. encryption, compression, and other such things. Because this may not be limited in use to just encryption, the `ssl` value used for client ports does not exist for servers, and this value is used instead. 
type | string | Should be set to `servers`. The `servers` type is a a TCP based connection that uses a different format than that used for clients.

### Defining Links

This tag defines which servers we will accept incoming links from, and which servers this server may create 
outbound links to. 

    <link name="hub.penguin.org"
    ipaddr="penguin.box.com"
    port="7000"
    allowmask="69.58.44.0/24"
    autoconnect="300"
    failover="hub.other.net"
    timeout="15"
    transport="gnutls"
    bind="1.2.3.4"
    sendpass="outgoing!password"
    recvpass="incoming!password">

Attribute | Type | Description
--------- | ---- | -----------
allowmask | string | When this is defined, it indicates a range of IP addresses to allow for this link (You may use either [CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing) or wildcard form for this address). e.g. if your server is going to connect to you from the range `1.2.3.1` through `1.2.3.255`, set `1.2.3.0/24` as the value. If this is not defined, then only the value specified in the `ipaddr` will be allowed for this link.
autoconnect | int | This optional setting sets the server to autoconnect. Value is the number of seconds between attempts. i.e. `300` is equal to 5 minutes.
bind | string | The IP to bind an outgoing connection to. If not defined, connections bind to the first server IP on the box, and if none of these are defined, then the socket is bound to `INADDR_ANY`.
failover | string | If you define this option, it *must* be the **name of a different** `<link>` **tag in your configuration**. This option causes the IRCd to attempt a connection to the server in the `<link>` tag specified by `<failover>` if the connection to *this* link fails. For example, you could define two hub uplinks for a leaf server, and set the american hub as `autoconnect`, with the european hub as the `failover`. In this situation, your IRCd will **only** try the link to the european hub if the american hub is **unreachable**. **Note**: For the intents and purposes of this option, an unreachable server is one which **does not answer** the connection. As long as the link answers the connection with `accept()`, **it does not matter if the link completes**, the failover link will **not** be tried. Failover settings apply to both `autoconnect`'d servers as well as manually connected ones.
hidden | bool | If this to `yes` when using [m_spanningtree](spanningtree.md) for linking the IP address/hostname of the connection in this `<link>` tag will **never** be shown to *any* opers on the network. In `/STATS c` the address of the server on the other end of this link will show as `*@<hidden>`, and during `CONNECT` and inbound connections, its IP will show as `<hidden>` **unless the connection fails** (i.e. due to a bad password or servername).
ipaddr | string | Valid host or ip address for remote server. **These hosts are resolved on rehash and cached if you specify a hostname.** If you find that your server is still trying to connect to an old IP after you have updated your dns, try rehashing and then attempting the connect again.    
name | string | The name is the name of the server on the other end of the connection. This does **not** need to resolve but it **must** match the remote server's configured name to link.
port | string | The TCP port the remote server is listening for connections on.
recvpass | string | Password to receive to accept an inbound connection to this server.
sendpass | string | Password to send to create an outbound connection from this server.
timeout | int | If this is defined, then outbound connections will time out if they are not connected within this many seconds. If this is not defined, the default of `10` seconds is used.
transport | string | If defined, this is a transport name implemented by another module. Transports are layers on top of plaintext connections, which alter them in certain ways. Currently the supported transports are 'openssl' (`m_ssl_openssl`) and 'gnutls' (`m_ssl_gnutls`) which are types of encryption. If you define a transport, both ends of the connection must use a compatible transport for the link to succeed. OpenSSL and GnuTLS are compatible with each other.

###Defining services

Services require additional privileges over those given to normal linked servers. A server given these privileges is 
called a "u:line", and is referred to as a "u:line'd server".

To u:line a server (give it extra privilages required for running services, Q, etc) you must include the `<uline>` tag 
as shown in the example below. 

You can have as many of these as you like, but be warned that a u:lined server has extensive authority over the servers 
that have u:line'd it.

`<uline server="server.name">`


## Commands

### New Commands

Command | Oper-Only | Description
------- | --------- | -----------
`/RCONNECT [source mask] [target mask]` | Yes | When the `/RCONNECT` command is issued, all servers which match `[source mask]` will try to `/CONNECT` to the first server they have in their config matching `[target mask]`.<sup>1</sup> Note that this uses server names, and not hostnames.
`/RSQUIT [target mask]` | Yes | Causes the remote server `[target mask]` to be disconnected from the network. 
`/RSQUIT [source mask] [target mask]` | Yes | Causes the remote server `[target mask]` to have its connection closed by `[source mask]`, similar in operation to `/RCONNECT`.

1) For example: `RCONNECT penguins.* polarbears.*` causes the ircd `penguins.*` to attempt a connect to `polarbears.*`, 
regardless of which server you are currently on (so long as `penguins.*` is reachable of course!)

### Modified Commands

Command | Oper-Only | Description
------- | --------- | -----------
`/ADMIN [servername]` | No | Allows displaying of remote server's admin details
`/CONNECT [destination server mask]` | Yes | Connects local servers together
`/LINKS` | No | Shows which servers are linked to which other servers
`/MAP` | No | Shows a server map of all connected servers.
`/MODULES [servername]` | No | Allows displaying of a remote server's loaded modules 
`/MOTD [servername]` | No | Allows displaying of a remote server's message of the day file
`/SQUIT [destination server mask]` | Yes | Causes local servers to terminate their link
`/STATS [servername]` | No<sup>1</sup> | Allows display of remote stats
`/WHOIS [nick] [servername]` | No | Allows performing of remote WHOIS on remotely connected users

1) Note that many stats **are** infact oper-only.

## User Modes

This module implements no user modes.

## SNOMASK

No SNOMASKs directly implemented, but linking "activates" all `remote` SNOMASKs.

## Channel Modes

This module implements no channel modes.

## Extbans

This module implements no extended bans.

## Special Notes

**This module should be loaded last to avoid issues with load order.**

Note that in InspIRCd 1.1 (from beta 3 onwards) you may unload the spanningtree module with `/UNLOADMODULE`.

If you do this, **all servers will be disconnected** (`/SQUIT`). Use with CAUTION, and only for hotfixes where possible!

### Suggests

[`m_ssl_gnutls`](ssl_gnutls.md), [`m_ssl_openssl`](ssl_openssl.md) for transport encryption ( **STRONGLY RECOMMENDED** )
