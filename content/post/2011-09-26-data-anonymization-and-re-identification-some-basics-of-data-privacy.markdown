---
author: Tom Slee
comments: true
date: 2011-09-26 23:49:24+00:00
excerpt: "\n\t\t\t\t\t\t"
layout: post
link: http://tomslee.net/2011/09/data-anonymization-and-re-identification-some-basics-of-data-privacy.html
slug: data-anonymization-and-re-identification-some-basics-of-data-privacy
title: "\n\t\t\t\tData Anonymization and Re-identification: Some Basics Of Data Privacy\t\
  \t"
wordpress_id: 33
---


				

_Why Personally Identifiable Information is irrelevant. __An introduction to information entropy, open data, and the possible  end of crowdsourcing. _







### Tim O'Reilly and ZIP Codes







From his [Strata Conference on Data Science](http://strataconf.com/strata2012), Tim O'Reilly [tweeted](https://twitter.com/#!/timoreilly/status/115772828120383489) with  dismay the recent California court decision that the zipcode is now to  be classified as "personally identifiable information". "No more  demographics" he lamented. A little later he [retweeted](https://twitter.com/#!/timoreilly/status/115776752017620992) a response that  "apparently 87% of US residents can be uniquely identified by  zip+DOB+gender: bit.ly/qysMqs" and later [followed up](https://twitter.com/#!/timoreilly/status/117592754439192576) with "Here's a  reference for the claim that zip code, gender and DOB uniquely  identify 87% of individuals:  [http://www.citeulike.org/user/burd/article/5822736](http://www.citeulike.org/user/burd/article/5822736) via @crdant".




These tweets are odd and disturbing. The zip/DOB/gender finding is a  basic one in studies of privacy, published years ago by Latanya  Sweeney of Carnegie Mellon University. I gave a talk at work on  privacy a year ago, and this was one of the first references I came  across. Tim O'Reilly has been pushing an agenda of Open Data,  particularly Open Government Data, for the last couple of years, and  yet it looks as if he isn't aware of the basic privacy issues around  such data. Can that really be the case?




If it is, then here, to help Tim along, are some notes from my talk as  a kind of introduction to data privacy, or at least to  data-anonymization and re-identification. A great resource on some of  these issues from a legal perspective is Paul Ohm's 2009 paper "Broken  Promises of Privacy: Responding to the Surprising Failures of  Anonymization" ([PDF](http://epic.org/privacy/reidentification/ohm_article.pdf)), University of Colorado Law Legal Studies  Research Paper No. 09-12. It's long, but it's so well written it's an  easy read. Much of these notes originated with this paper, in one form  or another.













### How Privacy Broke Crowdsourcing







A few years ago Netflix ran its highly successful and widely  publicised crowdsourced prize competition, in which it released a data  set of users and their movie ratings and let competitors download them  and search for patterns. The data consisted of a customer ID (faked),  a movie, the customer's rating of the movie, and the date of the  rating.




In the FAQ for the competition, Netflix said this:




Q. Is there any customer information in the dataset that should be  kept private?




A. No, all customer identifying information has been removed; all that  remains are ratings and dates. This follows our privacy policy… Even  if, for example, you knew all your own ratings and their dates you  probably couldn't identify them reliably in the data because only a  small sample was included (less than one tenth of our complete  dataset) and that data was subject to perturbation.




This certainly looked reasonable enough, but Arvind Narayanan and  Vitaly Shmatikov of the University of Texas had other ideas.1 First,  they looked at the claim that the data was perturbed by asking  acquaintances for their rankings. They found that only a small number  of the ratings were perturbed at all, which makes sense because  perturbing the data gets in the way of its usefulness.




In the Netflix data set, different users have distinct sets of movies  that they have watched. The data set is sparse (most people have not  seen most movies), and there are many different movies available, so  individual tastes and viewing histories leave a clear  fingerprint. That is, if you knew what movies someone watched, you  could pick them out of the data set because no one else would have  seen the same combination.




A closer look showed that with 8 ratings (of which 2 may be completely  wrong) and dates that may have a 14-day error, 99% of the records in  the Netflix data set uniquely identify an individual.  For 68% of  records, two ratings and dates are sufficient. Various combinations of  information are sufficient to identify users, eg 84% by 6 of 8 movies  outside the top 500.




But of course there is no personally identifiable information in the  data set. So is this a privacy issue? It is when you have another data  set to look at. The researchers took a sample of 50 IMDB users. The  IMDB data is noisy - there is no ranking, for example. Still, they  identified two users whose Netflix records were 28 and 15 standard  deviations away from the next best. One from ratings, another from  dates.




So despite Netflix's best efforts, the data set included enough  information to identify some individuals. Partly because of this, a  planned follow-up competition was scrapped, and the whole enterprise  of crowdsourcing recommender algorithms was given a possibly terminal  blow.













### What's this all about?







Just to be clear, this set of notes is not about the following things:






  * Encryption 


  * Restricting access to data 


  * Lost USB keys and CDs 




It is about these:






  * Deliberately released data that turns out to infringe on privacy 


  * HIPAA, EU Data Directive, corporate rules for handling customer data 


  * Advertising and ISPs 


  * Gov 2.0, data.gov, and "openness"




It's about claims such as: "Attorneys on Monday accused Google of  intentionally divulging millions of users' search queries to third  parties in violation of federal law and its own terms of service"  (October 26 2010)




"MySpace and some popular applications on the social-networking site  have been transmitting data to outside advertising companies that  could be used to identify users, a Wall Street Journal investigation  has found" (October 23, 2010)




"Facebook users may inadvertently reveal their sexual preference to  advertisers in an apparent wrinkle in the social-networking site's  advertising system, researchers have found" (October 22, 2010)




(These claims are a year old, found in the week before I gave the  talk. I'm sure there are many more.) The Facebook case was one in  which advertisers (for a nursing program I believe) asked to target  their ads specifically at females and at men interested in other  men. But unlike, for example, an ad about a gay bar where the target  demographic is blatantly obvious, a male user reading the ad text would  have no idea that it had been targeted solely at a very specific  demographic, and that by clicking it he would reveal to the advertiser  both his sexual preference and a unique identifier (cookie, IP  address, or e-mail address if he signs up on the advertiser's site).  "Furthermore (the researchers [wrote](http://www.pcworld.com/article/208583/facebook_ads_could_out_gay_users_researchers_say.html)) such deceptive ads are not  uncommon; indeed exactly half of the 66 ads shown exclusively to gay  men (more than 50 times) during our experiment did not mention 'gay'  anywhere in the ad text."













### Don't we have laws to deal with this?







Indeed we do. Europe and the USA adopt different approaches to  balancing privacy and utility, with the US adopting industry-specific  rules (HIPAA for health, FERPA for education, Driver's Privacy  Protection Act, FDA regulations, Video Privacy Protection Act etc),  while the EU has taken a global approach with the Data Protection  Directive. But both approaches are based on a common set of concepts  and assumptions.




The big thing is that there is an assumption that data can be  anonymized, and once it is then you can share it, because where's the  harm? Both sets of rules are built on the idea that there is such a  thing as personally identifiable information (PII) and that you can  hide it, while still releasing data that is useful. The release  process is "release and forget" because if data is properly anonymized  why do you have to track what's done with it? There is a faith in the  anonymization process, and that faith was broken by the Netflix study  and a couple of other related studies.













### Latanya Sweeney and the Massachusetts Governor







Let's go back to a time before HIPAA, when the debate was focused in  terms of _how much_ anonymization you needed to do. Here are some  quotations from Latanya Sweeney's paper ([PDF](http://epic.org/privacy/reidentification/Sweeney_Article.pdf)), that Tim O'Reilly appeared  unaware of.




"Figure 1" below is a simple Venn diagram with two intersecting  circles. The left circle holds medical data: Ethnicity, Visit Date,  Diagnosis, Procedure, Medication, Total Charge. The right circle holds  a voter list: Name, Address, Date Registered, Party Affiliation, Date  Last Voted. And in the intersection is ZIP, Date of Birth, Sex.




<blockquote>

> 
> The National Association of Health Data Organizations (NAHDO) reported  that 37 states in the USA have legislative mandates to collect  hospital level data and that 17 states have started collecting  ambulatory care data from hospitals, physicians offices, clinics, and  so forth. The leftmost circle in Figure 1 contains a subset of the  fields of information, or attributes, that NAHDO recommends these  states collect; these attributes include the patient's ZIP code, birth  date, gender, and ethnicity.
> 
> 

> 
> In Massachusetts, the Group Insurance Commission (GIC) is responsible  for purchasing health insurance for state employees. GIC collected  patient-specific data with nearly one hundred attributes per encounter  along the lines of the those shown in the leftmost circle of Figure 1  for approximately 135,000 state employees and their families. Because  the data were believed to be anonymous, GIC gave a copy of the data to  researchers and sold a copy to industry.
> 
> 

> 
> For twenty dollars I purchased the voter registration list for  Cambridge Massachusetts and received the information on two  diskettes. The rightmost circle in Figure 1 shows that these data  included the name, address, ZIP code, birth date, and gender of each  voter. This information can be linked using ZIP code, birth date and  gender to the medical information, thereby linking diagnosis,  procedures and medications to particularly named individuals.
> 
> 

> 
> For example, William Weld was governor of Massachusetts at that time  and his medical records were in the GIC data. Governor Weld lived in  Cambridge Massachusetts. According to the Cambridge Voter list, six  people had his particular birth date; only three of them were men;  and, he was the only one in his 5-digit ZIP code. [Editor's note: a  5-digit zip code may have several thousand people in it.]
> 
> 

> 
> The example above provides a demonstration of re-identification by  directly linking (or "matching") on shared attributes. The work  presented in this paper shows that altering the released information  to map to many possible people, thereby making the linking ambiguous,  can thwart this kind of attack. The greater the number of candidates  provided, the more ambiguous the linking, and therefore, the more  anonymous the data.
> 
> 
</blockquote>




In a theatrical flourish, Dr. Sweeney sent the Governor's health  records (which included diagnoses and prescriptions) to his office.




Now, of course, health information in the US is governed by HIPAA, but  according to HIPAA, "de-identified" health information is unregulated.  _De-identified_ means either: a statistician says it is de-identified,  or the 18 Personally Identifying Information (PII) identifiers are  suppressed or generalized. These PIIs are things like Name, e-mail  address, social security numbers, computer IP addresses, and so on.




The EU doesn't list specifics. Instead it says that PII is "anything  that can be used to identify you". But what does that cover? IP  addresses perhaps? Here is Google in their argument to the EU:






  * we "are strong supporters of the idea that data protection laws  should apply to any data that could identify you. The reality is  though that in most cases, an IP address without additional  information cannot."


  * "We believe anonymizing IP addresses after 9 months and cookies in  our search engine logs after 18 months strikes the right balance."


  * "we delete the last octet after nine months (170.123.456.XXX)"




The Latanya Sweeney result was the first to show that once you can mix  and match data sets, PII is just not enough to provide privacy. And  nowadays, of course, data mining multiple data sets is big business.













### How Do You Anonymize Data? k-anonymity







Let's step back a little and look at the technical side of  anonymization. There are four basic methods for anonymizing data:








Replacement - substitute identifying numbers
Suppression - omit from the released data
Generalization - for example, replace birth date with something  less specific, like year of birth
Perturbation - make random changes to the data





Then you have to measure how private a data set. Latanya Sweeney came  up with the notion of k-anonymity to define this. Here's how it works.




Think about a table, with rows and attributes. Each attributes is  either part of a quasi-identifier (like a name or address), or is  sensitive information (like the fact you had an operation on a  particular afternoon).  A quasi-identifier is a set of attributes  that, perhaps in combination, can uniquely identify individuals.  Sensitive information includes the attributes that we want to keep  private.  Your driving license number is an identifier; our driving  record is sensitive information.  The table satisfies _k-anonymity_ iff  each sequence of values in any quasi-identifier appears with at least  k occurrences.  Bigger k is better.




So here is a table with 11 rows.


<table cellpadding="6" cellspacing="0" frame="hsides" border="2" rules="groups" >

<tr >
NameRaceBirthGenderZipProblem
</tr>

<tbody >
<tr >

<td class="left" >Sean
</td>

<td class="left" >Black
</td>

<td class="right" >1965-09-20
</td>

<td class="left" >M
</td>

<td class="right" >02141
</td>

<td class="left" >Short breath
</td>
</tr>
<tr >

<td class="left" >Daniel
</td>

<td class="left" >Black
</td>

<td class="right" >1965-02-14
</td>

<td class="left" >M
</td>

<td class="right" >02141
</td>

<td class="left" >Chest pain
</td>
</tr>
<tr >

<td class="left" >Kate
</td>

<td class="left" >Black
</td>

<td class="right" >1965-10-23
</td>

<td class="left" >F
</td>

<td class="right" >02138
</td>

<td class="left" >Hypertension
</td>
</tr>
<tr >

<td class="left" >Marion
</td>

<td class="left" >Black
</td>

<td class="right" >1965-08-24
</td>

<td class="left" >F
</td>

<td class="right" >02138
</td>

<td class="left" >Hypertension
</td>
</tr>
<tr >

<td class="left" >Helen
</td>

<td class="left" >Black
</td>

<td class="right" >1964-07-11
</td>

<td class="left" >F
</td>

<td class="right" >02138
</td>

<td class="left" >Obesity
</td>
</tr>
<tr >

<td class="left" >Reese
</td>

<td class="left" >Black
</td>

<td class="right" >1964-01-12
</td>

<td class="left" >F
</td>

<td class="right" >02138
</td>

<td class="left" >Chest Pain
</td>
</tr>
<tr >

<td class="left" >Forest
</td>

<td class="left" >White
</td>

<td class="right" >1964-10-23
</td>

<td class="left" >M
</td>

<td class="right" >02138
</td>

<td class="left" >Chest Pain
</td>
</tr>
<tr >

<td class="left" >Hilary
</td>

<td class="left" >White
</td>

<td class="right" >1964-03-15
</td>

<td class="left" >F
</td>

<td class="right" >02139
</td>

<td class="left" >Obesity
</td>
</tr>
<tr >

<td class="left" >Philip
</td>

<td class="left" >White
</td>

<td class="right" >1964-08-13
</td>

<td class="left" >M
</td>

<td class="right" >02139
</td>

<td class="left" >Short breath
</td>
</tr>
<tr >

<td class="left" >Jamie
</td>

<td class="left" >White
</td>

<td class="right" >1967-05-05
</td>

<td class="left" >M
</td>

<td class="right" >02139
</td>

<td class="left" >Chest pain
</td>
</tr>
<tr >

<td class="left" >Sean
</td>

<td class="left" >White
</td>

<td class="right" >1967-03-21
</td>

<td class="left" >M
</td>

<td class="right" >02138
</td>

<td class="left" >Chest pain
</td>
</tr>
</tbody>
</table>


If we remove all the attributes except for the problem we have a very  anonymized data set (k = 11):


<table cellpadding="6" cellspacing="0" frame="hsides" border="2" rules="groups" >

<tr >
NameRaceBirthGenderZipProblem
</tr>

<tbody >
<tr >

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >Short breath
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >Chest pain
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >Hypertension
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >Hypertension
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >Obesity
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >Chest Pain
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >Chest Pain
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >Obesity
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >Short breath
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >Chest pain
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >
</td>

<td class="left" >Chest pain
</td>
</tr>
</tbody>
</table>


On the other hand, if we just remove the name and generalize the zip  code and date of birth we have a less anonymized set. Exercise: convince yourself that  k=2 for this set.


<table cellpadding="6" cellspacing="0" frame="hsides" border="2" rules="groups" >

<tr >
NameRaceBirthGenderZipProblem
</tr>

<tbody >
<tr >

<td class="left" >
</td>

<td class="left" >Black
</td>

<td class="right" >1965
</td>

<td class="left" >M
</td>

<td class="left" >0214*
</td>

<td class="left" >Short breath
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >Black
</td>

<td class="right" >1965
</td>

<td class="left" >M
</td>

<td class="left" >0214*
</td>

<td class="left" >Chest pain
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >Black
</td>

<td class="right" >1965
</td>

<td class="left" >F
</td>

<td class="left" >0213*
</td>

<td class="left" >Hypertension
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >Black
</td>

<td class="right" >1965
</td>

<td class="left" >F
</td>

<td class="left" >0213*
</td>

<td class="left" >Hypertension
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >Black
</td>

<td class="right" >1964
</td>

<td class="left" >F
</td>

<td class="left" >0213*
</td>

<td class="left" >Obesity
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >Black
</td>

<td class="right" >1964
</td>

<td class="left" >F
</td>

<td class="left" >0213*
</td>

<td class="left" >Chest Pain
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >White
</td>

<td class="right" >1964
</td>

<td class="left" >M
</td>

<td class="left" >0213*
</td>

<td class="left" >Chest Pain
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >White
</td>

<td class="right" >1964
</td>

<td class="left" >F
</td>

<td class="left" >0213*
</td>

<td class="left" >Obesity
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >White
</td>

<td class="right" >1964
</td>

<td class="left" >M
</td>

<td class="left" >0213*
</td>

<td class="left" >Short breath
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >White
</td>

<td class="right" >1967
</td>

<td class="left" >M
</td>

<td class="left" >0213*
</td>

<td class="left" >Chest pain
</td>
</tr>
<tr >

<td class="left" >
</td>

<td class="left" >White
</td>

<td class="right" >1967
</td>

<td class="left" >M
</td>

<td class="left" >0213*
</td>

<td class="left" >Chest pain
</td>
</tr>
</tbody>
</table>


Of course, the issue is utility. There is a tradeoff between keeping  the data useful for research and maintaining privacy. Researchers and  attackers are doing the same thing after all: looking for useful  patterns in the data.  With the k=2 data set you can ask questions  about correlation of problems with gender, or with geography to some  extent (although not very specific geographical factors, like toxic  leaks).




It would be nice if you could make the data set anonymous for the  purposes of attackers, but still useful for researchers. But it turns  out you can't. In a paper called _The Cost of Privacy: Destruction of Data-Mining Utility in Anonymized Data Publishing_, Justin Brickell and  Vitaly Shmatikov investigated the problem. They took a set of  different sanitization methods and compared it to a data set with  trivial sanitization (removal of identifiers). Here are the results.




[![Privacy_utility](http://whimsley.typepad.com/.a/6a00d83451d3b369e2015391e4feb4970b-320wi)](http://whimsley.typepad.com/.a/6a00d83451d3b369e2015391e4feb4970b-popup)   
  





The left bar of each pair is the privacy (smaller = more private), The  right represent the utility to the researcher (bigger = more  useful). Anonymization seeks to shorten left without shortening the  right, but the results show, depressingly, that small increases in  privacy cause large decreases in utility.













### Please could you tell me about the Database of Ruin?







OK, if you insist.




If we are going to take a new look, we need to recognize that privacy  is not a binary issue, and _it is not a property of a single data set_. We need to worry about reidentification attacks that do not reveal  sensitive information. As Paul Ohm writes: "For every person on earth,  there is at least one fact about them stored in a computer database  that an adversary could use to blackmail, discriminate against,  harass, or steal the identity of him or her… the 'database of ruin'  containing this fact but now splintered across dozens of databases on  computers around the world."




Privacy is erased incrementally as successive queries reduce  uncertainty and narrow in on an individual. The way to quantify this  reduction in uncertainty is to use the idea of _information entropy_,  adopted from the thermodynamic concept, and usually identified by  H. The information gained in a query is




H(before) - H(after)




as you  increase your knowledge of a system, the entropy (loosely, disorder)  decreases.




So what is the formula for H?




For a set of outcomes {i,…}, each with probability pi, the  information entropy is:




H = - SUM pi log2(pi)




(excuse the lack of greek sigma), and is measured in bits. The  logarithm appears because the probability of two independent events  occurring is the product of the probabilities of each event, but the  information we gain from observing two independent events is the sum  of the information we gain from each event




Take a simple example: a coin toss. Before the toss, there are two  outcomes with equal probabilities, so




H =  -(1/2) log2(1/2) - (1/2)log2(1/2)




= - log2(1/2)




= log2(2)




= 1 bits




which makes sense if you think about it, because the coin could be heads  (1) or tails (0).




After the toss, H = log2(1) = 0 : there is no uncertainty left and we  have complete information about the system.




In the same way, a dice roll has (before rolling it) an entropy of




H = log2(6) ~ 2.6 bits




So if the challenge is to identify one person in the population of the  world, how much information entropy is there?  The identity of a  random, unknown person is just under 33 bits (233 ~ 8 billion). Hence  the web site 33bits.org.




Learning a fact about the individual reduces the uncertainty (reduces  information entropy). So if you learn that the star sign is Capricorn  then that's -log2(1/12) = log2(12) = 3.58 bits of information.




If you find out other independent pieces of information you add up the  contributions to find out how much the the entropy has been  reduced. So a ZIP code may provide 23.81 bits of information, a  birthday 8.51, and gender 1 bit for a total of 33.32 bits: it probably  identifies one individual.




The Netflix de-anonymization paper used these ideas a bit.  The a  priori entropy of the data set (additional information required for  complete de-anonymization) is 19 bits (219 = 524288, which is about  the number of individuals in the data set).  Individual movies give  from 1 to 18 bits of information, depending on what you know about  them (dates within 14 days, rankings +/- 1).  Very popular movies gave  little information, but niche movies viewed by few individuals yielded  many bits of information. So little auxiliary information is needed to  re-identify records in the database.  In a theoretical excursion, the  researchers showed that de-anonymization is going to be robust against  noise, and does not need much additional information, so long as the  data set is large and sparse enough.













### So what now?







I can do nothing better than quote from Paul Ohm to summarize the  privacy dilemma we find ourselves in.




"Abandoning PII is a disruptive and necessary first step, but it is  not enough alone to restore the balance between privacy and utility  that we once enjoyed. How do we fix the dozens, perhaps hundreds, of  laws and regulations that we once believed reflected a finely  calibrated balance but in reality rested on a fundamental  misunderstanding of science?




Techniques that eschew release-and-forget may improve over time, but  because of inherent limitations like those described above, they will  never supply a silver bullet alternative.  Technology cannot save the  day, and regulation must play a role.




Ohm notes that the US sectoral approach to regulation sets the privacy  bar too low, by focusing on explicitly listed PII. Meanwhile the EU, by  saying "anything that can be used to identify you" would, if  interpreted in the light of modern de-anonymization techniques, be too  high.




The direction to take, says Ohm, is to focus on the people, not the  anonymization, and to distinguish private from public release. We need  to codify notions of trust and practices and apply strong sanctions  against re-identification. This will put more administrative and  procedural burdens in our future, but is needed to preserve privacy.




And, to return to Tim O'Reilly's tweet, open data advocates and big  data enthusiasts need to pay more attention to these issues rather  than relying, as some do, on personally identifying information as a  sufficient solution.













## Footnotes:







1 Arvind Narayanan and Vitaly Shmatikov, _Robust De-anonymization of Large Sparse Datasets_, IEEE Symposiom on Security and  Privacy, 2008. ([gated link](http://dl.acm.org/citation.cfm?id=1398064))








		
