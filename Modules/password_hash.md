---
title: Modules &raquo; m_password_hash
layout: default
---

## Description

Allows any user to hash a password.

## Configuration Tags

This module implements no configuration directives.

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/MKPASSWD <hashtype> <plaintext>` | No | N/A | Makes a hash of `<plaintext>` using the method supplied in `<hashtype>`

`<hashtype>` can be any loaded hash module. Note that prepending `HMAC-` to the name of the hash will use a salted
version of the hash that will thwart [rainbow table](http://en.wikipedia.org/wiki/Rainbow_table) attacks. i.e. 
`/MKPASSWD HMAC-sha256 passwordtext` will be far more secure than `/MKPASSWD sha256 passwordtext`

Note: `/MKPASSWD` has a hefty penalty of 5 seconds per use, which makes it nearly impossible for users to abuse this
in malicious ways.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

This module will operate alongside plaintext passwords. To use hashes simply replace the plaintext password in 
`<oper:password>` with the hash `/MKPASSWD` gives you.

Please note that once you move your oper passwords to hashes, you will be unable to oper up without this module 
loaded; if you unload this module, you will be left unable to reload it if you lose oper status.

This module can enumerate any module which implements the HashRequest interface. Currently, this includes [m_sha256](sha256.md),
[m_md5](md5.md) and [m_ripemd160](ripemd160.md). 

### Requires

This module requires at least one of the hashing modules. Any of them ([m_md5](md5.md) 
[m_sha256](sha256.md) [m_ripemd160](ripemd160.md)) will work.
