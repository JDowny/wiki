---
title: Modules &raquo; m_override
layout: default
---

## Description

Provides the ability for opers to 'override' things such bans, mode changes, etc. 
m_override can also specify the exact types of 'modehack' which are to be allowed for each oper type. 

## Configuration Tags

### Module Configuration

`<override noisy="yes" requirekey="yes">`

`noisy`: Announces all overrides in SNOMASKS as well as in the channel being overriden (via channel `NOTICE`)

`requirekey`: Forces Opers to override-join by using the channel key "override" to prevent accidental overrides. i.e.: `/join #secret override`

### Oper Configuration

The override module adds a new value to the `<type>` tag which specifies exactly what an oper may override. The tag is `<type:override>` and is specified in the following manner:

    <type name="NetAdmin"
    classes="OperChat BanControl HostCloak Shutdown ServerLink Services HostChange Modular"
    host="netadmin.chatspike.net"
    override="INVITE KEY LIMIT BANWALK KICK MODEOP MODEDEOP MODEVOICE MODEDEVOICE MODEHALFOP MODEDEHALFOP OTHERMODE">

You may have as many override tokens in the override variable as you wish, each of which allows the oper to override a specific IRCd setting as shown in the table below:

    INVITE       - Allows an oper to override a +i mode set on any channel
    KEY          - Allows an oper to override a +k mode set on any channel
    LIMIT        - Allows an oper to override a +l mode set on any channel
    BANWALK      - Allows an oper to override bans (of any type) mode set on any channel, basically any JOIN prohibition not covered by INVITE, KEY or LIMIT
    KICK         - Allows an oper to KICK even without channel (half)operator status
    MODEOP       - Allows an oper to op himself or others without channel operator status
    MODEDEOP     - Allows an oper to deop himself or others without channel operator status
    MODEVOICE    - Allows an oper to voice himself or others without channel (half)operator status
    MODEDEVOICE  - Allows an oper to devoice himself or others without channel (half)operator status
    MODEHALFOP   - Allows an oper to halfop himself or others without channel operator status
    MODEDEHALFOP - Allows an oper to dehalfop himself or others without channel operator status
    OTHERMODE    - Allows an oper to set any channel mode not directly covered by MODEOP, MODEDEOP, MODEVOICE, MODEDEVOICE, MODEHALFOP or MODEDEHALFOP, without the necessary channel (half)operator status.
    TOPIC        - Allows an oper to change any channel topic without ops or being in the channel. 

NB: Using the value `*` for override (`override="*"`) enables **all** override types. Use with **caution**.

## Commands

This module does not implement any commands.

## User Modes

This module does not implement any user modes.

## SNOMASK

SNOMASK | Description | Oper-Only
------- | ----------- | ---------
v | Can receive notices about use of oper-override even if `<override noisy="no">`. | Yes

## Channel Modes

This module does not implement any channel modes.

## Extended Bans

This module does not implement any extended bans.

## Special Notes

None.
