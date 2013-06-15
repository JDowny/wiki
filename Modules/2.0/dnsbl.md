---
title: Modules &raquo; m_dnsbl
layout: default
---

## Description

[m_dnsbl](dnsbl.md) provides support for looking up IPs of connecting users on one or more blacklists. It is 
fully configurable. **This is an advanced module** and knowledge of DNS is needed to use this module properly.

## Configuration Tags

    <dnsbl name="dnsblname" type="bitmask" domain="dns.domain.org" action="KILL" 
    reason="You are banned!" duration="1d" bitmask="5">

**or**

    <dnsbl name="dnsblname" type="record" domain="dns.domain.org" action="KILL" 
    reason="You are banned!" duration="1d" records="1,2,6,19,24-38">`

Attribute | Type | Description
--------- | ---- | -----------
name | string | A readable name for the blacklist, e.g. DroneBL (This is meant for oper reference, and does not affect the module's function in any way)
type | string | The type of blacklist, either `bitmask` or `record`
domain | string | the dns domain the bl uses. `dnsbl.dronebl.org` for example
action | string | one out of `KILL`, `ZLINE`, `KLINE`, `GLINE` ( **case sensitive!** )
reason | string | any text you want to use as banreason or tag (`%ip%` will be replaced by the user's ip). Suggested use is a link to the DNSBL's removal page or contact information for a network operator.
duration | string | how long you want to enforce the ban (takes no effect if `action` is `KILL`). This uses standard Inspircd date formatting: `1y2w3d5h6m7s`
bitmask | int | For bitmask type blacklists, this is an `AND` mask the result from the rbl is masked against. e.g. if you only want results `1` and `4`, enter `5` ( equal to `1 | 4`) here. Must be greater than `0` (use `255` for matching all [Class C](https://en.wikipedia.org/wiki/Classful_network) backlist results)
records | string | For record type blacklists this is a list of `A` record replies which cause a match for this blacklist. This value can contain lists or ranges of integer values, i.e. `1,2,3,5-9` to match all values within the range `1,2,3,5,6,7,8,9`.

**Note**: A single `<dnsbl>` tag may *only* make use of one of either records or bitmask at any one time, depending on the value of type.

Examples:

    <dnsbl name="DroneBL"
    type="bitmask"
    domain="dnsbl.dronebl.org" 
    action="ZLINE" 
    reason="You are listed in DroneBL. Please visit http://dronebl.org/lookup.do?ip=%ip%"
    duration="1h"
    bitmask="253">

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

Needs to be loaded on **each server** of a network.

Known to work blacklists are [Tor Server Blacklist](http://www.sectoor.de/tor.php) and [DroneBL](http://dronebl.org/).

This module creates the `STATS` flag `d`. Which displays current DNSBL stats for each `<dnsbl>` tag.
