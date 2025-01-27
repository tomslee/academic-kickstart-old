---
author: Tom Slee
comments: true
date: 2014-06-09 17:53:00+00:00
excerpt: "\n\t\t\t\tMore numbers from the Airbnb web site. There is a surprising amount\
  \ of churn in Airbnb's listings. Also, the importance of peer-to-peer reputation\
  \ is overrated.\t\t"
layout: post
link: http://tomslee.net/2014/06/the-shape-of-airbnbs-business-ii.html
slug: the-shape-of-airbnbs-business-ii
title: "\n\t\t\t\tThe shape of Airbnb's business (II)\t\t"
wordpress_id: 1251
categories:
- airbnb
tags:
- airbnb
---


				




Collecting data for several cities both in November 2013 and in May 2014 gives a look at some ways in which Airbnb's business is changing in these cities. The cities surveyed are:









	
  * Paris and New York (Airbnb's two biggest markets)

	
  * San Francisco (the home of Airbnb)

	
  * London, Rome, Berlin (three European capitals and major tourist cities)

	
  * Toronto and Chicago (two smaller markets).


As [in Part I](http://tomslee.net/2014/05/the-shape-of-airbnbs-business.html), the surveys were carried out by a two-stage method:



	
  * Stage 1 used the Airbnb search pages for a city to collect Room ID values (a number that uniquely identifies an individual listing).

	
  * Stage 2 visited the listing page for each Room ID and collected information about it.


The data were stored in a database and the charts here are based on queries of that database. The survey code (and database) are available on [github](https://github.com/tomslee/airbnbny).

The main observations are:



	
  * It is possible that the number of listings has reached a maximum in some of Airbnb's largest cities, particularly in the USA, while other cities do continue to show significant growth.

	
  * There is a surprising amount of churn in Airbnb's business. Over a third of the listings on the site in November were no longer there in May, to be replaced by a similar (or, in some cases, greater) number of new listings.

	
  * Around 90% of all ratings on the site are 4.5 stars or 5 stars (out of five).


These observations suggest some conclusions:

	
  * Airbnb's move to professionalize its host base may be a reaction to the churn in the host population, a necessary step to generate continued growth.

	
  * In April Airbnb expelled 2,000 listings from its New York offerings, claiming that they did not offer a positive experience. Many of those listings must have had either no ratings at all or were rated highly (4.5 or 5) by their guests.

	
  * The rating system does not provide a reliable assessment of host quality.










### Churn






Figure 1 shows the net change in the number of listings in each of the eight cities for which data was collected in both November and May, as a percentage of its November value.

Some cities seem to have maxed out in terms of listings. Six of the cities saw either decreases or increases of less than 10% in the total number of listings. Each of the three US cities in the study lost listings between November and May, while Berlin and Rome were big gainers.




![nysuffer.png](http://tomslee.net/wordpress/wp-content/uploads/2014/06/wpid-nysuffer.png)

Figure 1: Change in number of listings in cities.




The net gains or losses mask a bigger change. Figure 2 shows that in the six month period, well over a third of existing listings vanished from the site, and were replaced by a similar (or, in the case of Berlin and Rome, substantially greater) number of new listings. For both Paris and New York, well over 40% of listings vanished, only to be replaced by new ones. Figure 3 shows the total number of vanished and new listings.

The high churn rate must introduce uncertainty for Airbnb's future, as it is relying on a steady stream of new listings to replace those that are vanishing from the site. Perhaps this is one of the motivators of Airbnb's efforts to professionalize its host base: hosts who make a commitment to the business being more likely to stick around.




![churn.png](http://tomslee.net/wordpress/wp-content/uploads/2014/06/wpid-churn.png)

Figure 2: New and vanished listings between November 2013 and May 2014, as a percentage of the November number.








![example1.png](http://tomslee.net/wordpress/wp-content/uploads/2014/05/wpid-example12.png)

Figure 3: absolute number of new and vanished listings




[Note: I did wonder whether this high churn rate could be an artefact: whether the displayed room ID values could have changed between the November and May data collections. A query showed that, of the 10597 listings that occur in both the November and May collections from New York, 10529 have the same host. I concluded that room ID values are stable.]

We can look a little closer at those vanished listings. Figure 4 shows that the vanishing listings have fewer reviews than the overall population in the city.




![churn_reviewcount.png](http://tomslee.net/wordpress/wp-content/uploads/2014/06/wpid-churn_reviewcount.png)

Figure 4: Mean number of reviews for vanished listings and for all listings




Figure 5 shows the ratings that the vanished listings had received from guests. The overall distribution of ratings is investigated later in this report, but Figure 5 shows that, while many of the listings had no reviews at all (Airbnb recently claimed that reviews are left for 70% of visits, so it is likely that these listings had no visits either), of those that did have visits the average rating was overwhelmingly high (4.5–5).




![churn_lost_ratings.png](http://tomslee.net/wordpress/wp-content/uploads/2014/06/wpid-churn_lost_ratings.png)

Figure 5: The number of vanished listings by average overall rating




Figure 6 emphasizes the point, showing that the average rating of listings leaving the site is within 0.1 of those that stay on the site.




![churn_rating.png](http://tomslee.net/wordpress/wp-content/uploads/2014/06/wpid-churn_rating.png)

Figure 6: Average rating of listings that leave the site (red) and which have been on the site for the whole period (green). Note that the y axis **starts** at 4.5.




It seems likely that many hosts try Airbnb, have a few guests (or none at all) and then simply decide that, for whatever reason, the service is not for them. To repeat the conclusion from the overall churn rate, the high turnover rate does raise questions about what long-term population of hosts the site can support, and how it can ensure that those who try and leave the site are replaced by new hosts.












### Trust






Trust has long been a key part of the Airbnb business, and technology has been seen as the magic ingredient. Airbnb CEO Brian Chesky expresses the company's confidence when he [says](http://skift.com/2013/01/11/airbnb-responds-to-illegal-rentals-story-first-of-all-its-not-illegal-everywhere/) of city-level rules that "they're primarily set up for screening. To protect consumers. Well it turns out that cities can't screen as well as technologies can screen. Companies have these magical things called reputation systems… We think government should exist as the place of last recourse."

There are two sides to [Airbnb's trust system](https://www.airbnb.ca/trust). There is _peer-to-peer trust_, often described as a reputation system, which consists of ratings, personal profiles, and comments written by hosts or guests and seen by other hosts or guests. The other side is _centralized trust_, which consists of central payment, verified ID, and a complaint system.

Much of the talk around the sharing economy focuses on reputation and peer-to-peer trust (as in Chesky's comment above). That's because it's the peer-to-peer aspect that is new: after all, in one sense we have forever trusted strangers to deliver services from food to haircuts to regular taxis, and the centralized component of the system is not that different to many hospitality companies. Jason Tanz [writes](http://www.wired.com/2014/04/trust-in-the-share-economy/) in _Wired_ that


<blockquote>We are entrusting complete strangers with our most valuable possessions, our personal experiences—and our very lives. In the process, we are entering a new era of Internet-enabled intimacy.</blockquote>


So what do the numbers have to say about peer-to-peer trust?

Figure 7 shows the distribution of ratings for each listing. Airbnb provides ratings under a number of categories (cleanliness, accuracy of description etc) and collects them together as "overall satisfaction". The site does not give the ratings for individuals (although individual comments are visible) but provides an aggregate, from 0 to 5 stars with a half-star granularity.




![city_rating_distribution.png](http://tomslee.net/wordpress/wp-content/uploads/2014/06/wpid-city_rating_distribution.png)

Figure 7: Overall satisfaction ratings for listings in each city. The ratings for 0-3 are so few that they are collected together. Listings with no ratings are excluded.




The vast majority of ratings are either 4.5 or 5 stars. The finding is consistent with ratings on other sites (e.g. an earlier look at [BlaBlaCar](http://tomslee.net/2013/09/some-obvious-things-about-internet-reputation-systems.html), or more serious studies of eBay listed there). When we rate each other, ratings become more a courtesy than a judgment. Just as restaurant tips only weakly correspond to the quality of service, so a rating of 4.5 or 5 is more a way of politely concluding an exchange than it is of assessing the behaviour of a host or guest.

The ratings obviously fail to distinguish among the people on the site, and so are not providing the service for which they were intended. This is part of the reason why Airbnb and others have moved to emphasize the centralized trust aspect of their systems. But centralized trust is the same reason we trust the fast-food restaurant cook or the hotel cleaning staff. The major sharing economy sites rely on discipline and the potential for removal from the site to provide security for the users, just as traditional industries do.












### Churn and Trust in New York






The Airbnb court case in New York raised the profile of the service there, and resulted in Airbnb ejecting 2,000 listings from its service.

Airbnb [claims](http://publicpolicy.airbnb.com/new-york-airbnb-community/) that "we found that some property managers weren’t providing a quality, local experience to guests. These hosts weren’t making their neighborhood stronger and they weren’t delivering the kind of hospitality our guests expect and deserve. In some cases, they were making communities worse, not better."

With 10,000 listings vanishing from Airbnb in the New York area, it is difficult to know which 2,000 were removed by Airbnb and which left for other reasons. Some individual hosts with large numbers of listings have been removed, but that still leaves many unaccounted for. Figure _ny-vanished_ shows that, despite Airbnb's [suggestion](http://publicpolicy.airbnb.com/new-york-airbnb-community/) that the hosts are not "delivering the kind of hospitality our guests expect", most of the removed listings must have had either no ratings at all, or must have had good ratings from their guests.




![ny-vanished.png](http://tomslee.net/wordpress/wp-content/uploads/2014/06/wpid-ny-vanished.png)

Figure 8: The "overall satisfaction" ratings for listings in New York that vanished from the site between November 2013 and May 2014.




The biggest single category of the 10,000 New York listings that have vanished from the Airbnb site are listings with no ratings at all (shown as NULL). After that come the 5.0 and 4.5 ratings, leaving fewer than 800 with bad ratings (4 or lower). For at least 1200 of the listings that Airbnb removed, bad ratings is not the reason.

Combined with the very high number of positive ratings shown in Figure 7, this result shows that the significance of peer-to-peer ratings is exaggerated for Airbnb. While the company proclaims that peer-to-peer rating systems set it apart from old-style methods, it is clear that their trust system is essentially a traditional complaint-based, centralized system. The peer-to-peer ratings may give warm feelings on the site, but Airbnb itself clearly does not trust it when it goes to remove listings from its site.












### Conclusions






The data set suggests that there is a surprising amount of churn in Airbnb's hosts. Over a third of the host population in November left the site, to be replaced by new listings.

It is likely that a large number of people experiment with being Airbnb hosts, and then decide that it is not for them.

It will be interesting to see whether this becomes an issue for Airbnb as the number of ratings it has in the North American cities surveyed in November and May seems to have peaked. How will it continue the growth that is demanded of it by its backers in the face of the large number of hosts who drop off the platform?

While much is made of the novel peer-to-peer nature of Airbnb's reputation system, it appears that the company runs a complaint-based trust system that is not so different from other hospitality companies. In April Airbnb expelled 2,000 listings from its New York offerings, claiming that they did not offer a positive experience, but many of those listings had either no ratings at all or were rated highly (4.5 or 5) by their guests: it appears that Airbnb did not use its own ratings when judging who to remove from its platform.









		
