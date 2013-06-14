---
title: Modules &raquo; m_password_hash
layout: default
---

## Description

Allows any user to hash a password.

## Configuration Tags

To use this module, you must define a hash type for each oper's password you want to hash. For example:

    <oper name="Brain"
    host="ident@dialup15.isp.com"
    hash="hmac-sha256"
    password="01ba4719c80b6fe911b091a7c05124b64eeece964e09c058ef8f9805daca546b"
    type="NetAdmin">
 
## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/MKPASSWD <hashtype>`<sup>1</sup> `<plaintext>` | No<sup>2</sup> | N/A | Makes a hash of `<plaintext>` using the method supplied in `<hashtype>`

1) `<hashtype>` can be any loaded hash module. 

2) `/MKPASSWD` has a hefty penalty of 5 seconds per use, which makes it nearly impossible for users to abuse this
in malicious ways.

**Note**: Prepending `hmac-` to the name of the hash will use a salted version of the hash that will make 
[rainbow table](http://en.wikipedia.org/wiki/Rainbow_table) attacks far less feasible. i.e. 
`/MKPASSWD hmac-sha256 passwordtext` will be **far** more secure than `/MKPASSWD sha256 passwordtext` **This is 
strongly recommended.**

**DO NOT RUN** `/MKPASSWD` **ON A SERVER YOU DON'T TRUST WITH YOUR PASSWORD!**

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

Please note that once you move your oper passwords to hashes, you will be unable to oper up without this module 
loaded; if you unload this module, you will be left unable to reload it if you lose oper status.

### Requires

This module requires at least one of the hashing modules. Any of them ([m_md5](md5.md) 
[m_sha256](sha256.md) [m_ripemd160](ripemd160.md)) will work.
