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

The values have the following meanings:

`address`

Specifies which address ports bind to. Leaving this field blank binds the port to all available IP addresses.

`port`

The port number to bind to. You may specify a port range here, i.e. "6667-6669,7000,7001". If you do this, the server 
will count each port within your range as a seperate binding, making the above example equivalent to five seperate 
bind tags. A failure on one port in the range does not prevent the entire range from being bound, just that 
one port number.

`type`

Should be set to 'servers'. The servers type is a a TCP based connection but of a different format than that used 
for clients.

`transport`

If you have either of the SSL modules (m_ssl_gnutls or m_ssl_openssl) loaded, or the compression module (m_ziplink) 
loaded then you may make use of this optional value. Setting it to 'openssl', 'zip' or 'gnutls' indicates that the 
port should accept connections using the given transport name only. Transports are layers which sit on top of a 
socket and change the way data is sent and received, e.g. encryption, compression, and other such things. Because 
this may not be limited in use to just encryption, the 'ssl' value used for client ports does not exist for servers, 
and this value is used instead. 

### Defining Links

This tag defines which servers can link to this one, and which servers this server may create outbound links to. 

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

The values have the following meanings:

`name`

The name is the canonical name of the server, does not have to resolve - but must be the same as the remote servers 
connection info to link.

`ipaddr`

Valid host or ip address for remote server. **These hosts are resolved on rehash and cached if you specify a hostname.**
If you find that your server is still trying to connect to an old IP after you have updated your dns, try rehashing 
and then attempting the connect again.
    
`port`

The TCP port for the remote server.

`sendpass`

Password to send to create an outbound connection from this server.

`recvpass`

Password to receive to accept an inbound connection to this server.

`autoconnect`

This optional setting sets the server to autoconnect. Where the value is the number of seconds between attempts. 
i.e. 300 is equal to 5 minutes.

`transport`

If defined, this is a transport name implemented by another module. 
Transports are layers on top of plaintext connections, which alter them in certain ways. 
Currently the three supported transports are 'openssl' (`m_ssl_openssl`), 'gnutls' (`m_ssl_gnutls`) and 
'zip' (`m_ziplink`) which are types of encryption and compression, respectively. 
If you define a transport, both ends of the connection must use a compatible transport for the link to succeed 
OpenSSL and GnuTLS are compatible with each other.

`hidden`

When using m_spanningtree.so for linking. you may set this to 'yes', and if you do, the IP address/hostname of this 
connection will NEVER be shown to any opers on the network. In /STATS c its address will show as *@<hidden>, and 
during CONNECT and inbound connections, its IP will show as <hidden> UNLESS the connection fails (e.g. due to a 
bad password or servername).

`allowmask`

When this is defined, it indicates a range of IP addresses to allow for this link (You may use CIDR or wildcard form 
for this address). e.g. if your server is going to connect to you from the range 1.2.3.1 through 1.2.3.255, 
put 1.2.3.0/24 into this value. If it is not defined, then only the ipaddr field of the server shall be allowed.

`failover`

If you define this option, it must be the name of a different link tag in your configuration. This option causes the 
ircd to attempt a connection to the failover link in the event that the connection to this server fails. For example, 
you could define two hub uplinks to a leaf server, and set an american server to autoconnect, with a european hub as 
its failover. In this situation, your ircd will only try the link to the european hub if the american hub is unreachable. 
Note that for the intents and purposes of this option, an unreachable server is one which DOES NOT ANSWER THE CONNECTION. 
If the server answers the connection with accept(), EVEN IF THE CREDENTIALS ARE INVALID, the failover link will not be 
tried! Failover settings will also apply to autoconnected servers as well as manually connected ones.

`timeout`

If this is defined, then outbound connections will time out if they are not connected within this many seconds. If this 
is not defined, the default of ten seconds is used.

`bind`

The IP to bind an outgoing connection to. If not defined, connections bind to the first server IP on the box, and if 
none of these are defined, then the socket is bound to INADDR_ANY. 

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

`/RCONNECT [source mask] [target mask]`

When the `/RCONNECT` command is issued, all servers which match `[source mask]` will try to `/CONNECT` to the first 
server they have in their config matching `[target mask]`.

For example: `RCONNECT penguins.* polarbears.*` causes the ircd `penguins.*` to attempt a connect to `polarbears.*`, 
regardless of which server you are currently on (so long as `penguins.*` is reachable of course!)

`/RSQUIT [target mask]`

Causes the remote server `[target mask]` to be disconnected from the network. 

`/RSQUIT [source mask] [target mask]`

Causes the remote server `[target mask]` to have its connection closed by `[source mask]`, similar in operation to 
`/RCONNECT`.

### Modified Commands

`/ADMIN [servername]`

Allows displaying of remote server's admin details

`/CONNECT [destination server mask]`

Connects local servers together

`/LINKS`

Shows which servers are linked to which other servers

`/MAP`

Shows a server map of all connected servers.

`/MODULES [servername]`

Allows displaying of a remote server's loaded modules 

`/MOTD [servername]`

Allows displaying of a remote server's message of the day file

`/SQUIT [destination server mask]`

Causes local servers to terminate their link

`/STATS [servername]`

Allows display of remote stats

`/WHOIS [nick] [servername]`

Allows performing of remote WHOIS on remotely connected users

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

`m_ssl_gnutls`, `m_ssl_openssl` for transport encryption (**STRONGLY RECOMMENDED**)

`m_ziplink` for transport compression (can reduce traffic on high-bandwidth networks)
