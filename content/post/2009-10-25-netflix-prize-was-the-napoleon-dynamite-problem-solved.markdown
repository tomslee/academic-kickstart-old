---
author: Tom Slee
comments: true
date: 2009-10-25 21:09:44+00:00
excerpt: "\n\t\t\t\t\t\t"
layout: post
link: http://tomslee.net/2009/10/netflix-prize-was-the-napoleon-dynamite-problem-solved.html
slug: netflix-prize-was-the-napoleon-dynamite-problem-solved
title: "\n\t\t\t\tNetflix Prize: Was The Napoleon Dynamite Problem Solved?\t\t"
wordpress_id: 106
---


				

I just gave a talk at [work](http://iablog.sybase.com/tslee/2009/10/google-street-view-reaches-sybase-waterloo) on “Recommender Systems and the Netflix Prize”, and included the two major popular articles about the prize in its final year or so. One was in Wired Magazine and one was in the New York Times., and each focused on one outstanding problem that the competitors faced. Wired looked at the quirkiness of users as they rate movies, and the NYT focused on the difficulty of predicting ratings for a handful of divisive movies. 

 

Now that the contest is over we can answer the question, “were those problems solved?”

 

Let’s start with the Wired article. Entitled “This Psychologist Might Outsmart the Math Brains Competing for the Netflix Prize” [[link](http://www.wired.com/techbiz/media/magazine/16-03/mf_netflix)] it interviewed Gavin Potter, aka “Just a guy in a garage”. Here’s the hook:

 

<blockquote>  
> 
> The computer scientists and statisticians at the top of the leaderboard have developed elaborate and carefully tuned algorithms for representing movie watchers by lists of numbers, from which their tastes in movies can be estimated by a formula. Which is fine, in Gavin Potter's view — except people aren't lists of numbers and don't watch movies as if they were.
> 
> </blockquote>

 

Potter is focusing on effects like the Kahneman-Tversky anchoring effect:

 

<blockquote>  
> 
> If a customer watches three movies in a row that merit four stars — say, the Star Wars trilogy — and then sees one that's a bit better — say, Blade Runner — they'll likely give the last movie five stars. But if they started the week with one-star stinkers like the Star Wars prequels, Blade Runner might get only a 4 or even a 3. Anchoring suggests that rating systems need to take account of inertia — a user who has recently given a lot of above-average ratings is likely to continue to do so. Potter finds precisely this phenomenon in the Netflix data; and by being aware of it, he's able to account for its biasing effects and thus more accurately pin down users' true tastes.
> 
> </blockquote>

 

Well Potter didn’t win, but did these kind of ideas help when it came to the winning submission? The answer is yes. The winning teams worked these kind of patterns, which are independent of particular user-movie combinations, into their models through the bland name of “baseline predictors”. 

 

Any model has to predict ratings that individual users will give for particular movies. A very simple baseline predictor could take the average of all the ratings for that movie, take the average of all ratings given by the user in question, and split the difference. So if the movie has an average rating of 3.45 and the user has rated all the movies he/she/they have watched with an average of 2.55, then the model would predict a rating of 3. This includes some minimal level of user-quirkiness (are they a high or low rater?), some level of information about the movie (is it rated highly or not?) yet has nothing to say about how this particular user is expected to react to this particular movie.

 

In their winning submission, the BellKor team [[PDF link](http://www.netflixprize.com/assets/GrandPrize2009_BPC_BellKor.pdf)] list their major improvements in the final year of the competition, and the first item they give is improved baseline predictors. In particular, 

 

<blockquote>  
> 
> Much of the temporal variability in the data is included within the baseline predictors, through two major temporal effects. The first addresses the fact that an item’s popularity may change over time. For example, movies can go in and out of popularity as triggered by external events such as the appearance of an actor in a new movie. This is manifested in our models by treating the item bias as a function of time. The second major temporal effect allows users to change their baseline ratings over time. For example, a user who tended to rate an average movie “4 stars”, may now rate such a movie “3 stars”. This may reflect several factors including a natural drift in a user’s rating scale, the fact that ratings are given in the context of other ratings that were given recently and also the fact that the identity of the rater within a household can change over time…
> 
>    
> 
> It was brought to our attention by our colleagues at the Pragmatic Theory team (PT) that the number of ratings a user gave on a specific day explains a significant portion of the variability of the data during that day.
> 
> </blockquote>

 

A model with these variations, and no specific user-movie considerations (i.e., one that is useless for presenting a list of recommendations to a user) actually ends up being significantly more accurate than Netflix’s own Cinematch algorithm was at the beginning of the competition.

 

So score one for the winners – they solved the user-quirkiness problem.

 

The second article was in the New York Times and was called “If You Liked This, You’re Sure to Love That” [[link](http://www.nytimes.com/2008/11/23/magazine/23Netflix-t.html)]. Its focus was not the quirkiness of users, but unpredictable movies. Author Clive Thompson interviewed Len Bertoni, a leading contestant:

 

<blockquote>  
> 
> The more Bertoni improved upon Netflix, the harder it became to move his number forward. This wasn’t just his problem, though; the other competitors say that their progress is stalling, too, as they edge toward 10 percent. Why?
> 
>    
> 
> Bertoni says it’s partly because of “Napoleon Dynamite,” an indie comedy from 2004 that achieved cult status and went on to become extremely popular on Netflix. It is, Bertoni and others have discovered, maddeningly hard to determine how much people will like it. When Bertoni runs his algorithms on regular hits like “Lethal Weapon” or “Miss Congeniality” and tries to predict how any given Netflix user will rate them, he’s usually within eight-tenths of a star. But with films like “Napoleon Dynamite,” he’s off by an average of 1.2 stars…
> 
>    
> 
> And while “Napoleon Dynamite” is the worst culprit, it isn’t the only troublemaker. A small subset of other titles have caused almost as much bedevilment among the Netflix Prize competitors. When Bertoni showed me a list of his 25 most-difficult-to-predict movies, I noticed they were all similar in some way to “Napoleon Dynamite” — culturally or politically polarizing and hard to classify, including “I Heart Huckabees,” “Lost in Translation,” “Fahrenheit 9/11,” “The Life Aquatic With Steve Zissou,” “Kill Bill: Volume 1” and “Sideways.”
> 
>    
> 
> So this is the question that gently haunts the Netflix competition, as well as the recommendation engines used by other online stores like Amazon and iTunes. Just how predictable is human taste, anyway? And if we can’t understand our own preferences, can computers really be any better at it?
> 
> </blockquote>

 

The reason Napoleon Dynamite is a problem is not because it’s the most difficult movie to predict – it isn’t – but because it’s difficult to predict **and** it was rated by a lot of people. A movie that is difficult to predict but which is rated by only a handful of users will contribute very little to the total error in a model.

 

Well, now the competition is done, the complete data set and the predictions of the winning submission are available for download [[link](http://archive.ics.uci.edu/ml/datasets/Netflix+Prize)], so download them I did, loaded them into a [SQL Anywhere](http://www.sybase.ca/products/databasemanagement/sqlanywhere) database, and graphed the results. Here is a plot of the remaining error for each movie against the total number of ratings for that movie, for all 17770 movies. Napoleon Dynamite is the red dot.

 

[![grand_prize_erorr_vs_rating_count](http://whimsley.typepad.com/.a/6a00d83451d3b369e20120a6762ae6970c-pi)](http://whimsley.typepad.com/.a/6a00d83451d3b369e20120a61ece12970b-pi)

 

With 116,362 ratings, Napoleon Dynamite has a higher error than any other movie rated more than 50,000 times. I’s RMSE is 1.1934: just as bad as it was for Len Bertoni when the original article was written.

 

So there you go: user quirkiness was resolved, at least the the extent that was needed to win the prize, while quirky movies remained stubbornly unpredictable till the end.


		
