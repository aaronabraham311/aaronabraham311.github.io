---
description: Oct. 8, 2021
title: A Laymen's Explanation of Facebook's 2021 Outage
date: 2021-10-08
---
On October 4, 2021, Facebook and its affiliated apps mysteriously disappeared from the Internet for a couple of hours, costing the company hundreds of millions in lost revenue. Jokes about the incident ran amok on other social media platforms, but what was more interesting (at least to an engineer like myself) was the root cause of the incident.

Several individuals, articles and blog posts explained the technical reasons behind the outage, but I found them quite difficult to comprehend if you were not from a tech background. I wanted to take a stab at explaining this incident in a simple and concise post as a test of my technical and writing skills.
# How the Internet Actually Works: DNS and BGP

The underlying technology and principles of the Internet were the key reasons why this incident occured. Let's start by developing some context around how the Internet works.

Let's say we wanted to go to www.facebook.com. When you type this link and hit 'Enter', a series of processes take place. Here's a diagram:

![[image (22) (1).png]]

Let me try to explain this diagram in the context of a pizza delivery. Let's say that we are a pizza delivery person and we were just handed a hot pizza. What's the process?

1. You pick up the pizza and get the address
2. You get the full address from your GPS/phone
3. Figure out the route to the address
4. Drive to the address
5. Deliver the pizza and get your payment

Each of these steps is analogous to how a typical request works. When you type in facebook.com, that's akin to picking up a pizza and getting a rough address. Computers don't know what www.facebook.com is. They need an address to a server where they can get the information that you requested, just like how a pizza delivery person cannot just work off a street name. To get an exact address, computers will either have stored the address earlier or they will go to a DNS resolver, which will map the Facebook's server IP address to 'www.facebook.com'.

Once the computer has the address, the computer will then make a network connection to the Facebook server by going through a particular route. This is akin to a pizza delivery person mapping and driving through a route. How is this route determined on the Internet? That's where Border Gateway Protocol (BGP) comes in. BGP allows a network request to hop between different network until it reaches the server. Think of it like a GPS.

Once the request arrives at the Facebook server, the server will process the request and return information (like how the pizza is delivered to your door and you send payment). The server will return this information through a similar process to get your status updates, Instagram Reels and DMs to your device.

# Ok, so what exactly happened?

The best analogy to Facebook's outage is a pizza driver that cannot enter your street due to a street name change that wasn't published to a map. Thus, when a driver tries to figure out where you are located, they cannot even find an address because the address was not published.

In Facebook's case, a server configuration change stopped announcing the Facebook routes to BGP and to DNS resolvers. Thus, when people tried to search www.facebook.com, their devices pinged DNS resolvers but no valid IP address was returned.

This is also why all Facebook-related services were down. Because the entire 'street' of business was no longer publishing their address and routes, DNS resolvers couldn't direct requests to the correct address nor it could it give a good network route for requests to any of the services!

Why did it take so long to fix? There's some speculation around this, but I heard 2 decent reasons:

* **Cascading effects**: when a service like this goes down, it can become quite difficult to pin down the root cause because more problems keep popping up as more people try to access Facebook. Without figuring out the root cause, any fixes are pretty useless. It's like trying to repair a house without a roof without knowing you are missing a roof: you will have all types of problems but most of them can be fixed by putting up a roof. Facebook's engineers probably had a hard time figuring out the root cause (it's easy for me to say this while I sit typing this up)
* **Lack of access due to coronavirus**: since this issue is closely related to server networks, the only decent way of fixing this issue is to go into Facebook's server centre and fix the problem. Coronavirus may have limited the number of engineers in the centre and caused a long delay in actually fixing the issue

# Why should we care?

For the common person, these root cause analyses don't mean much. However, the incident has mainly showed us why it is dangerous to depend on platforms: many businesses and individuals derive a large source of their income, architecture and security (and dare I say identity) from platforms like Facebook. Another example would be Amazon: a huge portion of today's Internet (including our beloved Netflix) runs on AWS and AWS outages are often the most impactful for individuals and companies. When such power is concentrated in 1 platform, it becomes critical for engineers to maintain as high of an uptime as possible; billions of dollars can be wiped out in seconds without proper guardrails.

As more of the world becomes online, Internet infrastructure can either become a huge bottleneck or a conduit for better times. Our response to events like these determine the outcome.

# Resources

I have to give credit to these three resources. If you are interested in the technical underpinnings of the post, these three links would be a good start:

* [Cloudflare's analysis](https://blog.cloudflare.com/october-2021-facebook-outage/)
* [Hussein Nasser's analysis](https://www.youtube.com/watch?v=JODWEal5vko)
* [Facebook's analysis](https://engineering.fb.com/2021/10/04/networking-traffic/outage/)

The fidelity of this post is quite low, but I intended this to be a test of simplification rather than a test of technical prowess. Hence, I may have made a few mistakes in this analysis, but I believe the overall picture is correct.
