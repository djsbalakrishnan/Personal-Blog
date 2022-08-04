---
title: "Ipl Analytics"
date: 2020-07-10T22:22:34+05:30
draft: false
description: "We’ve all been engulfed by the uncertainty that is COVID-19. It doesn’t seem to be going anywhere anytime soon. Of all the stuff that has come to an indefinite standstill, sporting action, especially cricket is something that we are missing the most."
tags: [Analytics]
---

![Dharamshala](images/IPL.jpg)

### Overview

We’ve all been engulfed by the uncertainty that is COVID-19. It doesn’t seem to be going anywhere anytime soon. Of all the stuff that has come to an indefinite standstill, sporting action, especially cricket is something that we are missing the most.

It is now that time of the year where we would ideally be getting out of a hangover from the IPL. I have been an avid follower of the Indian Premier League from its inception, so much so that I wanted to fill in this void of having no IPL by looking at some of its data points and this exercise led me to build a [side project](https://nbviewer.jupyter.org/github/djsbalakrishnan/IPL-Analytics/blob/master/notebooks/IPLAnalytics.ipynb).

Here’s some number crunching from IPL over the years if you’ve been dying for that cricket fix of yours

### Analysis so far!!
You can find the notebook [here](https://nbviewer.jupyter.org/github/djsbalakrishnan/IPL-Analytics/blob/master/notebooks/IPLAnalytics.ipynb)


### Batsman Statistics
- [x] Most Runs
- [x] Most Runs (over)
- [x] Most Fours
- [x] Most Fours (innings)
- [x] Most Sixes
- [x] Most Sixes (innings)
- [x] Most Fifties
- [x] Most Centuries
- [x] Hightest Scores (innings)
- [x] Best batsman in powerplay
- [x] Best batsman in death overs (last 4 overs)
- [x] Best Batting Strike Rate
- [x] Best Batting Average
- [x] Bowler vs Batsman Head to Head Competition
- [x] Top 4 Batsman Score comparison

### Bowler Statistics
- [x] Bowler providing most extras
- [x] Most Wickets
- [x] Most Maidens
- [x] Most Dot Balls
- [x] Most Dot Balls (innings)
- [x] Most Runs Conceded (Innings)
- [x] Best Bowling Economy
- [x] Best Bowling Economy (innings)
- [x] Best bowler in powerplay
- [x] Best bowler in death overs (last 4 overs)
- [x] Best Bowling Innings
- [x] Bowler Wicket Taking Kind Percentage

### Feilder Statistics
- [x] Best Fielder

### Data Source
- CricInfo
- Kaggle
- CricSheet
- IPL T20 Official Website

### Data Information

We have two different CSV files that are imported as inputs.
- matches.csv
- deliveries.csv

### Matches

It has a total of 18 features, out of which 12 of them are categorical, 5 of them are numerical and 1 is a date field. It had a few data discrepancies which I am listing below for reference.

| Feature | Type | Remarks |
| ------ | ---- | ------- |
| city | category | It had duplicate values for Bangalore (Bengaluru) and Chandigarh (Mohali). It also had 7 null values, each of these had venue as Dubai. |
| team1, team2, toss_winner, winner | category | It had duplicate values for Rising Pune Supergiant (Rising Pune Supergiants) team |
| winner | category | It had 4 null values; they correspond to matches which had no result. |
| player_of_match | category | It had 4 null values; they correspond to matches which had no result. |
| venue | category | It had a lot duplicate values. For example, we had duplicates for Rajiv Gandhi International Stadium, Punjab Cricket Association IS Bindra Stadium, M. A. Chidambaram Stadium, M Chinnaswamy Stadium and Feroz Shah Kotla. |
| umpire1, umpire2 | category | It had 2 null values. I found those values from Cricinfo |

**I could reduce memory consumption by 30% by typecasting the features to valid datatypes** 

### Deliveries

It has a total of 21 features, out of which 8 of them are categorical and 13 of them are numerical. It had a few data discrepancies which I am listing below for reference.

| Feature | Type | Remarks |
| ------ | ---- | ------- |
| inning  | int64 | I have no idea how an innings value be equal to 5. I could not understand this feature completely | 
| batting_team, bowling_team | category | It had duplicate values for Rising Pune Supergiant (Rising Pune Supergiants) team |
| total_runs | int64 | It had a lot of entries where the total_runs was more than 7 |

**I could reduce memory consumption by 22% just by typecasting the features to valid datatypes.**

### Contribution
PRs on new Analytics, Bug fixes are welcome. Feel free to open an issue.


### License
[CC](https://creativecommons.org/licenses/by-nc-sa/4.0/)


### Disclaimer
This tool is only intended for personal use and is a simple demonstration.
