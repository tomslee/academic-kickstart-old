---
author: Tom Slee
comments: true
date: 2016-02-26 21:09:23+00:00
excerpt: "\n\t\t\t\tLooking back at the Airbnb report that Murray Cox and I did earlier\
  \ this month, now that Airbnb admits we were right...\t\t"
layout: post
link: http://tomslee.net/2016/02/wrapping-up-personal-notes-on-the-airbnb-report.html
slug: wrapping-up-personal-notes-on-the-airbnb-report
title: "\n\t\t\t\tWrapping up: personal notes on the Airbnb report\t\t"
wordpress_id: 3715
---


				_Looking back at [the Airbnb report](http://tomslee.net/how-airbnb-hid-the-facts-in-nyc) that Murray Cox and I did earlier this month, now that [Airbnb admits we were right](http://fusion.net/story/272780/airbnb-new-york-data-purge/)..._

It was the beginning of [December](https://www.airbnbaction.com/data-on-the-airbnb-community-in-nyc/) when Airbnb released data about its listings in New York City,  but it was early January before I had time to properly compare my own data to theirs. Pretty soon, I noticed an anomaly: what looked like a significant jump in the proportion of single-listing hosts between two surveys I had carried out, either side of the November 17 date Airbnb chose as a seemingly-random snapshot of their business. Murray Cox regularly collects data on Airbnb listings too at [Inside Airbnb](http://insideairbnb.com), so we talked about it. He looked at his data and thought he saw the same. So that's interesting, we thought...

Then it was several weeks of questioning. We looked again and again at data reliability, we checked and cross-checked calculations, and we mulled over alternative explanations.  There is good reason to expect Airbnb to be misleading: there is $25 Billion in fortunes to be made through a good IPO, and that's a lot of pressure to make things look better than they are. But incentives are one thing, and reality is sometimes another. Airbnb routinely calls our data sets inaccurate (see [here ](http://www.theverge.com/2015/1/21/7865959/airbnb-under-fire-new-york-city-city-council)and [here](http://www.capitalnewyork.com/article/city-hall/2015/02/8562038/scraped-airbnb-data-shows-58-listings-possibly-illegal), for example), and even though comparisons to Airbnb's own selective data releases have made us fairly confident, I did worry that going big on a story may set us up for failure and embarrassment if we had missed something obvious.

First we asked ourselves: if these listings were actually removed, is this a story? Yes, we thought. If Airbnb removed listings immediately before making a "public data release" and never once mentioned doing so, it seemed like a clear case of using data to mislead, and given the high profile of the company's original data dump (two New York Times stories, and many others) someone should be interested.

Can we prove that the changes are not just noise? I scan the Airbnb web site for NYC periodically, but a survey I did in early November had given bad results (for boring technical reasons) so the bracketing data sets I had were from early October and early December - a bit too wide for comfort. But Murray's data has proven more reliable than mine, and (tipped off by [Ariel Stulberg of The Real Deal](http://therealdeal.com/looks/Ariel%20Stulberg/by/)) he had run an additional survey on November 20. His data confirmed what I'd seen and more -- clearly there was something unusual that happened in early November.

Next: are our calculations correct? Comparing Airbnb data sets on different dates is tricky because there is always significant churn on the site -- a lot of people put up a listing, get little interest or decide it's not for them, and leave again. So I did my own calculations twice over (once in SQL, once using python [pandas](http://pandas.pydata.org/)), and Murray did his own, and we compared, until we came to feel confident in them.

And what about alternative explanations? Running similar calculations on a number of other cities (thank you [Jupyter notebooks](http://jupyter.org/)) showed nothing of similar size. Even the previous known purges (like [April 2014](http://www.cnet.com/news/airbnb-wipes-2000-ny-apartment-listings-before-court-hearing/)) did not show up quite so dramatically. Given the timing, we were pretty confident that the change was prompted by Airbnb removals, but who knows?

Finally: if Airbnb is removing "bad actors", isn't this a good thing? After talking it over with people I respect (thank you Lynne) we agreed that the big problem is one of trust. I managed to get the last word in the [New York Times story](http://www.nytimes.com/2016/02/12/business/airbnb-purged-new-york-listings-to-create-a-rosier-portrait-report-says.html) on our report: Airbnb's business model depends on changing regulations in cities around the world, and so cities need to be able to trust Airbnb. By hiding what they did, Airbnb is acting in an untrustworthy manner. Their "Community Compact" (actually a unilateral document, not a compact) commits Airbnb to co-operating with cities and being transparent: this action was neither co-operative nor transparent.

So several rounds of edits later, and after many attempts to format graphs so as to put the message in a clear fashion, we released our findings as a report, and it got [more coverage than I could have expected](http://tomslee.net/2016/02/airbnb-report-media-coverage.html). I admit I was nervous about Airbnb's response: a bad calculation or an overlooked reasonable explanation could leave us looking pretty stupid.

In the first story (in the [New York Daily News](http://www.nydailynews.com/news/world/airbnb-dropped-1g-questionable-listings-opening-books-article-1.2526230)) "Airbnb dismissed the findings, saying through a spokesman that 'listings come on and go off throughout the year. We routinely review our listings to ensure guests are having the quality, local experience they expect and deserve'." The way I read that, Airbnb is saying the changes we saw are just regular churn in the business, and implicitly denying that the company did anything special in that time. The "spokesman" also said that "The report also focuses on the busy marathon and Halloween weekend, when listings spiked"; a claim the company repeated to [The Guardian.](http://www.theguardian.com/technology/2016/feb/10/airbnb-new-york-city-listings-purge-multiple-apartment-listings)

After a brief panic and a little reflection, it was clear to us that this explanation does not hold water. We hadn't seen a spike in overall listings, we had seen a thousand more listings vanish from the platform than during other months, and almost exclusively these extra vanished listings were owned by hosts with multiple listings: there's no reason for any special event to have such an effect.

As the day went on and coverage spread, Airbnb obviously got their act together and came up with a standard response. For example, here is what they sent to Fusion's [Kristen V. Brown](http://fusion.net/story/267202/a-new-report-alleges-that-airbnb-manipulated-data/):


“The facts are clear for all to see—the vast majority of our hosts are everyday people who have just one listing and share their space a few nights a month to help make ends meet. Airbnb is an open people-to-people platform where listings come on and go off throughout the year. We’ve also done significant work to educate our community about what is in the best interest of their city and we routinely review our listings to ensure guests are having the quality, local experience they expect and deserve.”


The company provided one other piece of updated information, [which was to share](http://fortune.com/2016/02/11/airbnb-listings-research-data/) "a partial snapshot with _Fortune_ of its New York City listings as of Feb. 8 that shows that 94% of hosts there only have one listing."

The paragraph is fluff, sprinkled with generalities. The number they give (94%) actually matches what Murray and I had found rather than countering it (Figure 1 in [the report](http://whimsley.s3.amazonaws.com/wordpress/wp-content/uploads/2016/02/how-airbnbs-data-hid-the-facts-in-new-york-city.pdf)). This response again made me feel more confident that we were on the right track.

Still, I confess it was pretty sweet when, on Wednesday morning, Airbnb changed its tune. The company sent a letter and an FAQ to New York State representatives and posted the two documents [on its site](https://www.airbnbaction.com/our-community-compact-in-new-york-city/). I first heard of these documents from the above-mentioned Kristen Brown. Here is the key Q&A:


**Did you remove listings from your community last fall? **




Yes. We issued our Community Compact in November. Throughout November, and consistent with our Compact commitments, we removed roughly 1,500 of the 37,000+ Airbnb listings in New York City in an effort to remove listings that appeared to be controlled by commercial operators and did not reflect Airbnb’s vision for our community. 622 hosts were impacted, including 375 (60%) that had 2 or more listings removed.


The company has changed its tune, and conceded that it did indeed remove listings (and did not tell anyone about doing so). Fusion's [report ](http://fusion.net/story/272780/airbnb-new-york-data-purge/)had a great headline:


_Airbnb admits that it purged 1,500 unflattering New York listings right before data release_




The debate continues, of course. Working with Pat Clark of Bloomberg, Murray Cox [has shown](http://www.bloomberg.com/news/articles/2016-02-25/airbnb-s-purged-landlords-are-relisting-their-apartments) that some of the ejected listings have already started returning. The question of whether Airbnb's own "vision for the community" is a sufficiently precise and legitimate criterion for removal will be debated (hint: No). But for now, I'm happy to celebrate being right.

		
