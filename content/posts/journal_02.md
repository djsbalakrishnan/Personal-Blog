---
title: "Journal #02"
date: 2025-06-01T12:15:21+05:30
draft: false
description: ""
tags: [Journal, NewsLetter]
---

### 🔧 LeetCode Problem of the Week

This week, we're diving into a LeetCode question that, while simple, really gets you thinking about different approaches. We'll break down a few ways to solve it and then land on the most optimized one. Here’s the question:

> Given an array `nums` containing `n` distinct numbers in the range `[0, n]`, return the only number in the range that is missing from the array.

You can find the problem right here: [Missing Number](https://leetcode.com/problems/missing-number/)

Now, one of the first ideas that might pop into your head is to sort the array in increasing order. Then, you could just iterate through the sorted array to find that missing number. It’s easy to visualize, right? But here’s the catch: the built-in sorting algorithm is often the bottleneck, typically taking `O(n logn)` time.

If we want to optimize this further, we could try using a `HashSet` to store all the values from the array. Then, we can run a loop from 0 up to the array's length to figure out which number didn't make it into our set. The trade-off here, though, is the additional space we use.

So, is there a better way? Can we solve this problem in linear time complexity with no additional space used?

Yes, we absolutely can, by tapping into the magic of Bit Manipulation, specifically the XOR operator. The core idea here is that XORing two identical numbers always results in 0.

Think about it.


### 🌍 Projects & Articles I’m Excited About
Lately, I've been doing a fair bit of traveling, attending weddings, catching up with family and close friends. It’s been tough to carve out time for personal projects, let alone manage critical office projects and teach when I find the time.

Having said that, being the only Software Engineer in the family pretty much makes you the dedicated technical support. My main task for this trip? Reorganizing my mother’s laptop.

Picture this: over 2,000 documents - everything from question papers and reference books to attendance sheets and rank reports, scattered across multiple directories like OneDrive, Downloads, Documents, and Desktop. Yeah, a real digital jungle.

Manually sitting down to sort all those files? No way. That would have eaten up hours of my time. My best bet was to first figure out how my mom ideally wanted her directory structured, and then identify keywords to categorize the mess.

After understanding her requirements, I sat down and created the desired empty directory structure. Then, I copied all the source files and folders into a single location. Deduplicated them based on their file names, and wrote a Python script that would walk through the source location, read each file's content, and then, based on keywords, move them to their desired destination.

Even after running this script, we still had about 150 files that either didn't contain any keywords or whose content the script couldn't read. Since I had zero intention of maintaining this script, I did not enhance it. Rather, I asked my mom to open each of those remaining files and rename them with a prefix that would allow me to move them easily to its destination. This made my life a lot easier, and we successfully tackled what had been a major pain point for her.

### 🛠️ Essential Resources for Software Engineers
As software engineers, we spend most of our time staring at either our code editor or the terminal. Personally, I use VS Code as my primary editor, and here are a few extensions I highly recommend to level up your workflow:

- [Python (by Microsoft)](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
- [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- [Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)
- [Prettier - Code Formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [Flake8 Lint](https://github.com/microsoft/vscode-flake8)


### 🎧 Music to Fuel Your Work
I have been listening to [Megamo Aval from Meyaadha Maan](https://music.youtube.com/watch?v=GGE7I99eRAI) on loop lately. Seriously, Pradeep Kumar's voice is just pure therapy. If you get a chance, I absolutely recommend listening to this one with your eyes closed.

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

