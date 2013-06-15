---
title: Modules &raquo; m_filter
layout: default
---

## Description

Allows filtering of text from private and channel messages and notices, part messages and quit messages, for 
abuse prevention and realtime blocking of viruses and worms. 

## Configuration Tags

To use this module you should add the following tags to your Configuration file:

`<filteropts engine="glob">` and `<include file="filter.conf">`

`<filteropts:engine>` - This variable is to define what matching engine filter will use. The available options are: 

Engine | Description
------ | -----------
glob | Wildcard matching with glob patterns (`*` and `?`). Requires [m_regex_glob](regex_glob.md)
pcre | Regular expression matching with the Perl Compatible Regular Expression engine. Requires [m_regex_pcre](regex_pcre.md)
posix | Regular expression matching with the posix regular expression engine. Requires [m_regex_posix](regex_posix.md)
tre | Regular expression matching with the tre regular expression engine. This is the same regular expression engine UnrealIRCd uses so you may want to use it if you're used to that. Requires [m_regex_tre](regex_tre.md)

You should then create a `filter.conf` file, which contains filter entries. The `filter.conf` is a standard-styled 
config file, containing tags formatted like the one below:

`<keyword pattern="*qwerty*" reason="You qwertied!" action="gline" duration="1h6s" flags="pn">`

`pattern` depends on the regex module used in `<filteropts:engine>`, see the page for the chosen regex module for more
on pattern format.

`<keyword:action>` can be one of the following:

Action | Description
------ | -----------
none | Do nothing except log the match. This is the default if the `action` variable is omitted from the `<keyword>` tag.
kill | Disconnects the user if they match the pattern, giving `reason` as the quit reason. When the tag `kill` is in matches a `QUIT` message, `kill` acts the same as `block`: the user is already disconnecting, there is little point in sending a `KILL`
block | Blocks the whole line and informs all opers with `s` (is this a SNOMASK or a umode?) that the line was blocked, who sent it, and the `reason` text. In the case of `PART` and `QUIT` messages, a reason given by the user that matches a `<keyword>` tag with `action="block"` is replaced with `Reason filtered`, as it is not possible to block the whole `QUIT` or `PART` without desynching clients.
gline | Set a `GLINE` on the user's IP address, lasting for `duration`; otherwise the `GLINE` is permenant if `duration` is omitted from the `<keyword>` tag.
silent | This blocks the line only, and informs the user their message was blocked, but does not notify opers. 

`<keyword:flags>` determines what messages are matched against `<keyword:pattern>`

Flags | Description
----- | -----------
p | Block private and channel messages
n | Block private and channel notices
P | Block part messages
q | Block quit messages
o | **Don't** match against opers
* | Represents all of the above flags
- | Does nothing, a non-op for when you do not want to specify any flags 

## Commands

Command | Oper-Only | Chanop-only | Description
------- | --------- | ----------- | -----------
`/FILTER <filter-definition> [ <action> <flags> [ <gline-duration> ] :<reason> ]` | Yes | N/A | Sets a filter. See [Configuration](filter.md#configuration) for valid values.

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes

This module implements no channel modes.

## Extended Bans

This module implements no extended bans.

## Special Notes

Please note that while glob patterns are faster to match than regular expressions (such a those used in unrealircd, 
etc) **a large number of them can still impede performance** (i.e. a hundred or more). The more users you have, the 
less patterns you will be able to have without crippling your irc server. Filtering is always done locally, so if 
you have over 2000 users per server, consider other alternatives where possible. 

### Listing Filters

The following command will generate a list of all filters currently set:

`/STATS s [servername]`
