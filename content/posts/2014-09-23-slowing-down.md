---
title: Slowing down
created_at: 2014-09-23
author: Peter Hajdu
kind: article
tags: [News]
---

After a boring session of bug fixing yesterday I've started the implementation of the mission system.
As I was digging deeper in the class hierarchy and writing a lot of throw away code I realized that I
was going in the wrong direction. After some contemplation I came up with a few points I want my mission
system to be:

 * easy to create/modify missions
 * open to users
 * fast deployment
 * simple text format

A scripting language! I should have embedded one much earlier, on the other hand I wanted to
have something to play with as soon as possible. I don't think I can delay it further: I will use
lua with some wrapper library I think, but it is not written in stone yet. Cutting to the chase, you
should expect the development to slow down for a while.

