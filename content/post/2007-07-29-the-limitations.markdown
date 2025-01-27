---
author: Tom Slee
comments: true
date: 2007-07-29 21:58:02+00:00
excerpt: "\n\t\t\t\t\t\t"
layout: post
link: http://tomslee.net/2007/07/the-limitations.html
slug: the-limitations
title: "\n\t\t\t\tThe Netflix Prize: 300 Days Later\t\t"
wordpress_id: 207
---


				

Today the [Netflix Prize Competition](http://www.netflixprize.com/) has been running for 300 days.





Online DVD rental outfit Netflix caused a real buzz last October when it announced the competition. If anyone can come up with a recommender system for predicting customer DVD preferences that beats its own algorithm (Cinematch) by a certain amount, Netflix will hand over $1million. The prize got a lot of attention because it exemplifies the idea of crowdsourcing. Not only does Netflix rely on crowdsourcing of DVD ratings (user ratings of DVD titles) but the competition itself is an attempt to use crowdsourcing to develop the algorithms to make the most of those ratings. Instead of doing the work itself, or hiring specialists, Netflix lets whoever anyone enter their competition and pays the winner. The competition is still in progress: Netflix says it will run until at least 2011. So now the initial buzz has died down, what can we learn from the Netflix Prize?




First, the competition details (see [here](http://www.netflixprize.com/assets/NetflixPrizeKDD_to_appear.pdf) (PDF) for a short paper by two Netflix employees). Netflix made public a database of customer DVD ratings (tweaked to ensure privacy) that included over 100 million individual ratings of 17,770 titles by 480,189 people. If you sign up for the prize, you can download these ratings. Each rating involves one customer giving an integer number from one star (very bad) to five stars (very good) for a given title. For example, customer 296452 gave title 234 ("Animation Legend: Winsor McCay") a rating of 1 (very bad).




The idea is that competition entrants try to develop an algorithm by using the training set (which is the 100 million plus set of ratings), try it out on a set of probe set of test data that they also give you, and once they think they have a good algorithm, create a set of predictions for a qualifying set of users and titles, and upload it to Netflix. Netflix test these predictions against the actual rankings (which they keep private) for that qualifying set. They post the leading algorithms on a [leaderboard](http://www.netflixprize.com//leaderboard).




The quality of any algorithm is determined by its root mean squared error (RMSE). To calculate the RMSE you take the difference between the rating the algorithm predicts and the actual rating, and square it so it's guaranteed to be a positive number. Then you take the average of all these over the set of data to get the mean squared error. Finally, taking the square root gives the RMSE, which is the roughly the size of a typical error.




A perfect algorithm would predict exactly what rating every user would give to every title and would have an RMSE of zero. A random set of predictions has an RMSE of 1.95. But the actual range of action is much narrower than this 1.95 range. A simple algorithm that uses the average rating for each title as the prediction - "let's see, the average rating for the 104,000 customers who rated Mean Girls was 3.514, so I predict you will give it a rating of 3.514" - gets an RMSE of 1.0540. Netflx's Cinematch algorithm has an RMSE of 0.9525. Netflix set the prize target at a 10% improvement over that, which is an RMSE 0.8563. So the range that recommendation systems can realistically cover - from naively simple to cutting-edge research - seems to be the narrow band between the middle three lines in the following diagram.




![](http://docs.google.com/File?id=dfx7r5rf_85x9qfswgv)




In the days and weeks after the prize was announced, progress was rapid. The Cinematch score was matched within a week. Within a month the leaders were half way to the winning prize with a 5% improvement. But getting further improvement progress has proved more and more difficult. It took another month to get to a 6% improvement, about 5 more months to get to 7%, and the current (July 29 2007) leader is at 7.8% improvement and has been unchanged for a month. Here is a graph of the progress, showing the three lines above and the prize leader progress:




![](http://docs.google.com/File?id=dfx7r5rf_84dr8gwqgt)  


At this stage it is not clear if the prize is winnable: the existing algorithms use a lot of linear algebra and some pretty fancy machine learning ideas (see a description by a leading participant [here](http://sifter.org/%7Esimon/journal/20061211.html) and some sample code for a similar approach [here](http://www.timelydevelopment.com/Demos/NetflixPrize.htm)), the leading groups include university research labs from around the world, and many of the more obvious approaches have been explored. Certainly media and blog interest - huge in the early days - has dropped off in recent months. [This](http://www.nytimes.com/2007/06/04/technology/04netflix.html?ei=5088&emc=rss&en=eda04055720ce432&ex=1338609600&partner=rssnyt) New York Times article is one of the few from the last month or two.  
  
Let's not get into the computer science of recommender systems - there's a good review from 2004 called Evaluating Collaborative Filtering Recommender Systems  [here](http://dblab.mgt.ncu.edu.tw/%E6%95%99%E6%9D%90/2004%20Data%20Mining/2004-55.pdf) if you want to know more. Instead, let's step back a bit and ask what this prize tells us so far, and look at a couple of things we can learn by poking around the massive data set that Netflix provided.  
  
One question is: how good is an algorithm with an RMSE of 1, and is an algorithm with an RMSE of 0.8563 much better for the average customer? Actually, I guess that's two questions. Anyway, if the errors followed a normal distribution (which they don't, but we're talking back-of-envelope here) then if a customer actually rated a title as 2 (poor), an algorithm with an RMSE of 1.0 would predict somewhere between 1 and 3 about 70% of the time. Not bad, but not startling. If the algorithm gave ten recommended movies, then it would get on average seven out of ten within one unit of the customer's actual rating. Meanwhile, the RMSE=0.8563 algorithm would get 7.6 out of ten. While this is an improvement, and while it may be a remarkable technical accomplishment, it does not seem to be exactly a revolutionary leap compared to the really simple algorithms as far as customers go.  
  
[**Update, December 25, 2007: **Yehuda Koren of leading team KorBell approaches the recommendation problem a different way, looking at ordering of recommendations rather than at matching them. His way is more appropriate, and gives much more encouraging results. See [here](http://www.netflixprize.com/community/viewtopic.php?id=828).]  
  
As soon as you start looking at the data set it becomes obvious why it is so difficult to get good results. Databases don't have the linear algebra and other mathematical tools for taking a run at the prize but they are convenient for exploring data sets, so I loaded the data into a [SQL Anywhere](http://www.ianywhere.com/products/sql_anywhere.html) database ([The developer edition](http://www.sybase.com/detail?id=1016644) is a free download, and I'll provide a perl script to load the data if you really want it) and started poking around. Here are a few of the more obvious oddities (all these observations have been posted elsewhere - see the [Netflix prize forum](http://www.netflixprize.com/community/) for more):




  * Customer 2170930 has rated 1963 titles and given each and every one a rating of one (very bad). You would think they would have cancelled their subscription by now.


  * Five customers have rated over 10,000 of the 17,770 titles selected - and presumably they also have rated some of the others among the 60,000 or so titles Netflix had available when they released the ratings. Are these real people?


  * Customer 305344 had rated 17654 titles. Even though Netflix make it easy to rate titles that you have not rented from them (so they can get a handle on your preferences) can this be real?


  * Customer 1664010 rated 5446 titles in a single day (October 12, 2005).


  * Customer 2270619 has rated 1975 titles. 1931 were given a 5, 31 were given a 4, 10 given a 3, 2 given a 2 (Grumpy Old Men and Sex In Chains) and a single title was given a 1. That title? Gandhi, which has an average rating of over 4 and which less than 2% of those who watch it give a 1.


  * The most often rated movie? Miss Congeniality with ratings by over 232,000 of the 480,000 customers. And which title is most similar to it in terms of ratings (using a slightly weighted Pearson formula)? Bloodfist 5: Human Target.


  * Most highly rated - Lord of the Rings: Return of the King (Extended Edition), with 4.7.



Some of the more bizarre facts above may be artifacts of whatever tweaking process Netflix put the data set through (although they claim not to have materially affected the statistics). While odd, bizarre users are not always difficult to deal with: if you have rated each of the last 1963 titles you've watched as 1 it is pretty easy to predict what you will rate the next title. But others are more tricky.




One reason for these oddities is one of the things that Evaluating Collaborative Filtering Recommender Systems identifies. They note that (on other, smaller data sets) even the best algorithms don't seem to get beyond an RMSE of 0.73 on a five-point scale, and speculate that the cause may be "natural variability". We users provide inconsistent ratings - sometimes we'd rate a movie a 3 and sometimes a 4, with no consistency. It may depend on our mood when we watched the movie - we may give a romantic movie a higher rating if we watched it on a first date than if we watched it a week later after being left broken hearted, or a demanding movie a low rating because we were tired and out of sorts when we watched it - or it may depend on our mood when we actually provide the rating.




There are other, more obvious reasons which, for reasons I don't understand, don't seem to get discussed much. Netflix itself and most competitors talk about the data in terms of "movies" and "users". But the "movies" in the list are not all movies: a lot are TV series or music video collections. The variability among the episodes of a series (Do you think Lost Season 1 deserves a 3 or a 4?) must make single-number ranking even more variable and these composite DVDs figure prominently among those titles that have the biggest variance in ratings.




Then there's the fact that a customer might not really be a single person. It might be a household with several viewers in it. So perhaps one person likes Terminator, one likes Bridget Jones, and one likes Spongebob Squarepants. Once we realize that the "user" might be a collection of people there is no strangeness between giving high ratings to each of these, but you can see how, depending on which household member entered the rating, the values may be quite different (perhaps this is why titles like 'N Sync: Making of the Tour, Pokemon Vol 9, and Boston Red Sox 2004 World Series Collectors' Edition have high variance - the person rating may not always have been the person who wanted to watch it). If the data set contains these inevitable variations (in addition to the plain kookiness on show in the Netflix set) then it may be that even the clevverest algorithm can make little progress in untangling all the intrinsic vagueness of the data. 




So what I get from the Netflix prize is that there are probably significant limits to recommender systems. Even the smartest don't do a whole lot better than the simple approaches, and a lot of work is required to eke out even a little more actual information from the morass of data. It seems surprisingly difficult to get reliable, factual information on this important question of how useful they can be. Part of the reason is that they are new - Amazon has only been in business for about ten years after all - and part of the reason is that the behaviour of these systems is often a closely guarded secret despite the aura of openness that web companies cultivate.




This matters because there is a surprising amount riding on the effectiveness of recommender systems. Silicon Valley's new-economy enthusiasts see them as the key to developing a new level of cultural democracy: they see recommender systems as a trebuchet hurling rocks at the castles of the old elite of mainstream media, big publishers with big marketing departments, big-chain book stores and Hollywood sequels. Recommender systems are claimed to embody the "wisdom of crowds". The idea is that everyone just publishes stuff (blogs, wikipedia entries and so on) and amateur readers or viewers decide what has merit by their actions (rating stories, buying and rating books and DVDs and so on). The work of critics is "crowdsourced" to customers, but it is the recommender system that distills these ratings to yield the aforementioned wisdom.




If faith in recommender systems is misplaced, then the new boss may look much like the old boss only with more computer hardware. There is a danger that recommender systems may simply magnify the popularity of whatever is currently hot - that they may just amplify the voice of marketing machines rather than reveal previously-hidden gems. Even worse, their presence may drive out other sources of cultural diversity (small bookstores, independent music labels, libraries) concentrating the rewards of cultural production in fewer hands than ever and leading us to a more homogeneous, winner-take-all culture.




I'm no futurist, but I see little evidence from the first 300 days of the Netflix Prize that recommender systems are the magic ingredient that will reveal the wisdom of crowds.


		
