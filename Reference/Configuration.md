---
title: Configuration 
layout: default
---

## Introduction

Configuring InspIRCd &mdash;as any other IRCd&mdash; is not an simple task. Since InspIRCd is as
feature-full as it is, there is a lot to configure. But, not to panic, there is this documentation!
Configuration of InspIRCd is done by editing the configuration text file, usually called
*inspircd.conf*. The configuration files are formatted as a XML-like document, which for most people
is somewhat different to what they are used to. The format of an instruction within the
configuration file looks like the following:

    <tagname variable="value">

There may be one or more variables in the tag, each of which must have exactly one value. A variable
must be followed immediately by an equals sign and then it's value in quotes, with no spaces between
the two, as shown in this example. The tagname must contain only alphabetical characters. 

You **do not** require closing tags as in XML.

We provide example configuration files with each InspIRCd release, which are automatically copied in
the configuration directory when you do your install. These examples are the best
configuration-documentation there is, so use them to your advantage! Since these examples cover most
of the things that InspIRCd features, we will give only additional information on this wiki.

## Isn't there an easier way?

New users of InspIRCd are sometimes overwhelmed by the lot of configurable items in our software,
which results in the question above. We try to make installing and configuring as easy as possible.
Many defaults in the example configuration files will work perfectly to begin your IRCd with. It is
very easy to just start reading and change things along, which makes a cool instance of InspIRCd for
you. When you get to the advanced stuff, you can check on the wiki or ask anything in our support
channel.

For those who are still being very lazy or just want to know, the minimum required tags to get an
IRCd running are: `<server>` and `<bind>`, but you probably want a `<oper>` too. This allows you to
run a **very minimal** IRCd.

## Things not to forget

Make sure you keep your syntax right, as described in the beginning of this page. If you don't, you
end up with an IRCd that doesn't want to run and you need to trace back where you left out a quote
or a greater-than sign.

If you want to link several servers, or want to use services, you **must** load the
*m_spanningtree.so* module!

