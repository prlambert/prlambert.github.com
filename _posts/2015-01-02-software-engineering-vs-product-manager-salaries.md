---
layout: post
title: "Engineering vs. Product Manager Salaries (at Facebook & Google)"
---
*Note (2019): I wrote and published this long before I was hired at Google. I'm keeping it up for historical purposes, but I have not revisted it since publication. I do not endorse any of it today.*

*Note (2015): I originally wrote this in November 2014, to have some data while transitioning out of startupland. It may no longer be accurate.*

Facebook and Google are two of Silicon Valley’s fiercest competitors for talent. So who pays more? Specifically, what do they pay their Software Engineers (SEs) and Product Managers (PMs)? A few weeks ago, I came across a dataset that makes it surprisingly easy to answer this question.

The data is a fortunate byproduct of disclosure requirements around visa sponsorship. As you may know, the H1B is the standard work visa for tech workers in the United States. To get one, an alien worker (like me) needs to get sponsored by a US company (like Facebook, Google, or Twitter) who petitions the government on their behalf. Every H1B petition becomes public domain and includes job title, location, and — most important for our purposes — offered wage.

Since the data comes directly from the US government, I trust it more than the self-reported salaries on Glassdoor. That said, there are still a lot of caveats and holes in this analysis. I’ve listed a few near the end of this article.

## The Data

I’ve sampled and cleaned the data this way:

1. Pulled the H1B petitions for each company in 2012, 2013, and 2014 by scraping tables on [http://visadoor.com/](http://visadoor.com/). For example: [http://visadoor.com/h1bvisa-by-companies-2014-google-inc.](http://visadoor.com/h1bvisa-by-companies-2014-google-inc.)

1. Combined the three years into a single dataset for each company.

1. Kept only petitions that had a status of “Certified”.

1. Considered only salaries quoted annually.

1. Kept only results with the job title “Software Engineer” or “Product Manager”.

## The Results

First, a 5-number summary table:

![](/images/summarytable.png)

And graphically, using a boxplot:

![](/images/boxplot.png)

*If you haven’t read a boxplot in a while, the bottom and top borders of each box are the 25th and 75th percentiles. The line in the middle is the median (50th percentile). The width of the boxes is not significant. The solid lines stretching above and below extend for a maximum 1.5x the height of the box (the [interquartile range](http://en.wikipedia.org/wiki/Interquartile_range)). Samples beyond those lines are considered outliers, shown as dots.*

Now let’s approximate a continuous distribution for the roles at both companies.

![](/images/cdistribution.png)

Overlaid for each role:

![](/images/sedistribution.png)

![](/images/pmdistribution.png)

## Thoughts and Observations

Salaries across positions and companies are pretty close, both in range and distribution. If we’re playing it safe, this is probably the only real conclusion we can draw. There is expected error in all this data that I haven’t quantified. Given how close things are, any further conclusions would be a little sketchy.

But who has any fun playing it safe? Here are my thoughts anyway:

* On the whole, PMs are paid slightly more than SEs. PMs at each company earned more than their SE counterparts by roughly $15,000 at the 25th, median (50th), and 75th percentiles. I believe this is because, generally speaking, PM-roles are more senior, i.e. comparatively there aren’t that many entry-level PM positions. Many PMs start off as SEs and make the jump to product after a few years.

* Top Engineers make more than anyone — the highest salaries at both companies were held by SEs, not PMs. I suspect that this is because great PMs move up the management ladder, become entrepreneurs, etc… while a lot of great Software Engineers want to keep writing code and never move into management.

* Google SEs have a clear two-peak distribution at the $105,000 and $127,000 levels.

* Facebook SEs also have a two-peak distribution, edged slightly to the right of Google’s, with peaks around $110,00 and $140,000. However, the second peak is less pronounced — maybe there are fewer senior engineers at Facebook?

* Despite Google SEs having higher median and mean salaries than Facebook SEs overall, I would argue that “in general” Facebook pays their Engineers more. How’s that? Look at the density plots. It’s as if Facebook’s was made by shifting the Google distribution ~$8000 to the right. The issue is that Google has a number of very high-earning outliers. If you remove the outliers by considering only salaries below $180,000, you’ll find that Facebook has the higher mean and median.

* Facebook PMs have two peaks around $105,000 and $145,000. Google PMs, on the other hand, have a single peak at $140,000. I suspect this is because the entry-level PMs at Google are called “Associate Product Managers” (APMs) and so weren’t included in my dataset, while at Facebook junior PMs may get the “Product Manager” title on their H1Bs (just a guess, I actually don’t know. They do have an APM-equivalent role called “Rotational Product Manager” (RPMs) but that might not be the title on the petitions or there might be relatively few of them).

* The SE:PM ratio at both companies are very similar. 35 Engineers per 1 PM at Google; 40 Engineers per 1 PM at Facebook.

## Caveats and Holes

Naturally there are many factors that undermine the credibility of my conclusions. Here are a few:

* Sample sizes for Engineers are much larger than for Product Managers (e.g. we only have 24 FB PMs vs 3354 Google SEs).

* Titles may not be consistent across companies and even years, and since the sampling is done entirely based on title this is a big deal. Clearly the 95k “Software Engineer” and the 210k “Software Engineer” are not the same seniority. For example, if one company changes titles at either end of the spectrum earlier or later (eg “Junior Software Engineer” or “Lead Engineer”), it would significantly skew the data.

* This data only reflects base salary, not total compensation. Cash bonuses, equity, benefits, and perks are all excluded. Equity can be significant and vested RSUs are nearly as liquid as cash since Google and Facebook are highly traded public companies

* Our samples are taken from H1B filings, i.e. Foreigners applying for work permits in the USA. I would guess that alien workers and Americans are probably paid comparably by these companies for the same job, but this could still have a big impact. For example, it might make our results skew high:

1. There is more friction to hiring a foreigner. The individual needs to be worth the effort of jumping through hoops like the H1B lottery.

1. Many H1B applications are for individuals already working in the US and are changing statuses, for example from an F (student) visa with OPT or, for Canadians like me, from a TN. As such, these salaries don’t reflect the individual’s initial earnings but instead a salary obtained after a few years with the company.

1. For each petition, the federal government sets a “prevailing wage” — what they believe is the average salary for the role, seniority, and location. The sponsoring companies are not allowed to pay below this. They must pay at, or above, the prevailing wage. This sets a minimum bar on these salaries not present for domestic workers.

On the other hand, the H1B sampling could also have the opposite effect:

1. Senior, higher-earning, employees are more likely to have been in the US for longer and already graduated to green cards or citizenship. Put another away, a higher proportion of early-career workers are on H1Bs than mid-to-late career workers so we probably have too many lower-end earners in the sample.

1. Being on an H1B ties your immigration status to your employer — you can’t quit your job or easily move to another one without risking being deported. This severely restricts job mobility and thus power in the labor market for H1B workers.

## Wrapping Up

This was fun, but remember that it’s not all about the money — or even mostly about the money. If you’re lucky enough to be in one of these roles, your job satisfaction and personal happiness is going to be determined much more by your feelings towards the work itself, your relationship with your co-workers, and a bunch of other intangibles. Having said that, I don’t fault anyone for striving to realize their full earning potential. Good luck in that noble pursuit.
