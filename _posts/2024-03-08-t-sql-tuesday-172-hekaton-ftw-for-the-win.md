---
id: 4640
title: 'T-SQL Tuesday #172: Hekaton FTW (For the Win)!!!'
date: '2024-03-08T05:52:24+00:00'
author: way0utwest
layout: post
permalink: '/172'
categories:
    - Invitations
tags:
    - t-sql
    - '2024'

---

[Invitation ](https://toddkleinhans.wordpress.com/t-sql-tuesday-172-hekaton-for-the-win-ftw/)from [Todd Kleinhans](https://toddkleinhans.wordpress.com/).

## First off, what in the world is Hekaton?

Hekaton was the internal project name within Microsoft to implement in-memory tables (IMOLTP) both with and without persisting data to disk (more on that aspect later); it was designed with a completely latch-free and lock-free data structure based on timing. Short version- if implement correctly and properly, it would give fantastic performance if used properly and correctly.

From what I have gathered over the years, it was announced with great fanfare and I even have a signed copy from Kalen Delaney of her book on the subject!

<figure class="wp-block-image">[![](https://toddkleinhans.files.wordpress.com/2017/11/12.jpg?w=1024)](https://toddkleinhans.files.wordpress.com/2017/11/12.jpg)</figure>## Enter Stage Left – Sad Trombone

So if this shiny new and awesome hammer was built and introduced, why didn’t it take off like wildfire? I was incredibly hopeful for a variety of reasons that will come out shortly but sadly disappointed- but then like a phoenix rising from the ashes, it once again has relevance in my daily life as a SQL Server DBA at my current employer. Slowly but surely, starting off with tempdb metadata performance using IMOLTP this is about to become an intense ride.

## Are You Using Hekaton? How is it working?

I realize Hekaton is an edge-case scenario for many and yet those who need it have been waiting for several years for it to be fully implemented, regression tested, and be able to sell this awesome capability to upper management with zero to little risk.

## Your Mission- Make the Case for Hekaton

How are you using Hekaton? Hits, misses, etc. – What went well and what went poorly?

Please let the community know so that we can learn from each other and have the strength and encouragement to make things better than when we inherited it.

At my current employer we are about to test and implement tempdb metadata using IMOLTP. I have future plans for using Hekaton inside of containers on a customer by customer basis in addition to some other GPU go-fast magic. More to come…