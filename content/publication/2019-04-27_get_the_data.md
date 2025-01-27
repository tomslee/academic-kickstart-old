---
author: Tom Slee
comments: true
date: 2017-04-27 16:46:21+00:00
layout: post
slug: airbnb-get-the-data
title: "Airbnb Data Collection: Get the Data"
---

Each link downloads a zip file of the data for a named city or region. The zip file holds one or more csv files. Each csv file represents a single “survey” or “scrape” of the Airbnb web site for that city. The data is collected from the public Airbnb web site without logging in and the code I use is available on [GitHub](https://github.com/tomslee/airbnb-data-collection).

Here is the data provided for each listing. Please note that while other data can be collected from the site, and while other sites (especially the excellent Inside Airbnb) collect richer data about the host and the details of each listing, I have no plans to expand the scope at the moment:

- room_id: A unique number identifying an Airbnb listing. The listing has a URL on the Airbnb web site of http://airbnb.com/rooms/room_id
- host_id: A unique number identifying an Airbnb host. The host’s page has a URL on the Airbnb web site of http://airbnb.com/users/show/host_id
- room_type: One of “Entire home/apt”, “Private room”, or “Shared room”
borough: A subregion of the city or search area for which the survey is carried out. The borough is taken from a shapefile of the city that is obtained independently of the Airbnb web site. For some cities, there is no borough information; for others the borough may be a number. If you have better shapefiles for a city of interest, please send them to me.
- neighborhood: As with borough: a subregion of the city or search area for which the survey is carried out. For cities that have both, a neighbourhood is smaller than a borough. For some cities there is no neighbourhood information.
- reviews: The number of reviews that a listing has received. Airbnb has said that 70% of visits end up with a review, so the number of reviews can be used to estimate the number of visits. Note that such an estimate will not be reliable for an individual listing (especially as reviews occasionally vanish from the site), but over a city as a whole it should be a useful metric of traffic.
- overall_satisfaction: The average rating (out of five) that the listing has received from those visitors who left a review.
- accommodates: The number of guests a listing can accommodate.
- bedrooms: The number of bedrooms a listing offers.
- price: The price (in $US) for a night stay. In early surveys, there may be some values that were recorded by month.
- minstay: The minimum stay for a visit, as posted by the host.
- latitude and longitude: The latitude and longitude of the listing as posted on the Airbnb site: this may be off by a few hundred metres. I do not have a way to track individual listing locations with
- last_modified: the date and time that the values were read from the Airbnb web site.

The first line of the CSV file holds the column headings.

Here are the cities, the survey dates, and a link to download each zip file.

### Aarhus

Survey dates: 2016-10-28 (2258 listings), 2016-11-26 (1900 listings), 2017-01-21 (2167 listings), 2017-02-21 (2295 listings), 2017-03-30 (2323 listings), 2017-04-18 (2398 listings), 2017-04-28 (2360 listings), 2017-05-15 (2437 listings), 2017-06-19 (2802 listings), 2017-07-28 (3142 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/aarhus.zip)

### Alpes Maritime

Survey dates: 2016-09-06 (24868 listings), 2017-01-28 (25888 listings), 2017-02-26 (26707 listings), 2017-04-24 (26057 listings), 2017-06-19 (28554 listings), 2017-07-12 (32343 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/alpes_maritime.zip)

### Amsterdam

Survey dates: 2014-05-24 (5645 listings), 2014-08-30 (6840 listings), 2015-01-19 (7693 listings), 2015-03-17 (7807 listings), 2015-12-16 (9850 listings), 2016-05-31 (13360 listings), 2016-08-04 (15314 listings), 2016-12-15 (17018 listings), 2017-01-18 (16871 listings), 2017-02-17 (16542 listings), 2017-03-27 (16362 listings), 2017-04-24 (17037 listings), 2017-05-12 (17201 listings), 2017-06-15 (17795 listings), 2017-07-22 (18723 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/amsterdam.zip)

### Anchorage

Survey dates: 2016-05-13 (447 listings), 2017-03-10 (728 listings),
2017-04-12 (764 listings), 2017-05-22 (842 listings), 2017-06-24 (932
listings), 2017-07-20 (969 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/anchorage.zip)

### Asheville

Survey dates: 2016-09-10 (757 listings), 2016-12-26 (799 listings),
2017-03-10 (783 listings), 2017-04-12 (788 listings), 2017-05-14 (810
listings), 2017-06-24 (848 listings), 2017-07-20 (854 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/asheville.zip)

### Asturias

Survey dates: 2017-07-02 (1225 listings), 2017-07-26 (1327 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/asturias.zip)

### Auckland

Survey dates: 2016-08-19 (4590 listings), 2016-12-26 (6103 listings),
2017-01-16 (6230 listings), 2017-02-12 (6507 listings), 2017-03-25 (7384
listings), 2017-04-13 (7889 listings), 2017-04-22 (8010 listings),
2017-05-10 (8487 listings), 2017-06-14 (8847 listings), 2017-07-19 (8815
listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/auckland.zip)

### Barcelona

Survey dates: 2014-05-20 (10441 listings), 2014-09-04 (10413 listings),
2015-01-14 (12467 listings), 2015-04-29 (10468 listings), 2015-11-06
(14012 listings), 2016-05-30 (17154 listings), 2016-07-25 (19145
listings), 2016-08-28 (18953 listings), 2016-10-22 (16383 listings),
2016-12-10 (15148 listings), 2017-01-18 (17153 listings), 2017-02-18
(17269 listings), 2017-03-27 (17385 listings), 2017-04-15 (17448
listings), 2017-04-24 (17572 listings), 2017-05-12 (17775 listings),
2017-06-15 (18558 listings), 2017-07-23 (18838 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/barcelona.zip)

### Belgium

Survey dates: 2016-12-30 (15711 listings), 2017-01-29 (15761 listings),
2017-02-28 (15695 listings), 2017-04-26 (15980 listings), 2017-06-19
(17093 listings), 2017-07-14 (17651 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/belgium.zip)

### Berlin

Survey dates: 2014-05-18 (7789 listings), 2015-01-19 (11553 listings),
2015-07-04 (12903 listings), 2015-11-07 (14132 listings), 2015-11-30
(14922 listings), 2016-05-01 (16135 listings), 2016-05-29 (8490
listings), 2016-08-30 (15680 listings), 2016-10-09 (16540 listings),
2016-12-15 (18551 listings), 2017-01-01 (18684 listings), 2017-01-17
(18312 listings), 2017-02-16 (18473 listings), 2017-03-26 (18999
listings), 2017-04-23 (19528 listings), 2017-05-11 (19681 listings),
2017-06-15 (20415 listings), 2017-07-21 (21864 listings25 (2443
listings), 2017-02-12 (2565 listings), 2017-03-11 (2580 listings),
2017-04-10 (2634 listings), 2017-05-08 (2645 listings), 2017-06-10 (2721
listings), 2017-07-10 (2954 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/calgary.zip)

### Cambridge MA

Survey dates: 2016-09-30 (1442 listings), 2017-03-10 (1694 listings),
2017-04-12 (1713 listings), 2017-05-14 (1765 listings), 2017-06-24 (1825
listings), 2017-07-20 (1809 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/cambriddates:%202016-07-10%20(2437%20listings),%202016-11-07%20(2222%20listings),%202017-01-30%20(2673%20listings),%202017-03-01%20(2743%20listings),%202017-04-27%20(2925%20listings),%202017-05-18%20(3045%20listings),%202017-06-19%20(3358%20listings),%202017-07-16%20(3582%20listings)%3C/p%3E%0A%3Cp%3E%3Ca%20href=)


### Florence

Survey dates: 2015-10-11 (5309 listings), 2015-11-02 (6175 listings),
2015-12-20 (6583 listings), 2016-01-07 (6698 listings), 2016-08-05 (8553
listings), 2016-09-12 (8525 listings), 2016-12-26 (8702 listings),
2017-01-24 (8725 listings), 2017-02-22 (8753 listings), 2017-04-04 (8945
listings), 2017-04-29 (9198 listings), 2017-05-19 (9215 listings),
2017-06-22 (9394 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/florence.zip)

### Frankfurt

Survey dates: 2016-03-27 (1580 listings), 2016-08-21 (1717 listings),
2016-12-26 (1944 listings), 2017-01-23 (1910 listings), 2017-02-22 (1968
listings), 2017-04-02 (1998 listings), 2017-04-28 (2134 listings),
2017-05-18 (1957 listings), 2017-06-22 (1995 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/frankfurt.zip)

### Geneva

Survey dates: 2014-11-26 (702 listings), 2016-08-09 (666 listings),
2017-01-23 (1663 listings), 2017-03-10 (1676 listings), 2017-04-12 (1738
listings), 2017-05-14 (1782 listings), 2017-06-24 (1849 listings),
2017-07-20 (1954 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/geneva.zip)

### Girona

Survey dates: 2017-05-13 (393 listings), 2017-06-04 (403 listings),
2017-06-23 (410 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/girona.zip)

### Granada

Survey dates: 2017-07-06 (3565 listings), 2017-07-25 (3595 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/granada.zip)

### Groningen

Survey dates: 2016-03-18 (382 listings), 2016-03-28 (386 listings),
2016-12-26 (533 listings), 2017-01-24 (588 listings), 2017-02-22 (607
listings), 2017-04-04 (610 listings), 2017-04-29 (648 listings),
2017-05-19 (645 listings), 2017-06-22 (706 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/groningen.zip)

### Helsinki

Survey dates: 2016-05-07 (1971 listings), 2016-12-26 (2742 listings),
2017-01-23 (2733 listings), 2017-04-02 (2792 listings), 2017-04-28 (2932
listings), 2017-05-18 (2936 listings), 2017-06-22 (3191 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/helsinki.zip)

### Houston

Survey dates: 2017-04-30 (7758 listings), 2017-05-08 (7712 listings),
2017-06-11 (7677 listings), 2017-07-13 (7559 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/houston.zip)

### Hungary

Survey dates: 2017-02-24 (4507 listings), 2017-04-28 (10517 listings),
2017-05-19 (10605 listings), 2017-06-21 (11141 listings), 2017-07-18
(12139 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/hungary.zip)

### Iceland

Survey dates: 2016-07-29 (4768 listings), 2016-09-24 (5005 listings),
2016-10-25 (4993 listings), 2016-11-29 (5180 listings), 2016-12-22 (5573
listings), 2017-01-27 (5629 listings), 2017-02-26 (5820 listings),
2017-04-23 (6255 listings), 2017-05-14 (6496 listings), 2017-06-18 (6876
listings), 2017-07-12 (7117 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/iceland.zip)

### Jersey City

Survey dates: 2016-05-26 (1284 listings), 2016-12-26 (1538 listings),
2017-03-10 (1561 listings), 2017-04-12 (1647 listings), 2017-05-14 (1694
listings), 2017-06-24 (1808 listings), 2017-07-20 (1798 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/jersey_city.zip)

### Joshua Tree

Survey dates: 2016-05-27 (227 listings), 2016-11-06 (234 listings),
2017-03-10 (154 listings), 2017-04-12 (160 listings), 2017-05-14 (171
listings), 2017-06-24 (174 listings), 2017-07-20 (178 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/joshua_tree.zip)

### Kenya

Survey dates: 2017-05-12 (4420 listings), 2017-07-23 (4764 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/kenya.zip)

### Kitchener Waterloo

Survey dates: 2016-05-22 (262 listings), 2016-09-22 (274 listings),
2016-10-28 (282 listings), 2016-12-10 (346 listings), 2016-12-25 (326
listings), 2017-02-12 (353 listings), 2017-03-11 (343 listings),
2017-04-10 (349 listings), 2017-05-08 (366 listings), 2017-06-10 (382
listings), 2017-07-10 (388 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/kitchener_waterloo.zip)

### Lake Tahoe

Survey dates: 2017-05-08 (4365 listings), 2017-06-29 (4342 listings),
2017-07-25 (4403 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/lake_tahoe.zip)

### Las Vegas

Survey dates: 2017-02-25 (5268 listings), 2017-03-10 (5261 listings),
2017-04-12 (5520 listings), 2017-05-14 (5691 listings), 2017-06-24 (5823
listings), 2017-07-20 (5830 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/las_vegas.zip)

### Lenox

Survey dates: 2017-06-25 (81 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/lenox.zip)

### Lincoln County

Survey dates: 2016-04-27 (435 listings), 2017-03-11 (810 listings),
2017-04-12 (492 listings), 2017-05-15 (878 listings), 2017-06-24 (941
listings), 2017-07-20 (1190 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/lincoln_county.zip)

### Linkoping

Survey dates: 2016-08-02 (57 listings), 2017-03-11 (50 listings),
2017-04-12 (50 listings), 2017-05-15 (56 listings), 2017-06-24 (67
listings), 2017-07-20 (70 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/linkoping.zip)

### Lisbon

Survey dates: 2015-03-18 (5652 listings), 2016-03-20 (8968 listings),
2016-06-02 (10272 listings), 2016-09-12 (10998 listings), 2016-12-26
(11668 listings), 2017-01-21 (11654 listings), 2017-02-21 (11792
listings), 2017-03-30 (12045 listings), 2017-04-18 (12287 listings),
2017-04-27 (12499 listings), 2017-05-15 (12797 listings), 2017-06-19
(13232 listings), 2017-07-27 (13578 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/lisbon.zip)

### London

Survey dates: 2013-12-21 (13054 listings), 2014-05-13 (13237 listings),
2015-01-17 (21298 listings), 2016-01-09 (34414 listings), 2016-08-07
(48515 listings), 2016-09-22 (47472 listings), 2016-12-26 (53313
listings), 2017-01-21 (53947 listings), 2017-03-31 (55846 listings),
2017-04-28 (57826 listings), 2017-06-19 (60561 listings), 2017-07-28
(64144 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/london.zip)

### Los Angeles

Survey dates: 2014-09-01 (10027 listings), 2014-09-18 (11317 listings),
2014-10-25 (11780 listings), 2015-04-06 (13899 listings), 2015-08-03
(15790 listings), 2015-08-27 (16649 listings), 2015-09-09 (16968
listings), 2015-10-13 (17420 listings), 2015-11-16 (18665 listings),
2015-12-10 (19709 listings), 2016-01-11 (18863 listings), 2016-02-10
(19311 listings), 2016-03-12 (19717 listings), 2016-04-12 (20951
listings), 2016-05-14 (21986 listings), 2016-06-14 (21996 listings),
2016-07-13 (23071 listings), 2016-08-15 (23793 listings), 2016-09-13
(24744 listings), 2016-10-14 (25347 listings), 2016-11-17 (24633
listings), 2016-12-17 (30735 listings), 2017-01-12 (29517 listings),
2017-02-10 (29316 listings), 2017-03-10 (29252 listings), 2017-04-06
(29955 listings), 2017-05-03 (30696 listings), 2017-06-05 (30829
listings), 2017-07-08 (32146 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/los_angeles.zip)

### Lyon

Survey dates: 2016-05-14 (7346 listings), 2016-10-02 (8106 listings),
2016-12-27 (9816 listings), 2017-03-11 (9494 listings), 2017-04-12 (9707
listings), 2017-05-15 (9856 listings), 2017-06-24 (10186 listings),
2017-07-20 (10409 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/lyon.zip)

### Madrid

Survey dates: 2014-08-29 (4790 listings), 2015-02-21 (5393 listings),
2017-03-11 (12615 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/madrid.zip)

### Mallorca

Survey dates

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/mallorca.zip)

### Melun

Survey dates: 2017-03-24 (37 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/melun.zip)

### Menorca

Survey dates: 2016-04-19 (1769 listings), 2016-04-20 (1757 listings),
2016-11-06 (1866 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/menorca.zip)

### Miami

Survey dates: 2015-08-17 (6947 listings), 2015-10-03 (7057 listings),
2015-10-18 (7414 listings), 2015-11-19 (7676 listings), 2015-12-12 (8349
listings), 2016-01-13 (8553 listings), 2016-02-12 (8855 listings),
2016-03-14 (9468 listings), 2016-04-12 (7034 listings), 2016-05-15 (7244
listings), 2016-06-15 (7162 listings), 2016-07-14 (7249 listings),
2016-08-16 (7212 listings), 2016-09-14 (7213 listings), 2016-10-15 (6563
listings), 2016-11-18 (6856 listings), 2016-12-21 (9811 listings),
2017-01-13 (7810 listings), 2017-02-12 (7845 listings), 2017-03-12 (7664
listings), 2017-04-07 (7586 listings), 2017-05-04 (7948 listings),
2017-06-04 (9608 listings), 2017-07-09 (8824 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/miami.zip)

### Montreal

Survey dates: 2014-08-30 (4424 listings), 2015-01-15 (6216 listings),
2015-09-02 (9236 listings), 2015-10-03 (9234 listings), 2016-06-29
(12476 listings), 2016-07-26 (12884 listings), 2016-08-20 (12587
listings), 2016-09-21 (12021 listings), 2016-10-27 (12444 listings),
2016-11-26 (11489 listings), 2016-12-08 (11518 listings), 2016-12-25
(13814 listings), 2017-02-11 (13729 listings), 2017-03-10 (13877
listings), 2017-04-10 (14342 listings), 2017-05-07 (14738 listings),
2017-06-10 (15286 listings), 2017-07-09 (15625 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/montreal.zip)

### Moscow

Survey dates: 2014-05-26 (1589 listings), 2014-08-24 (1843 listings),
2015-10-11 (3585 listings), 2015-11-02 (3819 listings), 2016-10-08 (5561
listings), 2017-03-11 (6201 listings), 2017-04-13 (6527 listings),
2017-05-15 (6789 listings), 2017-06-26 (6973 listings), 2017-07-21 (7200
listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/moscow.zip)

### Nairobi

Survey dates: 2017-05-12 (2516 listings), 2017-06-29 (2762 listings),
2017-07-25 (2837 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/nairobi.zip)

### Nantes

Survey dates: 2017-07-01 (2648 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/nantes.zip)

### Nashville

Survey dates: 2016-05-22 (3012 listings), 2016-08-30 (3486 listings),
2016-10-10 (3603 listings), 2016-12-16 (4067 listings), 2017-03-11 (4077
listings), 2017-04-13 (4357 listings), 2017-05-16 (4463 listings),
2017-06-26 (4787 listings), 2017-07-21 (4804 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/nashville.zip)

### New Orleans

Survey dates: 2015-01-16 (1905 listings), 2015-08-21 (2092 listings),
2015-10-03 (2667 listings), 2015-11-19 (2941 listings), 2015-12-13 (3041
listings), 2016-01-15 (3319 listings), 2016-02-15 (3697 listings),
2016-03-16 (3857 listings), 2016-04-12 (4177 listings), 2016-05-17 (4378
listings), 2016-06-16 (4069 listings), 2016-07-15 (4432 listings),
2016-08-17 (4482 listings), 2016-09-15 (4525 listings), 2016-10-16 (4449
listings), 2016-11-19 (4707 listings), 2017-01-13 (5067 listings),
2017-02-12 (5540 listings), 2017-03-12 (5663 listings), 2017-04-08 (5722
listings), 2017-05-04 (5855 listings), 2017-06-21 (3739 listings),
2017-07-10 (3862 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/new_orleans.zip)

### New York

Survey dates: 2014-05-10 (18921 listings), 2014-08-31 (20777 listings),
2014-10-17 (22388 listings), 2014-12-02 (25405 listings), 2015-02-27
(26441 listings), 2015-03-14 (28552 listings), 2015-08-10 (30001
listings), 2015-09-10 (30059 listings), 2015-10-13 (29898 listings),
2015-12-04 (33926 listings), 2015-12-21 (36062 listings), 2016-01-21
(36003 listings), 2016-02-25 (34935 listings), 2016-03-24 (34678
listings), 2016-04-03 (34380 listings), 2016-04-20 (34661 listings),
2016-05-23 (35067 listings), 2016-06-23 (34205 listings), 2016-07-20
(35547 listings), 2016-08-24 (37769 listings), 2016-09-20 (35620
listings), 2016-10-23 (35795 listings), 2016-11-26 (37439 listings),
2016-12-26 (39079 listings), 2017-01-15 (38768 listings), 2017-02-17
(37878 listings), 2017-03-14 (38549 listings), 2017-04-21 (39745
listings), 2017-05-06 (40733 listings), 2017-06-12 (39167 listings),
2017-07-12 (41245 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/new_york.zip)

### Newhaven CT

Survey dates: 2015-08-21 (369 listings), 2015-10-03 (475 listings),
2015-10-21 (431 listings), 2015-11-26 (567 listings), 2015-12-15 (586
listings), 2016-01-18 (604 listings), 2016-02-20 (632 listings),
2016-03-21 (678 listings), 2016-04-16 (473 listings), 2016-05-20 (481
listings), 2016-06-20 (489 listings), 2016-07-18 (444 listings),
2016-08-20 (431 listings), 2016-09-17 (444 listings), 2016-10-20 (448
listings), 2016-11-23 (471 listings), 2016-12-24 (407 listings),
2017-01-14 (359 listings), 2017-02-16 (373 listings), 2017-03-13 (370
listings), 2017-04-08 (388 listings), 2017-05-05 (420 listings),
2017-06-10 (414 listings), 2017-07-11 (428 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/newhaven_ct.zip)

### Newport

Survey dates: 2016-04-26 (57 listings), 2016-12-26 (70 listings),
2017-03-11 (94 listings), 2017-04-13 (61 listings), 2017-05-16 (83
listings), 2017-06-27 (138 listings), 2017-07-22 (148 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/newport.zip)

### Nice

Survey dates: 2016-06-25 (8802 listings), 2016-10-06 (9288 listings),
2016-12-08 (9444 listings), 2017-01-21 (9511 listings), 2017-02-21 (9604
listings), 2017-03-30 (9962 listings), 2017-04-18 (10168 listings),
2017-04-28 (10229 listings), 2017-05-16 (10576 listings), 2017-06-19
(11193 listings), 2017-07-28 (11629 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/nice.zip)

### Oahu

Survey dates: 2015-08-17 (2481 listings), 2015-10-18 (2696 listings),
2015-11-19 (2855 listings), 2015-12-12 (3086 listings), 2016-01-14 (3193
listings), 2016-02-13 (3214 listings), 2016-03-15 (3190 listings),
2016-04-14 (3539 listings), 2016-05-16 (3665 listings), 2016-06-15 (3844
listings), 2016-07-14 (3953 listings), 2016-08-17 (4020 listings),
2016-09-14 (4233 listings), 2016-10-15 (4200 listings), 2016-11-18 (4662
listings), 2016-12-21 (5146 listings), 2017-01-13 (5051 listings),
2017-02-12 (5249 listings), 2017-03-12 (5346 listings), 2017-04-07 (5610
listings), 2017-05-04 (5863 listings), 2017-06-08 (6028 listings),
2017-07-09 (6163 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/oahu.zip)

### Ottawa

Survey dates: 2016-05-16 (1496 listings), 2016-08-23 (1586 listings),
2016-09-21 (1624 listings), 2016-10-27 (1736 listings), 2016-12-07 (1897
listings), 2016-12-25 (1906 listings), 2017-02-12 (2003 listings),
2017-03-11 (2090 listings), 2017-04-10 (2257 listings), 2017-05-08 (2476
listings), 2017-06-10 (2919 listings), 2017-07-10 (3593 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/ottawa.zip)

### Palermo

Survey dates: 2016-09-14 (3635 listings), 2016-12-26 (3770 listings),
2017-03-11 (3872 listings), 2017-04-13 (3996 listings), 2017-05-16 (4086
listings), 2017-06-27 (4284 listings), 2017-07-22 (4434 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/palermo.zip)

### Paris

Survey dates: 2013-11-27 (19004 listings), 2014-05-16 (19946 listings),
2014-09-21 (27326 listings), 2014-12-26 (28826 listings), 2015-02-28
(31341 listings), 2015-12-17 (40005 listings), 2015-12-31 (41761
listings), 2016-05-26 (55951 listings), 2016-08-10 (62213 listings),
2017-01-01 (62963 listings), 2017-01-19 (62043 listings), 2017-02-18
(61666 listings), 2017-03-28 (62087 listings), 2017-04-25 (63634
listings), 2017-06-16 (65727 listings), 2017-07-25 (70158 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/paris.zip)

### Peel

Survey dates: 2016-09-24 (838 listings), 2016-10-29 (875 listings),
2016-12-09 (919 listings), 2016-12-25 (896 listings), 2017-02-12 (927
listings), 2017-03-11 (930 listings), 2017-04-10 (972 listings),
2017-05-08 (1017 listings), 2017-06-10 (1013 listings), 2017-07-10 (1064
listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/peel.zip)

### Philadelphia

Survey dates: 2015-08-20 (5990 listings), 2015-10-18 (7318 listings),
2015-11-19 (7177 listings), 2015-12-12 (7141 listings), 2016-01-14 (6895
listings), 2016-02-14 (7062 listings), 2016-03-16 (7026 listings),
2016-04-15 (6976 listings), 2016-05-16 (6813 listings), 2016-06-16 (6753
listings), 2016-07-15 (6921 listings), 2016-08-17 (6928 listings),
2016-09-15 (6904 listings), 2016-10-16 (6600 listings), 2016-11-19 (6875
listings), 2017-01-13 (7068 listings), 2017-02-12 (7152 listings),
2017-03-12 (7101 listings), 2017-04-07 (7090 listings), 2017-05-04 (7242
listings), 2017-06-08 (7391 listings), 2017-07-09 (7367 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/philadelphia.zip)

### Pittsburgh

Survey dates: 2017-04-30 (850 listings), 2017-05-08 (892 listings),
2017-06-12 (924 listings), 2017-07-13 (879 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/pittsburgh.zip)

### Portland

Survey dates: 2014-10-28 (1748 listings), 2015-02-22 (1900 listings),
2015-08-22 (1917 listings), 2015-10-23 (2622 listings), 2015-10-26 (2722
listings), 2015-11-21 (2847 listings), 2015-12-13 (2952 listings),
2016-01-15 (2897 listings), 2016-02-15 (2970 listings), 2016-03-17 (3077
listings), 2016-04-13 (3128 listings), 2016-05-17 (3238 listings),
2016-06-17 (3383 listings), 2016-07-15 (3496 listings), 2016-08-18 (3661
listings), 2016-09-15 (3714 listings), 2016-10-17 (3626 listings),
2016-11-19 (3914 listings), 2017-01-14 (3860 listings), 2017-02-16 (3837
listings), 2017-03-12 (3748 listings), 2017-04-08 (3634 listings),
2017-05-05 (3690 listings), 2017-06-09 (3815 listings), 2017-07-10 (3950
listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/portland.zip)

### Portland ME

Survey dates: 2016-07-31 (409 listings), 2017-03-12 (456 listings),
2017-04-13 (476 listings), 2017-05-16 (519 listings), 2017-06-27 (576
listings), 2017-07-22 (591 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/portland_me.zip)

### Porto

Survey dates: 2016-10-13 (4174 listings), 2016-12-12 (4461 listings),
2017-03-12 (4729 listings), 2017-04-13 (4971 listings), 2017-05-16 (5150
listings), 2017-06-27 (5561 listings), 2017-07-22 (5664 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/porto.zip)

### Prince Georges County

Survey dates: 2017-02-25 (1120 listings), 2017-03-12 (1121 listings),
2017-04-13 (1135 listings), 2017-05-16 (1149 listings), 2017-06-27 (1185
listings), 2017-07-22 (1203 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/prince_georges_county.zip)

### Quebec City

Survey dates: 2017-05-17 (2022 listings), 2017-06-11 (2120 listings),
2017-07-10 (2153 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/quebec_city.zip)

### Queenstown

Survey dates: 2017-03-28 (1171 listings), 2017-04-25 (1137 listings),
2017-05-10 (1205 listings), 2017-06-14 (1227 listings), 2017-07-18 (1210
listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/queenstown.zip)

### Reykjavik

Survey dates: 2016-04-24 (2551 listings), 2016-06-06 (2799 listings),
2016-06-30 (2936 listings), 2016-08-08 (2813 listings), 2016-09-11 (2821
listings), 2016-11-02 (2807 listings), 2016-11-23 (2996 listings),
2016-12-25 (3036 listings), 2017-01-01 (3053 listings), 2017-01-21 (2969
listings), 2017-02-22 (3046 listings), 2017-03-31 (3091 listings),
2017-04-19 (3237 listings), 2017-04-28 (3178 listings), 2017-05-16 (3306
listings), 2017-06-19 (3406 listings), 2017-07-28 (3650 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/reykjavik.zip)

### Richmond BC

Survey dates: 2017-01-13 (760 listings), 2017-02-12 (627 listings),
2017-03-13 (620 listings), 2017-04-12 (561 listings), 2017-05-12 (531
listings), 2017-06-14 (540 listings), 2017-07-13 (514 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/richmond_bc.zip)

### Rome

Survey dates: 2013-11-27 (1714 listings), 2014-05-19 (7810 listings),
2014-08-25 (9168 listings), 2014-11-28 (10778 listings), 2015-08-29
(15703 listings), 2016-01-06 (17900 listings), 2016-08-05 (23754
listings), 2016-09-11 (24061 listings), 2016-12-26 (25104 listings),
2017-01-16 (25275 listings), 2017-02-16 (25226 listings), 2017-03-25
(25430 listings), 2017-04-13 (25687 listings), 2017-04-22 (26000
listings), 2017-05-11 (26065 listings), 2017-06-14 (26206 listings),
2017-07-19 (26804 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/rome.zip)

### Saint Denis

Survey dates: 2017-03-10 (564 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/saint_denis.zip)

### Saint Lucia

Survey dates: 2016-09-25 (642 listings), 2017-03-12 (718 listings),
2017-04-14 (743 listings), 2017-05-17 (761 listings), 2017-06-27 (799
listings), 2017-07-23 (835 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/saint_lucia.zip)

### Saint Malo

Survey dates: 2017-05-17 (1285 listings), 2017-06-29 (1408 listings),
2017-07-25 (1460 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/saint_malo.zip)

### Salvador

Survey dates: 2017-07-01 (4308 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/salvador.zip)

### San Diego

Survey dates: 2014-05-25 (1901 listings), 2014-11-03 (2632 listings),
2015-08-22 (3318 listings), 2015-10-03 (4014 listings), 2015-10-23 (4222
listings), 2015-12-03 (4482 listings), 2015-12-16 (4587 listings),
2016-01-19 (4721 listings), 2016-02-22 (4813 listings), 2016-03-23 (4954
listings), 2016-04-18 (5356 listings), 2016-05-22 (5764 listings),
2016-06-21 (6257 listings), 2016-07-19 (7056 listings), 2016-08-22 (7177
listings), 2016-09-19 (7394 listings), 2016-10-22 (7481 listings),
2016-11-25 (7839 listings), 2016-12-25 (8030 listings), 2017-01-15 (8021
listings), 2017-02-17 (8054 listings), 2017-04-09 (8225 listings),
2017-05-06 (8316 listings), 2017-06-11 (8643 listings), 2017-07-11 (9111
listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/san_diego.zip)

### San Francisco

Survey dates: 2013-11-17 (215 listings), 2014-05-11 (4771 listings),
2014-08-24 (4771 listings), 2015-02-19 (5202 listings), 2015-06-05 (5305
listings), 2015-08-21 (5140 listings), 2015-10-21 (5587 listings),
2015-11-21 (7146 listings), 2015-12-14 (7399 listings), 2016-01-16 (7604
listings), 2016-02-17 (8549 listings), 2016-03-19 (8539 listings),
2016-04-15 (8051 listings), 2016-05-19 (7913 listings), 2016-06-04 (8669
listings), 2016-06-18 (7783 listings), 2016-07-17 (8037 listings),
2016-08-19 (7983 listings), 2016-09-17 (8076 listings), 2016-10-19 (8236
listings), 2016-11-21 (8407 listings), 2016-12-23 (8899 listings),
2017-01-14 (8508 listings), 2017-02-16 (8397 listings), 2017-03-12 (8286
listings), 2017-03-24 (8310 listings), 2017-04-08 (8319 listings),
2017-05-05 (8391 listings), 2017-07-10 (8344 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/san_francisco.zip)

### Santa Barbara

Survey dates: 2017-01-15 (467 listings), 2017-03-12 (403 listings),
2017-04-14 (398 listings), 2017-05-17 (359 listings), 2017-06-27 (351
listings), 2017-07-23 (384 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/santa_barbara.zip)

### Sao Paulo

Survey dates: 2017-07-01 (11118 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/sao_paulo.zip)

### Savannah

Survey dates: 2016-05-13 (494 listings), 2016-12-26 (615 listings),
2017-03-12 (717 listings), 2017-04-14 (752 listings), 2017-05-17 (777
listings), 2017-06-27 (835 listings), 2017-07-23 (877 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/savannah.zip)

### Seattle

Survey dates: 2015-09-01 (3223 listings), 2015-10-23 (3544 listings),
2015-11-28 (3715 listings), 2015-12-15 (3836 listings), 2016-01-19 (3871
listings), 2016-02-22 (3974 listings), 2016-03-22 (4048 listings),
2016-04-18 (4170 listings), 2016-05-22 (4413 listings), 2016-06-21 (4654
listings), 2016-07-19 (4935 listings), 2016-08-22 (5153 listings),
2016-09-18 (5253 listings), 2016-10-21 (5393 listings), 2016-11-24 (5654
listings), 2016-12-25 (5858 listings), 2017-01-15 (5717 listings),
2017-02-17 (5834 listings), 2017-03-13 (5816 listings), 2017-04-09 (5920
listings), 2017-05-06 (6062 listings), 2017-06-11 (6234 listings),
2017-07-11 (6399 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/seattle.zip)

### Seoul

Survey dates: 2016-05-29 (8519 listings), 2016-10-02 (9969 listings),
2016-12-28 (10690 listings), 2017-01-15 (10905 listings), 2017-01-15
(10930 listings), 2017-02-11 (11121 listings), 2017-03-24 (11544
listings), 2017-04-12 (11619 listings), 2017-04-21 (11723 listings),
2017-05-10 (11516 listings), 2017-06-14 (11965 listings), 2017-07-17
(12406 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/seoul.zip)

### Singapore

Survey dates: 2015-06-28 (2815 listings), 2016-06-11 (5796 listings),
2016-10-11 (6753 listings), 2017-03-12 (6828 listings), 2017-04-14 (7201
listings), 2017-05-17 (7212 listings), 2017-06-27 (7003 listings),
2017-07-23 (6834 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/singapore.zip)

### Sri Lanka

Survey dates: 2016-04-27 (7107 listings), 2016-09-24 (8725 listings),
2017-04-28 (11568 listings), 2017-06-21 (12176 listings), 2017-07-19
(12400 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/sri_lanka.zip)

### Switzerland

Survey dates: 2016-04-28 (15587 listings), 2016-08-13 (18901 listings),
2016-10-30 (19775 listings), 2016-11-30 (21043 listings), 2016-12-23
(22104 listings), 2017-01-26 (22506 listings), 2017-02-24 (23195
listings), 2017-04-21 (24992 listings), 2017-05-20 (25674 listings),
2017-06-16 (26398 listings), 2017-07-11 (27696 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/switzerland.zip)

### Sydney

Survey dates: 2014-09-26 (5567 listings), 2015-01-20 (7424 listings),
2015-03-20 (7871 listings), 2016-01-29 (13134 listings), 2016-06-11
(17343 listings), 2017-01-25 (23859 listings), 2017-03-12 (23297
listings), 2017-04-14 (24006 listings), 2017-05-17 (24419 listings),
2017-06-28 (25266 listings), 2017-07-23 (25506 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/sydney.zip)

### Tallin

Survey dates: 2016-07-08 (1378 listings), 2016-12-26 (1468 listings),
2017-01-24 (1483 listings), 2017-02-22 (1536 listings), 2017-04-04 (1574
listings), 2017-04-29 (1668 listings), 2017-05-19 (1708 listings),
2017-06-22 (1905 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/tallin.zip)

### Toronto

Survey dates: 2013-12-14 (2617 listings), 2014-05-18 (2656 listings),
2015-02-18 (4831 listings), 2015-06-29 (6587 listings), 2015-07-25 (6586
listings), 2015-11-21 (7607 listings), 2015-12-13 (7969 listings),
2016-01-15 (7980 listings), 2016-02-16 (8352 listings), 2016-03-17 (8452
listings), 2016-04-13 (9149 listings), 2016-05-18 (9446 listings),
2016-06-17 (9595 listings), 2016-07-16 (10155 listings), 2016-08-18
(10700 listings), 2016-09-15 (11026 listings), 2016-10-17 (11301
listings), 2016-11-20 (11735 listings), 2016-12-17 (12801 listings),
2017-01-14 (12597 listings), 2017-02-16 (12679 listings), 2017-03-12
(12528 listings), 2017-04-08 (12755 listings), 2017-05-05 (13042
listings), 2017-06-09 (13161 listings), 2017-07-10 (13267 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/toronto.zip)

### Turin

Survey dates: 2017-01-11 (3092 listings), 2017-03-13 (3205 listings),
2017-04-14 (3301 listings), 2017-05-18 (3403 listings), 2017-06-28 (3546
listings), 2017-07-24 (3662 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/turin.zip)

### Tuscany

Survey dates: 2016-08-02 (37295 listings), 2016-10-30 (38783 listings),
2017-05-04 (32850 listings), 2017-06-23 (24993 listings), 2017-07-20
(49286 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/tuscany.zip)

### Vancouver BC

Survey dates: 2015-04-25 (3036 listings), 2015-08-22 (3375 listings),
2015-11-26 (4595 listings), 2015-12-15 (4751 listings), 2016-01-17 (4731
listings), 2016-02-19 (4833 listings), 2016-03-20 (4916 listings),
2016-04-17 (5004 listings), 2016-05-20 (5209 listings), 2016-06-19 (5297
listings), 2016-07-18 (5611 listings), 2016-08-20 (5820 listings),
2016-09-17 (5926 listings), 2016-10-20 (5758 listings), 2016-11-22 (5611
listings), 2016-12-23 (5843 listings), 2017-01-14 (5619 listings),
2017-02-16 (5596 listings), 2017-03-13 (5588 listings), 2017-04-08 (5618
listings), 2017-05-05 (5781 listings), 2017-06-10 (5909 listings),
2017-07-10 (5994 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/vancouver_bc.zip)

### Veneto

Survey dates: 2016-11-07 (11543 listings), 2017-01-24 (15153 listings),
2017-01-30 (15218 listings), 2017-02-22 (15508 listings), 2017-03-01
(15743 listings), 2017-04-03 (16300 listings), 2017-04-29 (16940
listings), 2017-05-18 (17148 listings), 2017-06-19 (17915 listings),
2017-07-16 (18455 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/veneto.zip)

### Venice

Survey dates: 2015-12-20 (3161 listings), 2016-11-20 (5323 listings),
2016-12-27 (5727 listings), 2017-01-10 (5773 listings), 2017-01-23 (5801
listings), 2017-02-22 (5955 listings), 2017-04-02 (6120 listings),
2017-04-28 (6404 listings), 2017-05-18 (6402 listings), 2017-06-22 (6410
listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/venice.zip)

### Versailles

Survey dates: 2016-09-30 (6003 listings), 2017-03-13 (6052 listings),
2017-04-14 (6271 listings), 2017-05-18 (6515 listings), 2017-06-29 (6756
listings), 2017-07-24 (7175 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/versailles.zip)

### Victoria BC

Survey dates: 2016-07-08 (831 listings), 2016-11-06 (841 listings),
2016-12-10 (899 listings), 2016-12-25 (890 listings), 2017-02-12 (949
listings), 2017-03-11 (950 listings), 2017-04-10 (1004 listings),
2017-05-08 (1026 listings), 2017-06-10 (1063 listings), 2017-07-10 (1093
listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/victoria_bc.zip)

### Vienna

Survey dates: 2015-07-24 (5274 listings), 2015-08-01 (5445 listings),
2017-01-11 (7790 listings), 2017-03-13 (7787 listings), 2017-04-15 (7840
listings), 2017-05-18 (8010 listings), 2017-06-29 (8715 listings),
2017-07-25 (9252 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/vienna.zip)

### Warsaw

Survey dates: 2016-12-08 (3299 listings), 2016-12-14 (3389 listings),
2017-03-13 (3726 listings), 2017-04-15 (3863 listings), 2017-05-18 (4016
listings), 2017-06-29 (4325 listings), 2017-07-25 (4593 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/warsaw.zip)

### Washington

Survey dates: 2015-01-16 (2815 listings), 2015-08-22 (2800 listings),
2015-10-23 (3843 listings), 2015-11-26 (4081 listings), 2015-12-15 (4257
listings), 2016-01-18 (4245 listings), 2016-02-20 (4304 listings),
2016-03-21 (4290 listings), 2016-04-16 (4512 listings), 2016-05-20 (4756
listings), 2016-06-20 (4738 listings), 2016-07-18 (4960 listings),
2016-08-20 (5104 listings), 2016-09-18 (5186 listings), 2016-10-20 (5297
listings), 2016-11-23 (5975 listings), 2016-12-24 (7497 listings),
2017-01-14 (8885 listings), 2017-01-19 (9097 listings), 2017-02-16 (8475
listings), 2017-03-13 (8232 listings), 2017-04-08 (8061 listings),
2017-05-05 (8115 listings), 2017-05-11 (8085 listings), 2017-06-10 (8174
listings), 2017-07-11 (8237 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/washington.zip)

### Wellington

Survey dates: 2016-08-19 (858 listings), 2016-12-26 (1018 listings),
2017-01-16 (1039 listings), 2017-02-12 (1192 listings), 2017-03-25 (1338
listings), 2017-04-13 (1446 listings), 2017-04-22 (1455 listings),
2017-05-10 (1577 listings), 2017-06-14 (1894 listings), 2017-07-18 (1866
listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/wellington.zip)

### West Indies

Survey dates: 2016-09-28 (39195 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/west_indies.zip)

### Yellowknife

Survey dates: 2016-09-27 (67 listings), 2016-11-20 (78 listings),
2016-12-26 (84 listings), 2017-02-12 (93 listings), 2017-03-11 (89
listings), 2017-04-10 (83 listings), 2017-05-08 (93 listings),
2017-06-10 (95 listings), 2017-07-10 (88 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/yellowknife.zip)

### York

Survey dates: 2016-11-21 (551 listings), 2016-11-29 (754 listings),
2016-11-30 (587 listings), 2016-12-04 (495 listings), 2016-12-15 (511
listings), 2017-01-04 (92 listings), 2017-01-18 (496 listings),
2017-02-10 (519 listings), 2017-02-17 (532 listings), 2017-03-27 (545
listings), 2017-04-14 (563 listings), 2017-04-24 (561 listings),
2017-04-21 (607 listings), 2017-05-12 (580 listings), 2017-05-22 (139
listings), 2017-06-15 (617 listings), 2017-07-22 (670 listings)

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/york.zip)

### Zagreb

Survey dates

[Download zip
file](https://s3.amazonaws.com/tomslee-airbnb-data-2/zagreb.zip)

### Zurich

Survey dates: 2016-01-11 (912 listings), 2017-04-17 (2410 listings),
2017-05-18 (2271 listings), 2017-06-22 (2392 listings)

[Download zip file](https://s3.amazonaws.com/tomslee-airbnb-data-2/zurich.zip)
