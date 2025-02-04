---
id: 18300
title: 'T-SQL Tuesday #183 - Managing Permissions'
date: '2025-04-04T00:02:00+00:00'
author: way0utwest
layout: post
permalink: '/183'
categories:
    - Invitations
tags:
    - '2025'
    - 'SQL Server'
    - 'Security'
---

[Invitation ](https://voiceofthedba.com/2025/02/04/t-sql-tuesday-183-invite-tracking-permissions/) from [Steve Jones](https://voiceofthedba.com/)

Managing Database Permissions
One of the things I see lots of people struggle with is the database permissions for their logins/users. DBAs or Ops people are always getting requests to add people, rarely requests to remove people, and not often enough, requests to audit who has permissions.

Lots of systems that live for years have people with too many permissions but no one knows this.

It could be SQL Server, Oracle, CosmosDB, RDS, PlanetScale, etc. Well not that last one, they haven’t been around for years, have they? They have, since 2018, so maybe people do have this issue in MySQL.

Ultimately, we have to audit or understand permissions at some point. Or we need to update permissions. This could be a developer task (as they add/change objects) or it could be strictly Operations. I’ve seen both.

This month, I’m wondering how you track permissions, which I assume involves some code. Show us a good way to do any of these:

- check permissions
- update permissions
- add new logins/users across systems
- remove people
- report on permissions at various levels (user, object, database, etc.)