---
author: Tom Slee
comments: true
date: 2015-09-27 16:39:53+00:00
excerpt: "\n\t\t\t\tSome argue that open source software makes it more difficult for\
  \ developers to hand your personal info to the NSA, but the NSA happily makes its\
  \ data collection tools open source.\t\t"
layout: post
link: http://tomslee.net/2015/09/volkswagen-iot-the-nsa-and-open-source-software-a-quick-note.html
slug: volkswagen-iot-the-nsa-and-open-source-software-a-quick-note
title: "\n\t\t\t\tVolkswagen, IoT, the NSA and open source software: a quick note\t\
  \t"
wordpress_id: 3578
tags:
- iot
- openness
---


				(Attention conservation notice: the most interesting paragraph is the one about project NiFi, starting "Finley also writes...")

According to [Klint Finley in Wired](http://www.wired.com/2015/09/volkswagen-open-iot?utm_content=bufferae822), the lesson from the Volkswagen testing scandal is to use more open source software in more places. In particular, that Internet of Things (IoT) devices should be driven by open source software (even though the VW was not an IoT case). Here is Finley:


<blockquote>To protect consumers and realize its true promise, the Internet of Things must go the direction of the software and hardware that supports the Internet itself: it must open up...

Today, the vast majority of smart home gadgets, connected cars, wearable devices, and other Internet of Things inhabitants are profoundly closed... Ostensibly, this is for your own protection. If you can’t load your own software, you’re less likely to infect your car, burglar alarm, or heart monitor with a virus. But this opacity is also what helped Volkswagen get away with hiding the software it used to subvert emissions tests.</blockquote>


This seems wrong on two counts.

Finley writes about initiatives like the [OpenWrt](https://en.wikipedia.org/wiki/OpenWrt) operating system for embedded devices as an alternative, but a lot of IoT devices already run on Linux. What stops individuals from being able to exert control over their gadgets is the use of Linux permissions structures, not the openness of the OS code. IoT security frameworks will be much like security frameworks on Android and other mobile operating systems: sandboxed applications running in their own user space, using the security features of the operating system. The open source/closed source distinction is essentially irrelevant to the problem.

Finley also writes that the closed nature of some IoT devices "makes it harder to trust that your thermostat isn’t selling your personal info to door-to-door salesmen or handing it out to the National Security Agency." Which is ironic, because the software that might be handing out your personal info to the NSA _is already open source_. The NSA NiagaraFiles  project [provides](http://www.zdnet.com/article/nsa-partners-with-apache-to-release-open-source-data-traffic-program/) routes data among different computer networks and protocols. The NSA recently released this software as open source, and it is now hosted as an Apache project called [NiFi.](https://nifi.apache.org/) So that is the open source community (in the form of Apache) actively assisting the NSA in its data collection activities. The core developers on the project are all from the NSA and defense contractors ([link](https://wiki.apache.org/incubator/NiFiProposal)). And NiFi is being [touted ](http://www.zdnet.com/article/hortonworks-cto-on-apache-nifi-what-is-it-and-why-does-it-matter-to-iot/)as a big thing for IoT applications, so that your personal info can be more effectively routed to more destinations. The NiFi project is one more step in the active collaboration of Apache with the NSA, which I discussed back [here](http://tomslee.net/2013/06/should-the-apache-foundation-stop-hosting-accumulo.html) and [here](http://tomslee.net/2013/06/587.html), and tangentially in my [FORTHCOMING BOOK](http://www.orbooks.com/catalog/whats-yours-is-mine-by-tom-slee/).

The VW case is important and raises some big questions, but open-source vs closed source software is not  one of them. For a better take, see Zeynep Tufekci [here](http://www.nytimes.com/2015/09/24/opinion/volkswagen-and-the-era-of-cheating-software.html?_r=0).

(Full disclosure and openness: in my day job I have some involvement in IoT projects. My employer -- FOR WHOM I DO NOT SPEAK --uses a mixture of open source and proprietary code in its work.)		
