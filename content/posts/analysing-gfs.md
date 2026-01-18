---
title: "Analysing GFS"
date: 2026-01-11T00:00:00+05:30
draft: false
description: "Why did Google build a file system with a single point of failure? I break down the GFS architecture, its trade-offs, and how it paved the way for modern Big Data systems like HDFS."
tags: ["Whitepaper Analysis", "Data Engineering"]
---

Distributed systems aren't learned by memorizing definitions. They are learned by studying the trade-offs made by the giants.

The **Google File System (GFS)** paper (2003) is the grandfather of modern Big Data (HDFS, S3, **Colossus**). But let's be honest—reading a 15-page academic paper is dry.

I spent the weekend breaking down the paper and annotating the critical architectural decisions.

### 1. Download the Annotated Paper
Here is the original paper with my highlights.

<a href="pdf/GFS_Research_Paper.pdf" target="_blank"><strong>Download Annotated GFS Paper (PDF)</strong></a>

---

### 2. Session Notes (Update: Jan 18)
**The live deep-dive is now complete.** We spent 90 minutes today breaking down the "Kohli Highlights" analogy, the GFS Write Flow, and the evolution to Colossus. 

If you missed the session (or want to review the diagrams), I have compiled the full lecture notes and slides below. These cover the specific consistency guarantees and the "Choreographed Dance" of the primary/secondary replicas.

<a href="pdf/GFS_Notes.pdf" target="_blank"><strong>Download Session Notes & Slides (PDF)</strong></a>

*See you in the trenches.*