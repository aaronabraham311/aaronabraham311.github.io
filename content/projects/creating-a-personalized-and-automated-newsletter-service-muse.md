---
description: "Published: May 9, 2021"
title: "Creating a personalized and automated newsletter service: Muse"
date: 2021-05-09
tags:
  - technical
---
Over the course of my second co-op, two of my friends and I built a personalized, build-your-own newsletter product for news (you can check it out here: [https://weeklymuse.co](https://weeklymuse.co)) . This was my first time executing an entire conception-to-launch lifecycle for a product and I learned an enormous amount. I wanted to document this journey, as I strongly believe that what my friends and I did could be a model for other students as an alternative to side projects.

# How it all started

The first seeds of the idea were planted way back in April 2020 after my first year ended. I knew that I wanted to pursue some sort of project during my first co-op term, but I wasn't thrilled with the prospect of making another small app and putting it up on GitHub. I wanted to build software that others would actually use since that is pretty much the essence of what it means to build software. Furthermore, there are interesting challenges with scaling up a project that I would never experience when building a side project just for myself.

Furthermore, many of my friends were into entrepreneurship. We had regular discussions about cool products, ideas, articles regarding execution and hot takes on the future of technology. This heavily influenced me to make a product that people would actually want to use.

Thinking through this more, I realized that there is a spectrum of projects that a student could do. On one side we have side projects, which are oriented around learning and building  cool stuff; on the other side, we have full entrepreneurial pursuits that are more focused on building useful products that solve a legitimate problem and have great user growth. I decided to build something in the middle, something that is rooted in user problems and has users but also incorporates elements of learning and not as strict and stressful as an entrepreneurial venture. In other words, I wanted to build a **side product**.

# Finding a Problem

Given that I wanted to create a product that would actually solve a real problem, I reflected on my own life on the problems that I face that I thought others also struggle with. The problem that I decided to tackle was news consumption.

When I was a kid, I spent many of my early weekend mornings reading newspapers with my parents. This was my primary source of news. Nowadays, most people gather their news from social media. Looking at this from a broader view, I realized that social media is probably not the best medium for communicating interesting news for a couple of reasons:

1. **Algorithms**: much of social media news consumption is driven by algorithms that choose the most sensational content. This often means that your news pattern is driven by everyone else's patterns! To me, news consumption should be personal and should not dictated by what others think is popular. For someone that wants to be an independent thinker, social media is not something I enjoy at all.
2. **Niche content**: I love to read niche content relating to my interests (eg. news regarding specific countries, news about specific companies and industries) but this is pretty difficult to curate. You need to find these sources on your own time and vet them yourself. Furthermore, the reader needed to remind themselves to read these niche content on a regular basis. In other words, it can prove to be a hassle to keep up with niche content

I wanted to tackle this problem so that I could improve my news consumption. After talking with a few friends, I found that others also had the same problem, although the importance of this problem was pretty low to them. Since it was a side product and not a startup, I was OK with this feedback and decided to design and build the project!

After this problem analysis, I decided I wanted to create a build-your-own-newsletter product. Users could sign up and select a list of niche topics that they wanted to read about. The product would store these subscriptions and gather the most important news for each subscription and send a compiled newsletter every weekend.

# Designing and Building

I started the designs and planning process in November 2020. I first started off by prioritizing the set of features for MVP and making really basic flows and wireframes. Here are a couple of images of my process in the beginning:

![[IMG_869BDB797ED6-1.jpeg]]

![[IMG_DED260B27188-1.jpeg]]

With these designs, I moved into creating Figma high fidelity wireframes for all the wireframes. Here's a sample of my initial work:

![[Screen Shot 2021-05-09 at 12.01.20 PM.png]]

After I finalized my design, I set about planning the architecture of the app. The app itself was a pretty simple CRUD app design but the hard part was sending newsletters. I had no idea how to send email, let alone designing a nice one! I scoured across the web and found that AWS SES was a great way of sending emails. Together with an AWS Lambda function to collect news articles and build the newsletter and triggered on a weekly basis through events fired from AWS Eventbridge, we could send an email. Finding a solution for designing an email was a little more difficult as we needed to ensure that the newsletters looked good across multiple email platforms. Fortunately, the great folks at Mailjet made [MJML](https://mjml.io), an email design framework that did exactly what we needed!

Here's a brief diagram of our architecture:

![[IMG_7C79D1234738-1.jpeg]]

I will briefly explain certain decisions that we made regarding our architecture:

* **AWS Lambda**: to host our backend server, we could either use an EC2 instance (think of this like a computer on the cloud that is usually always running) or use AWS Lambda. AWS Lambda is a really interesting technology: it essentially creates functions for your backend endpoints, takes in requests and sends responses and autoscales. In other words, if you have a sudden flux of user activity, AWS Lambda would automatically spin up new functions to handle the extra load with extremely low latency. Given that it is also pretty much free for hobby projects, I decided to go with Lambda rather than worry about whether our EC2 instance could handle spikes in traffic.
* **API Gateway**: Think of the API gateway as a gateway into a community. It serves as a public address for the community but doesn't give away the addresses of the individual houses of the community for security and privacy reasons. We did the exact same thing with our Lambda functions. This is known as a **reverse proxy**. People often confuse reverse proxies with load balancers (distributes load across different servers while also masking server addresses). The difference is that reverse proxies are also useful if you have one server rather than multiple servers; you don't want to expose your server to the public as some malicious actor could overload your servers. AWS also enables us to set rate throttling to prevent too much load on our lambdas and spinning up too many instances
* **AWS SES**: cheap and easy to setup over other email providers (would recommend for others looking to develop email-based products)
* **MongoDB**: We could have gone with a relational setup on AWS RDS because we weren't worried too much about having to scale our database to handle lots of requests. However, MongoDB is way easier to work with as a dev and has in-built scaling capabilities, so we went with the NoSQL solution.

There are other parts of our application that I will not cover, like app and email analytics. Let me know if you would like me to write about that as well!

Now that I had an idea on the architecture and design, I joined forces with my two SE friends (Oustan Ding and Jonathan Cui) and we built our product over 4 months. Without their help and insight, this app would have taken much longer to complete, so huge thanks to them!

# Launching

To get user feedback as soon as possible, we created a private beta launch among our friends and gathered feedback over March 2021. However, we quickly realized a big problem: our friends aren't interested in news like we are. Thus, almost 90% of their feedback wasn't very useful to us. If I were to redo any part of our process, it would be this. No fault on our friends of course, but we should have been a little bit more picky with who we wanted to test our product to get the best feedback.

Regardless, we ran with the 10% of solid feedback and did several iteration cycles. By beginning of April, our team was wondering whether we wanted to make the app even cooler or just launch. After carefully weighing the pros and cons, we decided to launch and gather better user feedback to find out whether it is worth putting the energy into integrating cooler features.

On April 13, 2021, we opened up our app for everyone and launched it on [ProductHunt](https://www.producthunt.com/posts/muse-b0d3445e-a0b9-466f-a8ac-0cfeedd9fcaf), Reddit and HackerNews. Despite some hiccups caused by bugs on the platform, the launch went smoothly. By the end of the day, we had about 90 users. Over the next few weeks, our user base grew to over 120 users with 0 effort in marketing. Our setup now serves over 450 newsletters/month with very minimal maintenance needed. Overall, this was an incredible success for our team!

You can check out the product here: [https://weeklymuse.co](https://weeklymuse.co). Shoot me a message if you have suggestions or ideas on how we can improve!

# Takeaways

This was my first side product and suprisingly enjoyed the entire process of taking a product from the ground up without having to worry too much about sales/marketing like a full startup. This project taught me a huge amount about software architecture and email software because it integrated aspects of the side project philosophy. For people that are looking to create side projects, I would highly recommend trying out a side product instead. There's a crazy amount of satisfaction from seeing users using your product and enjoying it. Even from a more practical perspective of getting your next job, I would argue that side products are superior to side projects because you have actual users and had to solve problems you would never encounter in a small project.

I do concede though that side products are probably not the best way of learning something new as there can be stress related to it. Side projects are much more suitable for learning something completely new. Side products will probably never merit you the credit, admiration and money involved in a startup, but if you're fine dealing with a lack of external motivation, then side products might be for you!

If you are interested in building a product with me, shoot me a message!
