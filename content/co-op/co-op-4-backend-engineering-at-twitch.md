---
title: "Co-op #4: Backend Engineering at Twitch"
date: 2022-08-31
tags:
  - career
  - technical
---
![[03-glitch.jpg]]

In this post, I want to discuss my experience doing an in-person co-op in San Francisco during the summer of 2022 at Twitch!

# My journey into Twitch

For Software Engineering and CS students, the most important internships are ones you do in junior and senior year for 2 main reasons:

1. **Return offers:** as you become more senior, new grad offers start to be a part of your decision making processes. Ideally, you want to be a company that would fit you and compensates you well. These last few internships are where you are given return offers for new grad as you near graduation, so the companies you choose to intern at in your last few internships are quite important.
2. **More options**: some companies only hire interns in their junior or senior years. For UWaterloo students, options for external co-ops significantly open up after your 2B term. Why is optionality good for co-op/internships? You can explore areas that might fit you better and work on different aspects of software engineering. Also note that there are far more options for summer internships than off-season internships. Summer internships are really important!

I also had a couple of personal goals that I wanted to tackle in my next internship. Specifically:

1. **Working with large-scale distributed systems**: I was first exposed to distributed systems at Wish (can read more [here](co-op-2-data-engineering-at-wish.md)) and became really interested in it. Distributed systems are the foundation for many modern companies who deal with millions of users every day. I wanted to learn more about this field in my next co-op. This necessarily meant that I was looking for medium to large companies as they are really the only places where you can exercise this skill.
2. **Develop my engineering leadership skills**: I initially got into product management because I wanted to develop my leadership skills. I didn't understand that engineers can also be leaders and owners in certain companies. After talking with a few friends, I realized that I never fully explored software engineering roles that exercised leadership skills, so I tried to find internships at companies where that was a requirement for engineers.
3. **Impact**: any kind of work that I do must have a measurable impact on end users or engineering systems

Given all of this, I knew that I needed to work hard in order to secure a solid internship for my 4th co-op, which could lead to more opportunities for my 5th and 6th co-ops. I had started recruiting during my 2B term around July 2021 for 2022 internships. It seems really early to recruit almost a year in advance but it is **extremely important that you start early!** Often, being quicker in applying matters more than having the perfect resume and experiences.

Twitch applications came out in late August 2021. Although I don't really game or use Twitch, I knew that Twitch could satisfy most of my goals. I have always had a deep respect for Twitch engineering, especially after [reading about some of their engineering challenges](https://blog.twitch.tv/en/en/tags/engineering/?utm\_referrer=https://www.google.com) when solving for real-time video streaming (meta tip: read company engineering blogs to understand the problems engineers regularly face).

I was quickly moved into a Hackerrank online assessment and a subsequent onsite with 2 coding interviews. Compared to other interview processes, Twitch's is signicantly easier in that they don't test random Leetcode concepts. Engineers at Twitch try to incorporate algorithmic concepts with real-life situations in their questions, which made solving problems far more enjoyable. Communication, clean code and debugging seem to be far more important than getting the right answer.

Eventually, I was given the offer for Twitch for the Monetization organization in November 2021. I had a few different offers on the table and was in the process for another large company, but decided to move forward with Twitch given that it met most of my goals (meta tip: know what you're looking for in an internship before you begin recruiting). In February 2022, I was then entered into the team matching process with all open teams in the Monetization organization. I was placed with the Ad Controls and Delivery team.

# Ads at Twitch

At a high level, my team is responsible for delivering an ad successfully to a viewer of Twitch. When I was matched to this team, I was ambivalent. At that time, ads didn't seem to be an interesting problem space. Boy, was I dead wrong!

As I onboarded onto my team, one thing was continually emphasized: ads are primarily meant to help creators earn money. The constant focus on creators took me by surprise, as I had thought the prime focus for ad systems were for enriching the company. At Twitch, that wasn't the priority. Constant thought was put into whether ads satisfied the creator.

I was also exposed to the complexity of the ad system at Twitch. Twitch operates in a service-oriented architecture; engineers are responsible for building and maintaining services that are responsible for doing a few tasks really well. These services work together to achieve the end objective of delivering an ad to a viewer. Not only was there a lot of underlying complexity given the numerous services that my team owned, but these services had to deal with a huge amount of traffic. Availability and latency were important considerations in service architectures, especially considering the revenue-generating nature of my team.

# My work at Twitch

While I was learning about the ad delivery services, I was given a choice of tackling 3 problems that my team faced. I decided to move forward with one of the most costly problems plaguing ad services.

Ad traffic is usually cyclical. During the day, more people are watching Twitch so we naturally get more ad requests compared to night. However, we sometimes have huge traffic spikes when a big streamer who has 250k viewers of more decides to run an ad. When such a streamer runs an ad, that leads to a huge load of requests pummelling our ad servers at once without any sort of prior notice. This presents a huge scaling challenge, as we want to make sure our services can handle all of these requests while also ensuring that we don't scale up when we don't need to serve all of those ads.

Most teams would rely on an autoscaler, which can look at default service metrics such as CPU and memory utilization and scale up when these metrics start to spike. For our use case, that would have been too slow and we wouldn't be able to serve ad requests in time, which would mean we would be losing out on money. Another solution that has been developed is predictive scaling, which uses ML to determine when services should scale up (Netflix pioneered this with [Scryer](https://netflixtechblog.com/scryer-netflixs-predictive-auto-scaling-engine-a3f8fc922270)), but this fails with unexpected traffic spikes that Twitch often has to deal with.

I decided to tackle problem by making use of a very simple observation: people watch streams before they watch ads. This means that any ad traffic spike could be predicted if we know about viewership spikes across all Twitch channels. This real-time information could then be used to scale up our ad services within a few minutes.

I started designing my pre-emptive autoscaler service based off this observation with absolutely no idea on how to do real-time data processing. After reading a lot of documents and code, I converged on my final design that leveraged the following technologies:

* **Apache Flink**: an open source, distributed real-time data processing framework. Several companies are using Flink for real-time data processing given its excellent architecture and performance compared to micro-batch processing that frameworks like Apache Spark can provide. Language: Java
* **AWS Lambda**: an event-driven compute service. Language: Go
* **AWS Kinesis Data Streams**: very similar to Apache Kafka where real-time events are stored in streams that can be processed
* **AWS CloudWatch**: provides real-time monitoring and metrics for services
* **AWS Application Auto Scaler**: provides auto scaling capabilities with APIs to customize scaling behaviour
* **AWS CloudFormation:** engineers leverage CloudFormation to set up infrastructure by just writing infra configurations in a YAML-like format. Spinning up a Redis cache is easy as writing a few lines of code. By keeping your infrastructure in a file and in version control, it becomes easier for engineers to standardize and monitor infrastructure changes
* **AWS CDK**: basically CloudFormation but in lovely TypeScript rather than YAML

With my design in place, I began implementing my service. I also conducted load tests against our  ad services to understand the limits of scaling our services. When I finished implementation, I began a slow rollout into one of our most critical ad services. We noticed the service beautifully scaling up and down in line with traffic spikes, successfully handling ad requests while also scaling down when not needed. My service will be integrated into other services at Twitch that need pre-emptive scaling.

There were a few aspects that made this a little different than my previous work experiences:

1. **Ownership**: I was responsible for designing and implementing the entire service. While my mentor gave a lot of helpful guidance, it was up to me to drive this project. This was partially because I asked for as much independence as possible in order to exercise my technical leadership muscles. Twitch tries to give as much latitude to their interns as they can as this often leads to faster engineering growth as you have the freedom to make mistakes.
2. **Operational excellence**: in my previous internships, I didn't get the chance to see what happens after a service is deployed. I was also unaware of incident management and how engineers incorporate observational capabilities into services (such as metrics and alarms when things are going wrong). I was taught how to make my service observable and got to sit in on operational incidents for my team. This was extremely enlightening on how services should not only be constructed to meet the end goal for the user, but also should be constructed to be easily observable and debuggable.
3. **System design**: I had a ton of fun learning about real-time processing and the best system design practices for these systems. My team also invited me to a few design reviews where I got to learn how other teams design their services to meet various constraints when dealing with high scale.
4. **Writing**: While I still didn't have to write as much as I did during my PM internship, I still had a to write a lot of docs on my design, various spikes and testing plans. Amazon has a heavy writing culture and this has permeated Twitch. Even rollouts of services require detailed plans on how to roll out traffic and how to roll it back if things go wrong. I really enjoyed the technical writing!

By no means was my experience exclusive to my team. Interns on other teams and organizations were able to make similar impact and had similar levels of ownership. Twitch really does care about the intern experience and tries to make them feel like full-engineers.

However, my team at Twitch was not all work. I had a blast with the other interns as we did various intern events (eg. golfing, watching Top Gun, messing around in the arcade) and had a great time during team offsites. Interning at Twitch was really fun!

![[IMG_3525.jpg|Our front office]]

![[IMG_4358.jpg|Our absolutely goated Twitch food! Twitch kitchen staff made delicious breakfast and lunch every day!]]
# Life outside of Twitch

I was a little nervous as I started making my move-out plans before the internship. This was my first time living by myself in another country and it forced me to grow up in many ways. Fortunately, there have been many people that have been in the same spot as myself and some of them have written up guides on how to make a successful move to the United States. I followed [this guide](https://irenexychen.com/blog/2021/08/us-intern-guide-covid) from an upper-year SE student which got me through most of the bureacracy involved with moving. The major moving issue was housing, as Twitch did not provide corporate housing during my internship. Finding housing was a little tricky, but following the linked guide helped a bunch!

This was possibly the most fun I've had in a single summer. I decided to opt out of my extracurricular responsibilities with clubs in order to make the most of my time in San Francisco. With friends from Twitch and elsewhere, I was exploring SF and surrounding almost every week. Somethings we got up to:

* Visiting Yosemite during Memorial Day weekend: I went with a bunch of Waterloo and Twitch friends and thoroughly enjoyed myself. Yosemite is a lot like Banff!
* Visiting Point Reyes: highly recommend! Absolutely beautiful views of the Pacific Ocean and very picturesque
* Visiting LA during Juneteenth weekend: had a lot of adventures here, like attempting to climb Mount Hollywood in pitch darkness (wouldn't recommend)
* Visiting NYC during July 4th break: Twitch gave all employees, including interns, a whole week off during this national holiday. I went to NYC and met up with a bunch of friends and explored the city
* Exploring various SF neighborhoods, like Mission (which has some real good food)

I had an absolute blast in SF! I would highly recommend interning in the city at least once to experience the culture. I am not 100% sure if I would move here for full-time given its various problems (eg. homelessness, housing affordability, high cost of living, tech monoculture) but it's definitely worth exploring during an internship. Here a couple of pictures representing a small sample of my adventures:
![[IMG_3557.jpg]]

![[IMG_4189.jpg]]

# Reflections and Lessons

Twitch has been one of my favourite internships so far. The culture at Twitch is amazing and I have learned so much from my time at the company. I would highly recommend any intern to   apply to Twitch for an internship; I can guarantee that it will be a great time for you!

Here were a couple of lessons that I took away from my internship:

1. **Writing is a superpower**: Amazon has a heavy writing culture that has permeated Twitch. I didn't really understand why engineers have to write so much, but after writing numerous docs and spikes and watching senior engineers write root cause analyses after incidents, I realized that writing is not about output. It's a forcing function. Clear writing leads to clear thinking, which can be easily distilled and distributed to other teams. I learned a lot of writing strategies to enable such writing and I am hoping to take this into future internships.
2. **Aim to shorten feedback loops**: Engineering work is filled with feedback loops, such as code reviews, doc reviews, performance reviews, etc. These loops are usually the main reasons why work could slow down. I had a small issue where my design review took a long time to be finalized since I didn't share it with my team often enough and feedback was only asked once the design was finalized. Utilizing shorter feedback loops and making quick, incremental changes can significantly improve velocity. I used this strategy when writing spikes for more ambiguous parts of my project, which helped me derisk early and get feedback before I began tackling problems.
3. **The importance of system observability**: An unobservable system is a huge operational risk for engineering; if something goes wrong and there's no way to find out why it went wrong, it could break a lot of things in your system. Learning about efficient logging, metrics and setting up alarms made me realize how important it is to enable your system to be at least semi-transparent to enable engineers to fix things when the system goes south.
4. **Train yourself to be a faster learner**: In this internship, I was surprised by how quickly I was able to pick up new technologies. Much of this is because I have worked with similar technology before, so I could use a lot of pre-existing mental models. However, I have also found methods to help me learn tech much faster that is more customized to my ways of thinking. Fast learning is a key trait for software engineers due to our fast-evolving field of work; training yourself to learn fast is incredibly important! Constant exposure to new technical concepts and having the ability to prototype and test quickly are very important skills in becoming a faster learner and I would definitely lean into that!
5. **Expand engineering scope**: Will Lawrence does a great job of explaining why increasing product scope is important for PM career growth in [his newsletter](https://productlife.to/p/-great-pms-create-scope) and I think the same lessons can be applied for engineering. For engineers, it is important to always be performing at the next level, which often means that we shouldn't be constrained by the scope that we are given. Instead, we should constantly find ways to apply our skills in new areas and we should take initiative rather than waiting for someone to give us extra responsibilities. Some of the times that I felt most challenged was when I performed tasks outside of my project, such as upgrading a major piece of CDK code to a new standard for my team and others who relied on it. Taking such initiatives and actively sniffing out extra scope forces us to grow as leaders and engineers.
6. **Be concious of imposter syndrome**: I found myself in a few situations where I felt that I was way above my level of competence. For example, I once had ended up eating breakfast with a  principal engineer who agreed to critique my load testing strategy. To me, I felt like I didn't really belong in these situations, but I had to conciously remind myself that there was a reason why I was there. Almost everyone in software engineering has moments of imposter syndrome since growth requires pushing comfort boundaries. I haven't come across a surefire way to prevent these feelings, but it's important to catch these feelings before it spirals into self-doubt.

There are far more technical lessons that I learned during this internship regarding structuring clean code and coordinating design reviews, but much of these lessons can actually be found in the book, _The Missing README_. Would highly encourage interns and new engineers to take a peak! The book gives a great description of what engineering life is like at big tech companies.

Overall, my internship at Twitch was nothing short of awesome! I would highly recommend it to others if they want a taste of what life is like at a fast-moving tech company.
