---
title: "Journal #03"
date: 2026-01-24T13:30:00+05:30
draft: false
description: ""
tags: [Journal, NewsLetter, System Design]
---

### 🔧 LeetCode Problem of the Week

This week, we're diving into a LeetCode question that looks simple on the surface but is actually a perfect proxy for understanding how we handle memory constraints. Here’s the question:

> Given an array `nums` containing `n` distinct numbers in the range `[0, n]`, return the only number in the range that is missing from the array.

You can find the problem right here: [Missing Number](https://leetcode.com/problems/missing-number/)

Now, the brute-force instinct is to sort the array first. But standard sorting takes `O(n log n)` time. In a system processing millions of entries, that CPU cost is too expensive.

The next logical step is to use a `HashSet` to store all values and check what's missing. That drops the time to `O(n)`, but it costs `O(n)` in extra memory. If you are working on an embedded system or a high-throughput data pipeline, doubling your memory footprint just to find a single missing value is unacceptable.

So, how do we solve this in **linear time** with **zero additional space**?

We go down to the metal and use **Bit Manipulation**, specifically the `XOR` (Exclusive OR) operator. 

The fundamental property of XOR is that XORing two identical numbers cancels them out (returns 0), and XORing any number with 0 returns the number itself. If we XOR all the indices `[0 to n]` and then XOR that result with all the values present in the array, the duplicates will cancel each other out. The only value left standing will be our missing number. 

It is a beautiful, highly efficient solution used frequently in network packet reconstruction and data integrity checks.


### 🌍 Projects & Articles I’m Excited About
I’m currently writing this from Chennai, spending the Republic Day long weekend with my mother. 

As software engineers, we talk a lot about "Garbage Collection" and "Technical Debt" in our codebases, but we rarely apply it to our physical lives. This weekend, my main project isn't on a screen. It’s helping my mom do a massive physical refactoring of the house; auditing the kitchen, organizing the top shelves, and purging old books to donate to the local library. Clearing physical clutter has a direct correlation to clearing mental bandwidth. 

On the professional front, I’m heavily utilizing what I call the "Double-Dip Strategy" (a variant of the Feynman Technique). Lately, I've been helping a few friends and peers prep for their interviews by breaking down fundamental computer science concepts for them. Instead of just brushing up on the basics to help them out, I am using this as a forcing function to master the absolute hardest, edge-case variations of those topics for my own Staff-level upskilling.

If you want to master a complex topic like Distributed Transactions or Consistent Hashing, don't just read about it; try explaining it to a room of 50 engineers. That is the ultimate test of knowledge.


### 🛠️ Essential Resources for Software Engineers
- [Memento Mori Dashboard](https://www.dhirajbalakrishnan.dev/memento-mori/) - I just built this live life-calendar. It visualizes the exact weeks of your life passing by. It is the ultimate productivity hack, when you see your life's weeks ticking away on your screen, you stop wasting time on useless meetings and start building.


### 🎧 Music to Fuel Your Work
I have been listening to [The One](https://music.youtube.com/watch?v=9TvBBYmhd14) on loop lately. The rap section in this song hits hard.


Cheers!


<div style="padding: 20px; display: flex; justify-content: center;">
    <iframe 
        src="https://djsbalakrishnan.substack.com/embed" 
        width="480" 
        height="150" 
        frameborder="0" 
        scrolling="no"
        style="display: block; margin: 0 auto;"
    >
    </iframe>
</div>

