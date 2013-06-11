---
title: Modules &raquo; m_sslinfo
layout: default
---

## Description

Allows users to query an SSL user for their SSL client-key fingerprint. This can be used by client scripts to 
validate users. This module also adds the `* <user> is using a secure connection` `WHOIS` line, the ability for
opers to use SSL fingerprints to verify their identity and the ability to force opers to use SSL connections in 
order to oper up. It is **highly recommended** to load this module especially if you use SSL on your network.

## Configuration Tags

Note: The `<oper>` tags enabled by [m_sslinfo](sslinfo.md) are disabled by default, you must specify them to use them.

<oper
name="Brain"
host="ident@dialup15.isp.com *@localhost *@server.com *@3ffe::0/16"
vhost="brain.netadmin.omega"
type="NetAdmin"
fingerprint="67cb9dc013248a829bb2171ed11becd4"
autologin="on"
sslonly="yes">

Attribute | Type | Description
--------- | ---- | -----------
autologin | bool | If an SSL fingerprint for this oper is specified, you can have the oper automatically log in by setting this to `on`. This moves all security of the `<oper>` block to the protection of the client certificate, so be sure that the private key is well-protected!
fingerprint | string | When using the [m_sslinfo](sslinfo.md) module, you may specify a key fingerprint here. This can be obtained by using the `/SSLINFO` command while the module is loaded. This enhances security by verifying that the person opering-up has a matching SSL client certificate, which is very difficult to forge (impossible unless preimage attacks on the hash exist).
sslonly | bool | This oper can only oper-up if they're using a SSL connection. Setting this option adds a decent bit of security. **Highly recommended**, and borderlin-mandatory if the oper uses unsecured WIFI points or other untrusted networks. Note: It's redundant to specify this option if you also specify a fingerprint.

**These options will only work if [m_sslinfo](sslinfo.md) is loaded.**

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/SSLINFO <nickname>` | No | N/A | Displays `<nickname>`'s SSL client key fingerprint, if they have one.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

### Requires

Either [m_ssl_gnutls](ssl_gnutls.md) or [m_ssl_openssl](ssl_openssl.md).
