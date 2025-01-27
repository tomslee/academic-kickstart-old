---
author: Tom Slee
comments: true
date: 2006-08-31 22:16:21+00:00
excerpt: "\n\t\t\t\t\t\t"
layout: post
link: http://tomslee.net/2006/08/software_featur.html
slug: software_featur
title: "\n\t\t\t\tSoftware Featuritis, or Why Checklists are Bad\t\t"
wordpress_id: 312
---


				

Here is a common-sense approach to software development, which I'll call the checklist approach:





  1. Propose a new feature.


  2. Ask if the feature is useful.


  3. If the feature is useful, implement it.



This essay uses shows why the checklist approach fails: why adding useful new features to a software product can make the overall product less useful to end users. This is a phenomenon I like to call _featuritis_.




At its simplest, a software product is a set of n independent features (i = 1,..., n). Each feature has a utility to the customer of ui. The overall utility of the software product to the customer is therefore




U = Sum( ui )




This tells you to keep adding features to the software to increase its utility, end of story. Not very interesting.




But software is not quite so simple as this. Each feature has not only a utility, but also a cost -- ci. This is the cost to the end user---not the developer---of using or deciding not to use the feature. The cost may include the time taken to find out about a feature, deciding how to use it, whether it is the right feature to use (among the options available), difficulty exploring and evaluating the feature, and so on.




With this cost added in, the overall utility of the software product to the end user is




U = Sum( ui - ci )




Let's keep things really simple, and assume that all features have the same utility (u). We can't do this for the cost though: the cost of using a feature inevitably depends on the total number of features in the product. This may be because it takes longer to find information about a particular feature in the documentation or user interface, or because it is more difficult to decide if this is the right feature to use among those that are present, or a host of other reasons (more on this below). So the cost of finding out about a feature is (c * n).




The overall utility of the software is then 




U = Sum( u - c * n )




or, as all the terms are equal,




U = n ( u - c * n )




Which looks like this:




![Image1_1](http://whimsley.typepad.com/photos/uncategorized/image1_1.png)





The utility function increases up to a maximum at n = ( u / 2 c ), and then decreases: that is, beyond a certain point, adding new features actually makes the software less useful. In other words, software is vulnerable to featuritis: it can become so complex that its complexity makes it useless. It may contain useful features, but finding these needles in the haystack of the product is frustratingly difficult. Experience tells us that this is a reasonable, if not surprising, result.





What is more, adding features _that are useful in and of themselves _can still introduce featuritis. For a feature to be useful, its utility (u) must be greater than the cost of finding out about it (c * n). So using this model, features will be added to the software until the following condition is met





n = u / c.




which is where the line crosses the x axis. The maximum utility of the software occurs at half this value (n = u / 2 c): if we continue to add features until the last feature is only just useful, the overall utility of the software will be U = 0. If features were stopped at (u / 2 c), the utility would be U = ( u2 / 4 c ). Even a useful feature degrades the usability of other product features, by making them harder to use (increasing the cost of using them). 




It follows that checklist driven software development will lead to poor software. Checklists are simply lists of useful features, without any consideration of the costs they introduce to the customer. A longer checklist is often assumed to be intrinsically better than a short checklist, but we have just seen that this may not be so.




What it is about this very simple model that produces these results? The key assumption is that features have independent utilities, but that the costs of using features are not independent. In economists' jargon, features exert a negative externality on each other. Is there a reason to think this might be true? 




The independence of feature utility is simply a matter of defining a feature  
properly. For example, if a very common scenario requires two "features" (A and B) then the utility of feature A depends very much on whether feature B is present or not. By itself, the utility of feature A may be very low -- you can't do much with it by itself. Once feature B is present, though, feature A becomes very useful. They are not independent features. The problem here is that "features" A and B are incomplete, and so are really part of a single properly-defined "feature". The model requires that we define features in terms of tasks that customers can carry out. The model does not tell us to implement 5/6 of a feature and then not implement the last sixth because of complexity worries.




The second assumption is that the cost of using a feature is dependent on other product features. The idea of a cost of using a feature is a very general one, and is not only "how long does it take to locate this feature in the documentation?". It may also reflect the confusion and uncertainty introduced by a plethora of choices. For example, if there are multiple ways of carrying out a task, the customer must decide which way is the best. If there are other features that appear to be related, the customer must investigate those (and discard them) before deciding on a course of action. If there are prerequisite features that must be understood, the customer must learn these also. They must spend time evaluating the alternatives. It seems reasonable to assume that the cost of wisely using an appropriate feature does depend on the overall complexity (number of features) in the product. The job of user interface designers and documentation teams is, at least in part, to minimize this destructive interference between product features. Good UI and documentation can help postpone the point at which featuritis sets in, but can't hold it back for ever.




Of course, while simplified models like this might help us watch out for certain kinds of trap, they can't help us decide which specific features to include, and which to discard. Also, there is not much to be gained from trying to pinpoint the particular u and c associated with features or products. Despite the equations, it is a qualitative model and cannot be easily quantified in a useful manner. Finally, while it is certainly true that ui and ci are far from constant in any product, there is probably not a lot to be gained by trying to refine their representation. As soon as models like this are made more complex, the result is a very open-ended and conditional prediction. Building fine software products can't be reduced to equations.




But I do think the central ideas are broadly correct: complexity does influences cost and utility in different ways, software does tend to become overly complex. and---most importantly---asking "is this a useful feature?" is not the right way to develop good products.


		
