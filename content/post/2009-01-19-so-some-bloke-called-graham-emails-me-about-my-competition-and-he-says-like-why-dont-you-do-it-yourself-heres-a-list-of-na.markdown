---
author: Tom Slee
comments: true
date: 2009-01-19 21:41:04+00:00
excerpt: "\n\t\t\t\t\t\t"
layout: post
link: http://tomslee.net/2009/01/so-some-bloke-called-graham-emails-me-about-my-competition-and-he-says-like-why-dont-you-do-it-yourself-heres-a-list-of-na.html
slug: so-some-bloke-called-graham-emails-me-about-my-competition-and-he-says-like-why-dont-you-do-it-yourself-heres-a-list-of-na
title: "\n\t\t\t\tTumbleweed blogs (firstname challenge again)\t\t"
wordpress_id: 141
---


				

So some bloke called Graham emails me about [my competition](http://whimsley.typepad.com/whimsley/2009/01/firstnameblogspotcom-a-challenge.html) and he says, like, why don't you do it yourself then? And here's a list of names: http://bel-epa.com/area51/library/names.txt.

So I says, OK then. I will. And I write myself a little python like this:



    
    <span style="font-size: 15px; font-family: Courier;">import httplib</span><br></br><span style="font-size: 15px; font-family: Courier;">import re</span><br></br><span style="font-size: 15px; font-family: Courier;">import sys</span><br></br><span style="font-size: 15px; font-family: Courier;">conn = httplib.HTTPConnection("bel-epa.com")</span><br></br><span style="font-size: 15px; font-family: Courier;">conn.request("GET", "/area51/library/names.txt")</span><br></br><br></br><span style="font-size: 15px; font-family: Courier;">namelist = conn.getresponse().read().split()</span><br></br><span style="font-size: 15px; font-family: Courier;">conn.close()</span><br></br><br></br><span style="font-size: 15px; font-family: Courier;">activenames = {}</span><br></br><span style="font-size: 15px; font-family: Courier;">inactivenames = {}</span><br></br><br></br><span style="font-size: 15px; font-family: Courier;">print len(namelist)</span><br></br><br></br><span style="font-size: 15px; font-family: Courier;">for name in namelist:</span><br></br><span style="font-size: 15px; font-family: Courier;"> try:</span><br></br><span style="font-size: 15px; font-family: Courier;"> host = name + ".blogspot.com"</span><br></br><span style="font-size: 15px; font-family: Courier;"> p = re.compile('200[0-9]<')</span><br></br><span style="font-size: 15px; font-family: Courier;"> conn = httplib.HTTPConnection(host)</span><br></br><span style="font-size: 15px; font-family: Courier;"> conn.request("GET", "")</span><br></br><span style="font-size: 15px; font-family: Courier;"> response = conn.getresponse()</span><br></br><span style="font-size: 15px; font-family: Courier;"> body = response.read()</span><br></br><span style="font-size: 15px; font-family: Courier;"> mo = p.search(body) </span><br></br><span style="font-size: 15px; font-family: Courier;"> if mo:</span><br></br><span style="font-size: 15px; font-family: Courier;"> activenames[name] = mo.group().rstrip('<')</span><br></br><span style="font-size: 15px; font-family: Courier;"> print name, mo.group().rstrip('<')</span><br></br><span style="font-size: 15px; font-family: Courier;"> else:</span><br></br><span style="font-size: 15px; font-family: Courier;"> inactivenames[name] = "null" </span><br></br><span style="font-size: 15px; font-family: Courier;"> print name, "null"</span><br></br><span style="font-size: 15px; font-family: Courier;"> except:</span><br></br><span style="font-size: 15px; font-family: Courier;"> print "Failure on " + name </span><br></br><span style="font-size: 15px; font-family: Courier;">conn.close()</span><br></br><br></br><span style="font-size: 15px; font-family: Courier;">f = open("blogdeath.csv", "w")</span><br></br><span style="font-size: 15px; font-family: Courier;">f.write("name,year\n")</span><br></br><span style="font-size: 15px; font-family: Courier;">for name, year in activenames.iteritems():</span><br></br><span style="font-size: 15px; font-family: Courier;"> f.write(name + "," + year + "\n")</span><br></br><span style="font-size: 15px; font-family: Courier;">for name, year in inactivenames.iteritems():</span><br></br><span style="font-size: 15px; font-family: Courier;">  f.write(name + ",1900\n")</span><br></br>

And then I plot the results and they look like this.  
[![Blogs](http://whimsley.typepad.com/.a/6a00d83451d3b369e2010536e5d40d970c-320wi)](http://whimsley.typepad.com/.a/6a00d83451d3b369e2010536e5d40d970c-popup)  
Which means that of the 7489 potential firstname.blogspot.com URLs:  




  * 2692 don't seem to have anything going on ever or have weird styling so I can't catch the date headers blogger templates usually use. A quick scan suggests that most are stillborn. See http://ned.blogspot.com/ or http://karim.blogspot.com/ for a couple of examples.


  * 361 were born and died in 2000.


  * 2001 and 2002 were the peak years for firstname blogs, with over 900 dying off each year. Not surprising that this is an early peak: the firstname places would be picked up quickly. Perhaps more surprising is that these blogs have been sitting there for 7 or 8 years, unattended, and blogger hasn't done anything with them.


  * The number of dying blogs falls off - meaning that the number of active ones does as well probably. Until now, only 96 blogs have been updated in the first three weeks of 2009.   





96 out of 7489. That's about one in 75 that are active. Pretty small numbers.  
  
How does this silly survey compare with a bigger picture? The Technorati annual review of blogging for 2008 [says](http://technorati.com/blogging/state-of-the-blogosphere/) that about 7.5 million blogs were updated in the 120 days before their report of 133 million that they have ever indexed: about one in 20 or so. Given the longer timeframe, not too bad a match. So 19 out of 20 blogs that have ever been started are now moribund.

And here, for those of you who are interested, the 96 firstname blogs still going strong are listed at the end of this post.   


My technorati ranking is
about 33 at the moment but I have been as high as 90. That puts me,
they say, in the top 1% of blogs. I get about 50 readers a day, many of
whom are googlers who probably land here and don't find what they are
looking for. And, on generous average, about one comment per post, so 99 out of a hundred bloggers get few readers and no comments. If these people are a typical sample, maybe one of them gets a comment per post. Maybe you should choose one and say hello.  


elvina  
adger  
minta  
cindi  
worden  
doretta  
grover  
carmen  
charlton  
hildagarde  
melesa  
lillian  
miranda  
delcina  
barbette  
urbanus  
tina  
jess  
roland  
bonny  
madalyn  
vivi  
corabella  
nikoletta  
faunie  
cherey  
henka  
terrill  
olive  
valli  
kamila  
cherice  
lorette  
daune  
orville  
sella  
johnathon  
aleecia  
madelina  
dottie  
dario  
roselyn  
merrie  
amalea  
ephraim  
trey  
werner  
antonino  
levon  
lavina  
saxe  
douglas  
meira  
danila  
winston  
lavinie  
teresita  
clovis  
chas  
letti  
anders  
edythe  
aileen  
luanna  
huntlee  
bancroft  
sidonnie  
fancie  
marcelline  
joella  
pauline  
engracia  
oran  
kirk  
rhonda  
leonardo  
claudia  
evette  
kris  
bird  
zia  
wilmette  
merrel  
fitz  
cain  
lindy  
hope  
dwain  
mareah  
sara  
berkley  
pinchas  
josselyn  
robinett  
oprah  
heidi  


  


  



		
