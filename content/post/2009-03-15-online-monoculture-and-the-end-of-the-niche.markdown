---
author: Tom Slee
comments: true
date: 2009-03-15 13:57:50+00:00
excerpt: "\n\t\t\t\t\t\t"
layout: post
link: http://tomslee.net/2009/03/online-monoculture-and-the-end-of-the-niche.html
slug: online-monoculture-and-the-end-of-the-niche
title: "\n\t\t\t\tOnline Monoculture and the End of the Niche\t\t"
wordpress_id: 120
---


				Online merchants such as Amazon, iTunes and Netflix may stock more items than your local book, CD, or video store, but they are no friend to "niche culture". Internet sharing mechanisms such as YouTube and Google PageRank, which distil the clicks of millions of people into recommendations, may also be promoting an online monoculture. Even word of mouth recommendations such as blogging links may exert a homogenizing pressure and lead to an online culture that is less democratic and less equitable, than offline culture.

Whenever I make these claims someone says "Well I use Netflix and it's shown me all kinds of films I didn't know about before. It's broadened my experience, so that's an increase in diversity." And someone else points to the latest viral home video on YouTube as evidence of niche success.

So this post explains why your gut feel is wrong.

The argument comes from a paper by Daniel M. Fleder and Kartik Hosanagar called [Blockbuster Culture's Next Rise or Fall: The Impact of Recommender Systems on Sales Diversity](http://papers.ssrn.com/sol3/papers.cfm?abstract_id=955984). They simulate a number of different kinds of recommender system and look at how these systems affect the diversity of a set of choices. Towards the end of the paper they observe that some of their recommender systems increase the experience of diversity for every individual in the sample and yet decrease the overall diversity of the culture. So I wrote a program that does basically what they do in their paper and tweaked it to highlight this result.

The result is what's important here, rather than the particular algorithm used to generate this instance of it. But I know some people will want to know how the results are generated, so I'll give a short sketch. If you want more than this, Fleder and Hosanagar provide details, my tweaks to their model are available as source code (python) if you want, and if you post in the comments we could get into a discussion. But it's not important, trust me.

Each simulation starts with 48 customers and 48 products. Each product is described by two attributes, with values generated according to a normal distribution. So the products are distributed on a two-dimensional grid, with a value of about -3 to +3 along each axis. Each customer is assigned a taste for each attribute, so they also are scattered about in the same space. The idea is that a customer will prefer, other things being equal, a product that is close to it in these attributes. Here are two distributions of customers (blue) and products (red). You can see that most customers share a mainstream taste around the middle of the graph, but there are a few who have odd tastes off to the edges. Likewise, most products have attributes that are mainstream, but there are a few "niche" products closer to the edge.
![](http://whimsley.typepad.com/.a/6a00d83451d3b369e2011168f819ee970c-pi)

In this particular simulation, a customer can choose the same item over and over again, so it simulates something like streaming radio more than a bookstore. Each simulation starts off with a priming phase, in which each customer makes 75 choices according to a function which favours nearby products, but with some randomness so that they may on occasion choose one further away. After 75 choices we turn on a recommender function. Whenever a customer goes to make a choice, the recommender system identifies a product and recommends it to the customer. The recommendation increases the chance that the customer will choose the recommended product. Fleder and Hosanagar look at a few recommender functions. The one I use works like this:



	
  * The set of 48 customers is divided into equal-sized communities, with members&nbsp;chosen at random so they may not be close in taste.

	
  * The recommender function chooses an item by looking at what customers in the same community have chosen. It recommends the one most popular among others in the community.


I'm just going to show you two simulations. Run 1 above - which I will call Internet World - treats the entire set of 48 customers as a single community. The other (run 28 above), which I will call Offline World, breaks it into 24 communities of two people each. In Offline World I will get recommendations from the people around me and you will get recommendations from the people around you, but these recommendations are separate and isolated. In Internet World we each get recommendations from all 48 customers.


Here are the results for the two simulation runs I'm going to focus on. The results of these simulations are far from the only possible outcome, but they show why the gut feeling may fail, and I've chosen them for that purpose.


In Internet World each customer experiences an average of 3.5 products over the course of 75 choices with an active recommender system, while in Offline World each customer experiences only 2.4 different products. So the wider set of people providing recommendations in Internet World has led to an increase in individual diversity. This is like saying that "Netflix shows me pictures I would never had heard about from my friends alone", or "Amazon recommended a book I had never heard of, and I liked it".

On the other hand, the overall diversity of the culture can be measured by the Gini coefficient of the products. A Gini coefficient of zero is complete equality (each product is chosen an equal number of times) and a Gini coefficient of 1 is complete inequality (only one product is ever chosen by anyone). And Internet World has a Gini of 0.79 while Offline World has a Gini of only 0.52. Internet World is less diverse than Offline World.

How can these seemingly contradictory results happen? Let's take a look.

In the following graph, each dot is a customer, arranged in their two-attribute preference space (just like in the graphs above). But this time the area of each dot is proportional to the number of unique products they experience. So in Run 1 (Internet World) you can see that the dots are, on average, bigger than the dots in Run 28 (Offline World). This shows the greater individual experience of diversity in Internet World; for example, there is a customer with attributes of (1.1, -0.8) who samples no less than 38 different products, and only seven of the 48 customers stay with a single product throughout the whole simulation. Meanwhile in Offline World  the most eclectic customer samples only nine and there are no fewer than 19 customers who sample just one product. The experience of individual customers in Internet World is of broader horizons and more selection, as recommendations pour in from far and wide, rather than from the limited experiences of their small community in Offline World. This picture has become the standard narrative of choice in the Internet World - our cultural experiences, liberated from the parochial tastes and limited awareness of those who happen to live close to us, are broadened by exposure to the wisdom of crowds, and the result is variety, diversity, and democratization. It is the age of the niche.

![](http://whimsley.typepad.com/.a/6a00d83451d3b369e2011168f81de9970c-pi)
But wait!

Here is a graph of the products in each simulation. This time, the area of each dot shows its popularity: how often a customer chooses it.


![](http://whimsley.typepad.com/.a/6a00d83451d3b369e2011168f81e48970c-pi)


You can see that on the left, in Internet World, a few products were chosen a lot, especially the one centred on about (-0.2, -0.2). In Offline World there are many more medium-sized dots, showing that the consumption of products is more equal. In Internet World one product has "gone viral" and gets chosen over 1500 times out of the total of 3600, while 26 products languish in the obscurity of being sampled fewer than ten times. In Offline World no single product is chosen more than 10% of the time, and only 14 products are sampled fewer than ten times. In short, niche products do better in Offline World than in Internet World.

While each customer on average experiences more unique products in Internet World, the recommender system generates a correlation among the customers. To use a geographical analogy, in Internet World the customers see further, but they are all looking out from the same tall hilltop. In Offline World individual customers are standing on different, lower, hilltops. They may not see as far individually, but more of the ground is visible to someone. In Internet World, a lot of the ground cannot be seen by anyone because they are all standing on the same big hilltop.

The end result is the Gini values mentioned before. Here are Lorentz curves for Internet World (blue) and Offline World (green), in which the products are lined up in order of increasing popularity along the x axis, and the cumulative choices for those products is plotted up the Y axis. 

![](http://whimsley.typepad.com/.a/6a00d83451d3b369e2011168f81ea8970c-pi)

So there it is. Individual diversity and cultural homogeneity coexisting in what we might call _monopoly populism_.

But don't think this is just about automated recommender systems, like the ones that Amazon and Netflix use. The recommender "system" could be anything that tends to build on its own popularity, including word of mouth. A couple of weeks ago someone pointed me to [this video](http://www.youtube.com/watch?v=10FKWOn4qGA) of Madin, a six-year-old soccer prodigy from Algeria, and the next day my son, who moves in very different online circles to me, was watching the same one. I know who Jim Cramer is even though we don't get CNBC in Canada because everyone is talking about him and [helping his disembodied head to shoot down Jon Stewart](http://www.thebigmoney.com/articles/news/2009/03/13/play-jim-cramers-crashteroids-game). More people watched Tina Fey being Sarah Palin online than on Saturday Night Live, and Fey is now famous in countries where no one watches the TV show. Clay Shirky writes [an essay](http://www.shirky.com/weblog/2009/03/newspapers-and-thinking-the-unthinkable/) and I get five different links to it in my Google Reader feed in one morning. Our online experiences are heavily correlated, and we end up with monopoly populism.

A "niche", remember, is a protected and hidden recess or cranny, not just another row in a big database. Ecological niches need protection from the surrounding harsh environment if they are to thrive. Simply putting lots of music into a single online iTunes store is no recipe for a broad, niche-friendly culture.		
