---
title: Modules &raquo; m_customtitle
layout: default
---

## Description

Adds the `/TITLE` command which allows for trusted users to gain a custom `WHOIS` line. An vhost may also be specified,
but is not required.

## Configuration Tags

`<title name="foo" password="bar" title="Official Chat Helper">`
`<title name="bar" password="foo" host="ident@host.name" title="Official Chat Helper" vhost="helper.network.chat">`
`<title name="foo" password="fcde2b2edba56bf408601fb721fe9b5c338d10ee429ea04fae5511b68fbf8fb9" hash="sha256" title="Official Chat Helper">`

Attribute | Type | Description
--------- | ---- | -----------
name | string | The username used to identify for the title
password | string | The password used to identify for the title
hash | string | The hash for the specific user's password ( **optional** ). [m_password_hash](password_hash.md) and a hashing module ([m_sha256](sha256.md), [m_md5](md5.md), [m_ripemd160](ripemd160), etc.)  must be loaded for this to work.
host | string |  Allowed hostmasks for this title ( **optional** )
title | string | Title shown in `WHOIS`
vhost | string | Displayed host ( **optional** )

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/TITLE <name> <password>` | No | N/A | Authenticate for a `WHOIS` title.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

`<titlename="foo" password="bar" title="Official Chat Helper">` 

will appear as

`<nickname> Official Chat Helper`

Format your grammar accordingly.
