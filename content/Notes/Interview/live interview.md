---
title: Version 1
draft: true
tags:
date: 30-Aug-2025
---
## Data Science Lifecycle
1. frame a problem
	1. purpose of underlying problem statement
	2. e.g. why we need to customize telecom customer data?
2. understand the domain knowledge
3. collecting data
	1. how much data is enough
	2. are all data covering existing scenarios
	3. do I need new data
4. data processing
	1. cleaning raw data
		1. numerical data
		2. text data
	2. data formats need to align into single format
	3. clean data
5. understand the existing data (EDA)
	1. how many rows, cols
	2. how many outliers 
6. ML algorithms
	1. develop at least 2-3 models
	2. evaluate accuracy
	3. train test split 70-30
7. deployment
## if don't have enough data
1. understand the domain
	1. create some situations to get the data and compare it with the dataset, check the situations are covered or not
2. artificially prepare the data
## how do you justify that the data that you have is sufficient or not
2 scenarios
1. data is not available
2. data is sufficient or not

Suggestion
1. through data visualization in exploratory data analysis, if data is biased towards certain features, we can gather data is insufficient areas 
	1. balance the imbalanced dataset with extra weight in the imbalanced areas

## if one column having many missing values
1. missed certain fields when collecting data
2. data is not available

if data is numerical mean is used 
if data is categorical then with level mode is used

## if some values are very high and others are very low
if they are outliers we need to remove it

## in a team how ml projects are divided into team members and what tools are used for team collaboration?

## poker
psychology + math + randomness
it is expected to have no optimum solution, but there is.

## What are some features we should investigate regarding the bot issue?
1. content of post
	1. accounts  tagged
	2. keyword hashtags
	3. timing of the post
	4. words mentioned in the post
	5. links
	6. images
2. accounts making the post
	1. # followers
	2. # accounting followed
	3. ratio of # follow vs # followers
	4. are the followers spam accounts?
	5. content of account posts
	6. how many times reported spam
	7. email address
3. aggregated things
	1. spike in the # post in 5 min interval
	2. similarity  of posts in small time frame

## what would a dataset to train models  to detect bots look like? How would you approach collecting the data?

How many times reported spam - how we can label spam
naive labeling system
1. reported spam # of times = label as spam
2. no reports of spam = label as not spam

implementation approach to detect bot accounts
1. # followers
2. # following
3. # spam reports
4. value for email 
	1. basic encoding
		1. 1 for gmail, hotmail, yahoo
		2. 0 for otherwise
	2. more complex encoding
		1. try to develop a linear classifier
		2. domain name (one-hot encoded)
		3. 0/1 whether or not common names/words appear in email
5. content of post
	1. post #1, post #2, ... , post #10 
	2. # spam  reports
	3. accounts  tagged
	4. keyword hashtags
	5. timing of the post (milliseconds since epoch)
	6. one hot encoding of common spam words (claim, free, buy)
	7. links

one hot encoding
- `[gmail.com, hotmail.com, yahoo.com]`
- something@gmail.com =`[1,0,0]`1
- something@hotmail.com = `[0,1,0]`
- something@yahoo.com = `[0,0,1]`
- something@random.com = `[0,0,0]`

milliseconds since epoch = some integers since 1950 or something like that