---
id: 18500
title: 'T-SQL Tuesday #186 - Managing Agent Jobs'
date: '2025-05-06T00:00:00+00:00'
author: way0utwest
layout: post
permalink: '/186'
categories:
    - Invitations
tags:
    - '2025'
    - 'administration'
    - 'automation'
---

[Invitation](https://www.flxsql.com/2025/05/06/t-sql-tuesday-186-managing-agent-jobs-invite/) from [Andy Levy](https://www.flxsql.com/)

One of my favorite non-engine features of SQL Server is [SQL Server Agent](https://learn.microsoft.com/en-us/ssms/agent/sql-server-agent?view=sql-server-ver16). It’s been around for a quarter of a century and while it would be wonderful to see some [new features and revisions brought to it](https://datasteve.com/2020/10/02/sql-server-agent-2-0/), it does its job well and keeps on truckin’ - even in [Azure SQL Managed Instance](https://learn.microsoft.com/en-us/azure/azure-sql/managed-instance/job-automation-managed-instance?view=azuresql). For this month’s T-SQL Tuesday, I’d like to know:

**How do you manage and/or monitor your SQL Server Agent jobs?**

This question is intentionally left open to interpretation as I’m hoping to get a variety of takes on it. There are a number of directions this can go, just off the top of my head:

- Keeping job definitions in source control and deploying new/changed jobs from there
- Who is responsible for Agent jobs
- Monitoring and reporting on job success and failures, retries, and runtime performance (beyond the SSMS UI for Job History)
- Packaging the tasks run from jobs in such a way that Agent is “just” a task scheduler
- Setting up permissions and processes so that wide-reaching administrative permissions aren’t necessary to manage individual jobs
- Keeping jobs, other Agent-related objects, and permissions in sync across clusters or your whole environment
- These are just a few possible starting points, and certainly not an exhaustive list nor should you feel like you’re limited to choosing from them. Write about anything you like related to managing Agent jobs.

Again, please publish your post anytime between this going live and midnight (end of day) on Tuesday, May 13th and make sure it gets on my radar as described above, then I’ll get all the responses compiled into one post for everyone to check out.