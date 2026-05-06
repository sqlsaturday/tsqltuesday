---
id: 19200
title: 'T- SQL Tuesday #198 Invitation: Change Detection'
date: '2026-05-05T00:00:00+00:00'
author: way0utwest
layout: post
permalink: '/198'
categories:
    - Invitations
tags:
    - '2026'
---

[Invitation](https://datasavvy.me/2026/05/04/t-sql-tuesday-198-invitation-how-do-you-detect-data-changes/) from [Meagan Longoria](https://datasavvy.me)

This month’s topic is change detection.

## Why change detection?
I’ve been spending a lot of time lately with Fabric Mirroring for SQL Server 2025. One of the things that makes the SQL Server 2025 change feed interesting is how it handles change detection: rather than writing changes to intermediate change tables and having Fabric poll those changes, the change feed scans the transaction log at high frequency and publishes committed changes directly to OneLake. It eliminates a hop and reduces overhead on the source system.

Before Fabric Mirroring existed, incremental loads in data integration projects with source data in SQL Server required Change Data Capture, Change Tracking, or your own high watermark approach. Now my mirrored data lands in Delta tables in Fabric, which have their own Change Data Feed feature.

That got me thinking about how many different ways we’ve all solved this problem — figuring out what changed since the last time we looked — and what issues come up depending on your environment, your workload, and what you actually need to do with the changes.

## The prompt
Share a tip, technique, or lesson learned about how you’ve handled detecting data changes in your technology of choice.

This is intentionally broad. Some angles to consider:

- How do you handle incremental loads in your ETL or ELT pipelines? What’s your watermark strategy, and what edge cases have caused problems?
- Have you used CDC, Change Tracking, temporal tables, or the SQL Server 2025 change feed in a real system? What issues did you run into that the documentation didn’t mention?
- Have you been burned by a particular approach? Missed deletes, timezone issues, LSN gaps after a failover, clock skew between source and destination?
- What does change detection look like in your non-SQL-Server tools (dbt, Spark, Databricks, Azure Data Factory, C# application, etc.)?
- Do you have a script or process that checks for unexpected data drift between two environments?

SQL Server-specific or not, incremental loads or data validation — if it’s about knowing what’s different now versus before, it fits.