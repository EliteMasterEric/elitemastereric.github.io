---
layout: post
title: What is the Least Interesting Number?
date: 2023-02-24
tags: projects
---

*An interesting condundrum.*

On February 24, 2023, Tyler Glaiel made [this tweet](https://twitter.com/TylerGlaiel/status/1629220118856339457).

![](/images/lin-1.png)

{:.imagecaption}
*what's the least interesting number between 1 and 1000*

This tweet intrigued me, since many of the people in the comments were simply proposing their uninteresting numbers in the comments. The tweet is in reference to the [interesting number paradox](https://en.wikipedia.org/wiki/Interesting_number_paradox), which posits that no specific number can be itself uninteresting, because that would be an interesting fact about it. Other approaches had been proposed in the past, such as one which analyzes the On-Line Encyclopedia of Integer Sequences.

I, however, proposed an approach which sought to analyze the cultural significance of numbers in an emperical manner to determine the final answer; analyzing documentation on the number on sites such as Google and Wikipedia. I then received this reply:

![](/images/lin-2.png)

{:.imagecaption}
*Wait, THE VSauce?*

Now I have to see this through, I won't let you down, Michael.

## Debating Possible Approaches

When working on this, I had to first determine what it meant for a number to be interesting or uninteresting before I continued. The key to my approach was the idea that an interesting number has a lot of discussion surrounding it. For example, `666` is an interesting number because it is depicted in the Bible as "the number of the beast," and therefore a lot of discussion surrounds it.

Fun fact, fear of the number `666` is known as **hexakosioihexekontahexaphobia**. See? That's interesting.

I now had a different problem: How do I quantify how much a given number is discussed? I had two ideas for solving this:

- Search the number on Google, fetch the number of results provided. The more results means the more the number is discussed and the more interesting it is.
- Find the number's Wikipedia article (for example, [555 (number)](https://en.wikipedia.org/wiki/555_(number)), since the page titled `555` is reserved for the page detailing the year `555` of the Gregorian Calendar) and get the word count of that page. Longer word counts would mean more detailed trivia and knowledge surrounded the number, and therefore was more interesting.

Ultimately, my goal was to find the number with the LEAST discussion surrounding it, which therefore was the least interesting.

## Approach #1: Google

I ended up creating an application using Haxe (my programming language of choice) which integrated with [Apify](https://apify.com/), a service for web scraping providing support for a variety of target sites. I had to use this service since Google does not provide any public web search API itself (surprising, since practically all its other services have robust and powerful REST clients).

My application does the following:

- Authenticates and connects with Apify.
- Creates a job with the `apify/google-search-scraper` actor.
- Sends a request to search for a given set of terms. For example, it would perform a search query for `666`.
- Apify handles performing the request, including managing workers and concurrency.
- Apify then sends the resulting data back to my application.
- My application retrieves the query result count and writes it to a spreadsheet for interpretation.

This worked swimmingly, but I'll save the final results for later.

## Approach #2: Wikipedia

I wanted to get results from my other proposed approach as well, but this came with its own complications.

Apify thankfully has its own scraper dedicated to Wikipedia, however I found a particular issue with the scraper that complicated the process.

As noted by Michael, `198` does not have its own Wikipedia page. Rather, it does, but instead, `198 (number)` redirects to the page for `190 (number)`, at the section on "Integers from 191 to 199". 198 receives a few sentences here, so this counts, and other higher numbers are also redirected this way, such as `712 (number)`, but this data is more difficult to scrape automatically.


## RESULTS

Here we go, the info you've all been waiting for!

The least interesting number is **894**

![](/images/lin-result-1.png)