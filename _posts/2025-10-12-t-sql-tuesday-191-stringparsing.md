---
id: 18900
title: 'T- SQL Tuesday #191 Invitation: Your Favorite String Parsing Routines'
date: '2025-10-12T00:00:00+00:00'
author: way0utwest
layout: post
permalink: '/191'
categories:
    - Invitations
tags:
    - '2025'
    - 't-sql'
    - 'development'
---

[Invitation](https://voiceofthedba.com/2025/10/12/t-sql-tuesday-191-invitation-your-favorite-string-parsing/) and [roundup](https://voiceofthedba.com/2025/10/28/t-sql-tuesday-191-round-up/) from [Steve Jones](https://voiceofthedba.com/)

Your Favorite String Parsing Routines
One of the things that I’ve had to do a log in my career is parse strings in different ways. It seems our customers constantly find new ways to stick data into a string that we would prefer to have normalized in some way for searching, indexing, etc.

As a few examples, we might get someone who creates a PO that looks like 20260720321433, where there’s a year/month to start and then a number. We might need to parse either the number or the date from the field to determine when or which count of a PO someone has made. Other examples might be someone putting “Sam Jones” in the last name (surname) column because there isn’t a middle name space. We might need to get just the last name out of the field.

This year (2025) I’ve been using AI often to try and get data from various structures, often PDFs or more complex formats, but I have managed to ask AI to change a bunch of data in a field across different rows rather than try and work out some RegEx search and replace. That got me thinking.

What are your favorite string parsing routines that have helped you handle complex situations? That’s your invite for Oct 2025. Write on a way that you’ve handled parsing (and maybe replacing values) in complex strings.

I see questions on things all the time at SQL Server Central. A few examples:

[Doe, Jane E] [Doe Smith, Jane E] (get the without middle/initials/etc)
[Hello5-E-100] (get the final number)
192.168.1.100 – parse IPv4 (or v6) addresses
Parse XML for a value
Parse JSON for a value
[8/9/08 – out for upgrade; 8/16/08 returned to inventory. 8/31/2008 – deployed to field] – parse out all the dates
Write on Oct 21, 2025, a week late, and post a comment on this post linking back to your entry. I’ll compile everything next week for the roundup.