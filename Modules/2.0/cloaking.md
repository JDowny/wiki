---
title: Modules &raquo; m_cloaking
layout: default
---

## Description

Masks the hostnames of users so their real host isn't shown to other users. 

Examples: `user@Network-to4.rd9.73.82.IP` or `user@Network-q6s8c6.users.provider.net`

## Configuration Tags

### Standard

`<cloak mode="half" key="secret" prefix="net-">`

Attribute | Type | Description
--------- | ---- | -----------
key | string | A single string that can be any length of text. Random [base 64](https://en.wikipedia.org/wiki/Base64) text greater than 20 characters in length is recommended.
prefix | string | What to place before user cloaks. Network name is the most common choice.
mode | string | There are two methods (and two deprecated methods) available. They are outlined in the [next section](cloaking.md#cloak-methods)

#### Cloak Methods

Method | Description
------ | -----------
half | Cloak only the "unique" portion of a host; show the last 2 parts of the domain, `/16` subnet of IPv4 or `/48` subnet of the IPv6 address.
full | Cloak the users completely, using three slices for common CIDR bans (IPv4: /16, /24; IPv6: /48, /64)

### Deprecated

The following methods are only maintained for backwards compatibility; you should not need to use these. These methods
are slightly **less secure**, and always hide unresolved IPs. **If you are uncertain, use the standard method**.

    <cloak mode="compat-ip" 
    key1="0x10000000"
    key2="0x20000000"
    key3="0x30000000"
    key4="0x40000000"
    prefix="net-">

Method | Description
------ | -----------
`compat-host` | InspIRCd 1.2-compatible host-based cloaking
`compat-ip` | InspIRCd 1.2-compatible ip-always cloaking

If you use a compat cloaking mode then you **must** specify `key1`, `key2`, `key3`, `key4`; the values 
must be less than `0x80000000` and should be picked at random. Prefix is **mandatory**, and will default to 
the network name if not specified, and will always have a `-` appended.

## Commands

This module implements no commands.

## User Modes

Mode | Oper-Only | Description
---- | --------- | -----------
x | No | User has a cloaked host. Cloak will be removed if the user unsets `x` on themselves.

**Note**: This mode will **not** automatically be set upon newly connected users. You **must** use [m_conn_umodes](conn_umodes.md) to do this.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

The hostname will be cloaked by taking the first portion of the hostname (before the `.`) and replacing it with a 
hash of the entirety of the hostname (hashed as a string), prefixed by the network name, for example 
`ChatSpike-0DF3269C`. Because the hash is built from the entire hostname and not the ip address, the hash generated 
when the user does not resolve is **different** from the hash generated when the user does resolve. Also because 
the length of the hashed result is considerably shorter than the actual hash, a lot of data is purposefully lost 
in the process, meaning that there is **no way to reverse the cloaking process** on a hostname and retrieve the users 
IP address. This means that the cloak key's only use is to make cloaked hosts unique to your network, as it is 
simply not a reversible algorithm in any way, shape or form. Please note that a potential risk *may* exist if an 
attacker knows all possible hostnames on your network, and it is a very small network, as the attacker may guess 
at which hostname you are using. This risk exists on *all* host-cloaking IRCd software. 


### Channle bans with cloaks

WRITE ME

### Requires

[m_md5](md5.md) to hash user IPs/hostnames
