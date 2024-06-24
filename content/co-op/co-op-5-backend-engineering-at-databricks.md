---
title: "Co-op #5: Backend Engineering at Databricks"
date: 2023-05-04
tags:
  - career
  - technical
---

![[image (38).png]]

In this post, I wanted to talk about my experience interning as a software engineer at Databricks!

# My journey into Databricks

After my Twitch co-op last summer, I realized a few things:

1. I really like working with large-scale backend systems since there's a large amount of impact available for people to create
2. I want to work in a hard-working culture that is laser-focused on creating a useful product for the world and iterates quickly
3. My next 2 co-ops should be focused on companies that I would join for full-time, as I want to get return offers
4. SF is a great place and I would love to return back

Given all of these factors, I began compiling a list of companies that I wanted to work for by the end of the June 2022 and started applying to companies. Databricks has been on my radar for a long time since I have a few friends that had worked there in the past and had a great opinion about the future prospects of the company. Furthermore, the projects that interns had worked on in the past sounded far more interesting than many projects that I had heard from other company internship blogs (examples: [2021](https://www.databricks.com/blog/2021/11/08/summer-2021-databricks-internship-their-work-and-their-impact.html), [2020](https://www.databricks.com/blog/2020/05/04/intern-tips-for-a-virtual-databricks-internship.html), [2017](https://www.databricks.com/blog/2017/09/05/summer-personal-professional-growth-databricks.html)). Lastly, Databricks is quite active the space of data and AI, which is becoming even more important with the recent hype around LLM and AGI.

After I applied with a friend's referral in August 2022 (tip: applying with referrals has a much higher success rate than cold-applying), I moved on to a Codesignal a few days later. This led to 2 technical interviews and 1 hiring manager interview, after which I was finally selected.

Compared to other interviews that I had done for internships, I would say that Databricks has a higher bar and slightly harder questions. Databricks is well known for their high hiring bar for full time software engineers, and this does trickle down a bit for interns. Be well prepared and make sure your fundamentals are solid!

I had a few options on my table by October 2022 for my winter internship. I chose to go with Databricks for a few reasons:

1. It's a **growing company**, which will naturally create interesting engineering challenges. Furthermore, a growing company offers a bigger financial upside later down the road
2. **Calibre of Databricks employees**: During my interviews, I got to talk to a few engineers. The problems that they were solving seemed very complex, and yet they were able to explain it to a newbie like me very easily. I was left impressed at the level of intelligence of my interviewers. After digging more into the company, I realized that Databricks is quite a complex product; intelligence and creativity is required in order to solve the problems that Databricks is solving at scale. I knew that being in that environment would force me to grow
3. **Return offer**: Databricks seemed like a great place to return to work full-time compared to some of the other companies that I had offers from.

After a few months from when I accepted the Databricks offer, I went through the team matching process. This was just a form with the major engineering organizations with Databricks, but they also offered a place to comment on specific teams I wanted to join. Knowing that getting a return offer is dependent on having a supportive team and the return offer may likely be for the team I interned for, I had to make some careful decisions. Some factors that I looked into were:

1. Importance of teams to the company objectives
2. Team growth (both in terms of scope and people)
3. Oncall load: I didn't want to be placed on a team with a heavy oncall load as that would have hindered my mentor and may not be a team I would have wanted to return to

The above factors can be figured out by either talking to people that you already know at the company or reading company blog posts (tip: blog posts are an excellent window into the company!!). The team selection decision actually came down to my work at Wish. At Wish, I spent some time working with [Amundsen](https://www.amundsen.io/). I found out that the person who created Amundsen is now working at Databricks on a similar product called Unity Catalog. I wanted to work on a similar product because I knew how cool Amundsen was, so I commented that I want to join the Unity Catalog team. My perception of Unity Catalog before I joined was quite different from the reality of the product, but it turned out to be a good decision nonetheless.

# Unity Catalog

Unity Catalog is an incredibly important product for Databricks. To put this technology in context, let's go back to databases.

One aspect of databases that many people forget is that is composed of both data and metadata. Metadata describes data and includes information such as the location of data, access permissions and more. The place where we store this metadata is called the metastore. The metastore can be made available to any client so that they can get information about the underlying database.

One of the most common types of metastores is Hive Metastore (which is actually completely separate from the Hive database). Here's a high-level diagram of the metastore:

![[image (13).png | Taken from "Why We Need Hive Metastore" (JetBrains) ]]

The metastore DB will contain all the information related to the data that the database (not to be confused with the metastore DB) is storing. The Thrift server is a server that uses the Thrift communication protocol. Clients such as databases (eg. Hive, PrestoDB, Trino) can communicate with the Thrift server to get metastore data for various purposes (eg. check access control, query planning). This [article](https://blog.jetbrains.com/big-data-tools/2022/07/01/why-we-need-hive-metastore/) by JetBrains underscores the purpose of having a metastore.

Databricks created their own metastore called Unity Catalog (UC), which can be thought of as a managed Hive Metastore but with more features. By controlling the metadata of customers, Databricks can do a lot of cool things, including:

* **Centralized data governance**: If all metadata is controlled by Databricks, it's easy for Databricks to determine if someone should access a particular entity (eg. table, catalog, model, etc.) since all access must use the metastore to get information. Data governance is a very popular ask from enterprises.
* **Centralized search and lineage**: Since all the metadata is in UC, Databricks can track how data is created. This is useful for data scientists who want to know how certain tables were created and by which pipelines.
* **Query performance**: Since Databricks also has its own proprietary query engine, Databricks can figure out smart ways to use the metadata in UC to optimize queries.

All in all, UC is a very important product for Databricks and is a foundation to the company strategy.

### My work at Databricks

Unfortunately, this is the first internship where most of the work that I did cannot be shared with the public since it has not been released for general availability. For the sake of not breaking my NDA, I won't go into much details. My project was generally about surfacing usage data to customers via UC.

Like my past internship experience at Twitch, the first few weeks were dedicated to learning the codebase and getting familiar with Scala (Databricks uses this language for a large part of its codebase) via some starter tasks. Then, I onboarded onto my specific project and started working on a design doc. This took about 2-3 weeks since my project was complex and had a lot of moving parts. The design was approved after a large team meeting and discussions with senior engineers. This left me a month and half to build out my project and onboard a specific use-case to my infrastructure.

Overall, my project was really fun and well-scoped. I had to work with large parts of the Databricks' codebases and had to really understand some distributed system concepts, such as cache invalidation logic, tradeoffs of routing RPCs to different regions and much more. Furthermore, I had the pleasure of owning the entire project end-to-end, from design to deployment. This helped me understand what it is like being a full-time engineer at Databricks.

Compared to my previous internships, there were a few differences with the Databricks internship:

1. **Transparency:** The internal culture at Databricks values transparency very highly. Our CEO and CFO would regularly share financial updates, teams would send very honest feedback to each other regarding different Databricks' products and more. I am quite grateful to have been part of such a culture, as it has helped me make a better decision on whether I want to return or not
2. **Complexity**: Databricks is probably the most technically complex product that I have worked on so far. I had to learn a lot of different skills, like learning how to debug distributed nodes, how to work with cross-cloud data, cache invalidation logic in a distributed environment and more. This forced me to mature as an engineer and ask dumb questions throughout my entire internship. I don't have any regrets over this, since I learned a bunch
3. **Meeting people outside of my core team**: I had plenty of opportunities at Databricks to mingle with people outside of the UC team. During this winter, I was lucky to be included in our company kickoff in Las Vegas, where I met a ton of people from all backgrounds at Databricks. I also had 2 offsites with my team where I got to meet folks that worked closely with UC and met many people during our company happy hours. This was a lot of fun and I am hoping to prioritize this aspect in my future co-ops/jobs. Knowing people outside of your team can help you escape your team bubble and also get different perspectives on the company. Plus, it's super fun to make new friends!

As always, I had a ton of fun with the other interns in SF at Databricks. This internship is a close contender with Twitch as the "most fun internship" that I have had so far.

![[IMG_5004.jpg|Exploring Las Vegas during our company kickoff]]
# Life outside Databricks

Since I have already visited and lived in SF for a while, I didn't do as much exploring this time as I did last summer. However, a lot more of my close friends were in town, so we did a couple of trips. Some notable ones included:

* Drive down to Big Sur: For anyone who loves to drive, this is a really awesome experience. Many scenic views and roads are in great condition!
* Land's End for sunset: This is a very popular sunset spot in SF. Would recommend as it is a great vibe, especially if the weather is really nice
* Mount Tamalpais hike: This mountain north of SF probably has the best views of the Bay Area. I would especially recommend during the summer as you can get great views with the fog rolling in from the Pacific Ocean

One of the highlights this time was working out at Equinox, a very high-end gym in SF. Fortunately, Databricks has a very generous fitness benefit, so I paid less than the cost of going to a YMCA in order to access Equinox. Equinox is definitely an experience; if you are in SF and have the money, I would recommend working out there and ending it with their amazing eucalyptus towels.

I lived in North Beach this time compared to Russian Hill last summer. North Beach is definitely livelier and has better food than Russian Hill, but it is not as safe. I still haven't made a decision on whether I would want to live in SF full-time; I will probably evaluate that after I have lived in New York. Here's a couple pictures of some of the adventures that I went on:

![[IMG_5130.jpg|Bixby Bridge in Big Sur]]

![[IMG_5283 (2).jpg | View of North Bay + San Francisco on Mount Tam]]
# Reflections and Lessons

I am really going to cherish my time interning at Databricks. This internship really helped me evolve as an engineer and taught me so much on how to work with complex technical products. As I look back on the internship, these were some of the lessons I learned:

* **Measure twice, cut once**: This mantra was drilled in me as a kid when I was doing construction and robotics classes during middle school, but the same also applies to software engineering. Especially when working with large codebases, it's important to understand the scope of changes you need to make before you actually go about making a change. Reducing the blast radius of your change will help you make more focused and precise edits rather than completely upending the existing code structure.
* **Self management**: This is one of the most important lessons that I learned at Twitch that I carried on in Databricks. As an intern, you don't want to be too much of a burden to your mentor; you have to learn how to manage your own work and how to take intiative for your project. It's also important to lay out documentation on what you have been doing and the results so far, as this will factor into your return offer. Concretely, I did the following, which helped my manager and mentor a lot when deciding on return offers:
  * I made a daily log that described what I finished yesterday, what I am doing today, and blockers. I would send this log to my mentor so that they can be updated on my progress
  * I made a doc that described all my tickets and associated PRs that I shipped. I would constantly update this
  * I made a doc with all the documentation and design docs that I wrote
* **Notetaking**: This is something that I learned too late in my internship, but it pays dividends to ask dumb questions and make notes about it. There were some relatively new teammates when I joined who had only spent 4 months on UC; the level of questions and understanding of the product was unparalleled. Granted they were senior engineers, but it still impressed me how they onboarded so quickly. One of these engineers had a note-taking system which he used whenever he got new information. In our line of work, there is so much that we need to know when working with existing code and services; having a  good mental model of the product you are working on will pay off. I thought taking notes was an excellent way of developing this model. I will probably take this on to my next co-op
* **Release engineering**: At Twitch, the process of releasing a code change was pretty easy since we had a very strong CI/CD suite leveraged off years of Amazon's experience delivering software. Databricks doesn't have something as robust as Amazon's delivery system, so a large part of releasing software is manual. I was able to watch some of these releases and see various issues crop up (eg. rollbacks, test regressions) and how to deal with them, which was somewhat neat
* **Testing**: I would wager that I wrote 2x - 3x more test code than feature code this co-op. It gave me a newfound appreciation for testing, as I realized how much more secure code is when tests are passing and automated. I saw numerous instances during this internship what happens if bad tests are written and buggy code is made into production. In my previous internships, testing was not a very important aspect of my experiences, but Databricks cannot afford buggy code since it impacts real customers with millions of cumulative users. Learning about test pyramids and flaky tests was invaluable.

Overall, this internship has been enlightening and really fun. For any interns out there, I would highly recommend Databricks if you want to join a fast-growing company that will push your engineering knowledge.
