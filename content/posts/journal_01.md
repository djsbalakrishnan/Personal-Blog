---
title: "Journal #01"
date: 2025-05-18T11:54:31+05:30
draft: false
description: ""
tags: [Journal, NewsLetter]
---
 
### 🔧 LeetCode Problem of the Week
This week's LeetCode problem is pretty straightforward, but it hits on a really fundamental idea in DSA.

You can find the problem right here: [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)

> Given an integer array, return true if any value appears at least twice in the array, and return false if every element is distinct.

Now, there are a couple of ways to solve this.

One of the first things you might think of is to sort the array. If we put all the same numbers next to each other, then we can just iterate through the sorted array and see if any adjacent values are the same. While it is easy to visualize, the thing to keep in mind here is the time it takes to sort. Most of those built-in sort functions take O(nlogn) time under the hood, and that might not be the most efficient way.

Then there's another trick we can use with a HashSet. They have this property where they don't allow duplicates. So, if we add all the numbers from our array into a HashSet, it will just ignore the duplicate values. So, if the original array had any duplicates, the number of elements in our HashSet will end up being smaller than the length of the initial array. The Time Complexity for this solution will be O(n) which is better than the previous approach.

### 🌍 Projects & Articles I’m Excited About
I'm currently tinkering with my News Summariser project. Basically, it grabs the top 15 to 20 articles from places like Hacker News and TLDR, filters them based on simple keywords and upvotes, and then shoots them to my Telegram bot.
![Existing_Workflow](/images/Existing_Workflow.png)

It's been pretty handy for over a year now, but I've been wanting to make a couple of improvements.
- If you've ever glanced through Hacker News, you might have noticed that folks usually just share a link to an article. What I'm thinking of doing is adding a script that can scrape data from the link, summarize the content, and then share the summary instead of just the plain link.

- Also, there have been multiple instances where I've seen the same article pop up for a few days in a row. While I could just ignore the duplicates, I'd like to dedupe them by adding an Airtable layer to check if an article has already been shared.

![Future_Workflow](/images/Future_Workflow.png)

I'll definitely keep you posted on how these updates go. In the meantime, here are a couple of links to articles that caught my eye this past week. Check them out when you have a moment:

- [Dotless](https://lab.avl.la/dotless/)
- [Opt Out of AI](https://theconversation.com/avoiding-ai-is-hard-but-our-freedom-to-opt-out-must-be-protected-255873)


### 🛠️ Essential Resources for Software Engineers
As cliché as it might sound, I will 100% recommend a simple notepad and a pen to list down tasks to complete in the day.

![Notebook_Pen.png](/images/Notebook_Pen.png)

My routine is to start my day by listing down all the items for the current day, and my sources for these tasks usually are:

- Pending tasks from yesterday
- Scheduled Meetings
- My Ideal Calendar [got this idea from Ali Abdaal]

I then list these tasks on a makeshift calendar on my notepad. This helps me in prioritizing tasks, and I am never left thinking about what I should be doing at any given point in time. This also helps me decline ad-hoc requests that come my way throughout the day.


### 🎧 Music to Fuel Your Work
This week, I had [Ulagam Oruvanukka](https://music.youtube.com/watch?v=Fk7YoS0U7X4&si=U_XT7VE8vbN5fruc) from Kabali on loop, and honestly, the segment from 2:24 to 3:00 just hits different. Give it a listen if you need a mid-week energy boost!

And with that, I’m wrapping up Journal #01.
Catch you next week!

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
