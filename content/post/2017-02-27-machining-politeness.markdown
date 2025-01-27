---
author: Tom Slee
comments: true
date: 2017-02-27 03:05:56+00:00
excerpt: "\n\t\t\t\t\t\t"
layout: post
link: http://tomslee.net/2017/02/machining-politeness.html
published: false
slug: machining-politeness
title: "\n\t\t\t\tMachining politeness\t\t"
wordpress_id: 4313
---


				So Google (OK, "Jigsaw") has come out with the [Perspective API](https://www.perspectiveapi.com) which identifies toxic comments in online conversations:


<blockquote>The API uses machine learning models to score the perceived impact a comment might have on a conversation. Developers and publishers can use this score to give realtime feedback to commenters or help moderators do their job, or allow readers to more easily find relevant information, as illustrated in two experiments below. We’ll be releasing more machine learning models later in the year, but our first model identifies whether a comment could be perceived as “toxic" to a discussion.</blockquote>


It's the latest attempt to use machine learning to govern our online environment. Facebook is using it to stem the tide of fake news and sensationalistic news, while Alexa, Siri and other voice services or chat bots are the new interface to software services.

You can see why there is so much buzz about machine learning: it has suddenly taken a big leap forward, solving problems that have baffled computers for decades. Thanks to a new set of techniques called "deep learning", computer image recognition can now match humans, computer Go players and poker players can beat the best of us at strategy games, and computers are getting pretty good at playing video games too. And while we are at it, medical diagnoses, non-destructive testing of expensive equipment and "predictive maintenance" to help that equipment be used safely and efficiently. And the list will continue to grow.

Just to show how remarkable these new algorithms are: here is a small set of photos, with a completely computer-generated caption underneath each (from [here](http://cs.stanford.edu/people/karpathy/deepimagesent/devisagen.pdf)).

[![](http://whimsley.s3.amazonaws.com/wordpress/wp-content/uploads/2017/02/Untitled.png)](http://whimsley.s3.amazonaws.com/wordpress/wp-content/uploads/2017/02/Untitled.png)

I don't actually know what a wakeboard is, but I'll give it the benefit of the doubt. The project page, with more captions, is [here](http://cs.stanford.edu/people/karpathy/deepimagesent/).

But (you knew there was a but) there are reasons to have a sceptical perspective on Perspective.

In short, images don't change their appearance to try to trick image recognition software, and machine parts don't change their composition to trick image-based testing algorithms.

We don't know the details behind the Perspective API and Facebook's fake news algorithms, but here is a short diagram that gets the level of detail we need:

    
    INPUT --->  MACHINE LEARNING! ---> OUTPUT


The INPUT may be a set of a million images, and the OUTPUT may be a best estimate of what each image shows (or even a caption describing the image, above).

The methods we are looking at here fall under the name of "supervised" learning, which means that the algorithm is trained on a large sample of input images for which the correct output is already known. Then the MACHINE LEARNING! in the middle is tweaked until it gives good answers for the known set, and so that it performs well against a second set which it hasn't seen before. Finding the best tweaks is, of course, the subject of many massive research projects.

Machine learning algorithms identify a set of features that, when they are found in an image, show that it's an elephant or a desk or a catamaran. Deep learning algorithms consist of a set of layers that loosely mimic how the brain works, constructing a hierarchy of features, starting with simple things like edges, or patches of red and building on these to construct more abstract features that cannot be simply described, until the final layer spits out "turtle" or "bowtie" (or, in fact, a set of such guesses ranked in order of most likely to less likely).

So once people know the algorithm it turns out that it can be tricked by mimicking the features that the computer is looking for: it's like constructing optical illusions for computers. On the left column of the images below (taken from [here](https://arxiv.org/pdf/1406.2661v1.pdf)) is a set of images that the computer identifies correctly. The right image looks the same to you and me, but it has actually been slightly modified to trick the computer, which confidently claims that all three of them show an ostrich.

[![](http://whimsley.s3.amazonaws.com/wordpress/wp-content/uploads/2017/02/Untitled1.png)](http://whimsley.s3.amazonaws.com/wordpress/wp-content/uploads/2017/02/Untitled1.png)

And here is a set of images constructed by the researchers listed [here](http://www.evolvingai.org/fooling), together with a 2014 state-of-the-art algorithm's confident interpretation of each:

[![](http://whimsley.s3.amazonaws.com/wordpress/wp-content/uploads/2017/02/Untitled2.png)](http://whimsley.s3.amazonaws.com/wordpress/wp-content/uploads/2017/02/Untitled2.png)

Deep learning algorithms are getting amazingly good at winning the game of image recognition, but those algorithms are not yet good at the game of outwitting opponents who want to trick them. The algorithms have been trained against honestly-labelled images, and faced with these tricks they are like the aliens in Galaxy Quest who do not understand the concept of "acting".

[![](http://whimsley.s3.amazonaws.com/wordpress/wp-content/uploads/2017/02/Untitled3.png)](http://whimsley.s3.amazonaws.com/wordpress/wp-content/uploads/2017/02/Untitled3.png)

The playing field of image recognition is different to that of strategy. Of course, algorithms have got good at strategic games (chess, Go, etc) but that's playing against an opponent who plays within the strict borders of well-defined rules. The challenge of fake news is that of outwitting an opponent who tips the board over and throws the pieces in your face.

There are two cases where Google has had to play against tricky opponents: dealing with spam email, and dealing with attempts to game its search engine rankings. Are these cause for optimism that it will be able to deal with toxic comments?

Probably not.		
