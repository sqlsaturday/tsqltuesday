---
id: 26600
title: 'T-SQL Tuesday #201 Invitation: Temp Tables, Friend or Foe?'
date: '2026-08-04T00:00:00+00:00'
author: way0utwest
layout: post
permalink: '/201'
categories:
    - Invitations
tags:
    - '2026'
    - 't-sql'
    - 'performance'
---

[Invitation](https://www.jefftaylor.io/post/t-sql-tuesday-201-invitation-temp-tables-friend-or-foe) from [Jeff Taylor](https://www.jefftaylor.io/)

Recently, I was tuning a stored procedure for a client and ran into a pattern I encountered repeatedly. This one was a doozy. The query pulled 250+ million rows into a #temp table, then joined it back to itself, all to return one row. To answer a single-row question, it moved roughly 5GB of data through tempdb. To top it off, this was called thousands of times a day.

Let that sink in. 5GB of writes for one row.

The base table already had the indexes and statistics to query this fast. Everything the optimizer needed was right there. So I pulled the temp table out and rewrote it with a simple IF EXISTS against the existing indexes. Same answer. This time it moved 16KB. From 5GB to 16KB, just by not copying data, the engine already knew how to find.

I recently gave a session on tempdb, and this was one of the things I drove home. 

So, what is your opinion? Do you use temp tables?

The claim I'll defend

Here is my opening position, and I'll say it plainly: reaching for a temp table should be the exception, not the reflex.

Moving data into a #temp table, then adding an index to it, is a lot of extra work. You copy the rows. You write to tempdb. You build a new index from scratch. You generate fresh statistics. And you do this every time you run that stored procedure or query. In a lot of the code I see, all that effort recreates, poorly, what already existed in the source table. Using the indexes and statistics you already have, without moving the data, is usually faster.

That's my verdict. I think temp tables are used too freely, especially by developers who learned the "materialize it into a #temp first" habit and never questioned it.

The version I see most often is the worst: pull every column and every row into the #temp table, then work from that copy. In my opinion, that is never the right answer. If you truly have to stage something, stage a small set of IDs, a key list you'll probe against, not the entire result set with every column along for the ride. And even then, I'd reach for other tools first: a join back to the base table, an EXISTS, the correct index, and a window function. Copying the entire table or dataset into tempdb so you can search it again is backward. The haystack already had an index.

I'm not here to tell you temp tables are evil, or am I...I think "it depends", and in my experience, I have rarely used temp tables.

What I'd love you to write about

Pick whatever fits your world. A few prompts to get you going:
- A time a temp table rescued a query. What was the plan doing before, and what did materializing the data change? Show the numbers.
- A time you ripped a temp table out and the set-based query on existing indexes won. Same ask: show me the before and after.
- Your rule of thumb. When do you reach for a #temp table, and when do you refuse? How do you decide?
- The whole family. #temp vs. table variables vs. CTEs vs. indexed views. When does each one earn a spot?
- The tempdb side of the story. Contention, spills, statistics recompiles, the cost nobody sees until tempdb is on fire.
- The developer habit. Is "load it into a #temp and index it" a reasonable pattern, a code smell, or both, depending on the day?

Test it on your own hardware if you can, and bring the evidence. Execution plans, logical reads, durations, whatever tells the story. I'd rather read one measured example than ten opinions, my own included.

Disagree with me completely? Even better. Tell me why I'm wrong and back it up. That's the fun of this one.
