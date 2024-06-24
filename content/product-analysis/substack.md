---
description: "UPDATE: Substack published a reader portal! Another product prediction came to life.Published: August 2020"
title: "The Rise of Newsletters: Substack"
date: 2020-08-20
tags:
  - business
---
![[substack.png]]

I never heard about Substack before the coronavirus quarantine. It popped up on my radar in around April 2020 when Andrew Chen from a16z started talking about and wrote a memo on his investment in the company; since then, it has grown tremendously. Several people that I know are using it and I get a lot of my product management information through the newsletters published by Substack. I thought it would be interesting to do an analysis on this newsletter service and determine how it can improve to better accomadate its growing audience.

# What is Substack?

It all started with an essay. Two of the three founders, Hamish McKenzie and Chris Best, were employees of Kik, a large Canadian messaging company. After they left the company, Chris created an essay on why media has degenerated into the mess that we are in now, where media are more often rewarded by sensationalism rather than the truth. When looking into ways of solving this problem, they came across the reader-to-author direct-subscription business model.

What exactly is this business model? Many readers, including myself, love to get high-quality opinions from industry experts. You can get these short-form opinions on Twitter or you can get long-form (in my opinion, better quality) opinions from newsletters. Many of these authors, knowing that their opinions are worth a lot for information-hungry readers, will start to ask for payment for these subscriptions. Take the example of Ben Thompson's Stratechery, an excellent blog on tech business strategy. Thompson has a newsletter service where you need to pay to get more frequent newsletters or premium content.

In fact, it was Thompson's newsletter that inspired McKenzie and Best to start Substack along with another founder, Jairaj Sethi. They believed that a service that empowers authors to create and easily publish newsletters while easily building an audience is the perfect way to bring Thompson's strategy to other authors. As a reader, I can go to Substack and browse through past newsletters of an author; if I like it, I can sign up. Authors also have the choice to create paywalls where you will need to pay to read premium content.

I think this is an incredible idea. We have seen a trend in digital media where content is getting shorter but also more personalized. Reading newspapers or watching BBC News is no longer popular: rather, individuals get their news from bite-sized content from Twitter that is hyperfocused on the individual's interest. Substack has inadvertently captured this trend by distributing incisive opinions from journalists to interested users while also championing the author's right to profit from their work. Substack is the vanguard of this new author-to-consumer marketplace.

# Why is Substack superior to Medium?

When I first heard of Substack and explored it on my own, I was reminded of Medium, another blogging platform that has taken the tech world by storm. However, after reading posts online and doing some research on Substack's platform myself, I would cautiously opine that Substack is superior to Medium.

There are three reasons why:

1. **The control of the author**: Substack is extremely clear - the service is meant for authors, not readers. This fundamental distinction is why Medium flopped while Substack prospers and here's why. In the market, it is the author that has the levarage because they are the content creators. In other words, they hold access to the most valuable good in the media space. Allowing authors to control their subscriptions, which articles are sent out, how often they are sent out, etc. gives them more freedom to create what they want. On the other hand, Medium's rigid guidelines, control of writers and a focus on readers has created a situation where writers have to stoop to clickbait and other vile tactics to take full advantage of Medium's platform. What Medium got wrong was that readers will always be there; writers will not. Thus, it make more sense to focus on the writer's experience rather than the reader's as they are the limited good.
2. **Content distribution and superiority:** The philosophy behind subscriptions is completely different between the two services. On Medium, you subscribe to the platform. On Substack, you subscribe to the author. Why is this better? Authors who have great content get rewarded more on Substack because their distribution pipeline is a function of quality of writing. Meanwhile, Medium's algorithms pick clickbait content and harm great writers again. As a publisher on Substack, you are putting your own reputation on the line, which leads to better content.
3. **Personalization**: It's funny how the service with no recommendation algorithms is ironically the one that offers more choice for personalization. By now, I trash almost every single one of Medium's Daily Digests because the content is simply not what I like and is often in poor quality. Meanwhile, on Substack, I have the option to subscribe to authors that I personally enjoy reading. With no penalization on the Medium recommedation, author's are free to write what they want, which hopefully will stick to an interested reader.

# Product Recommendations

As always, I would like to take a stab at ways of improving Substack from both a user experience perspective and from a business stand point.

## User Experience

Let's first understand the user groups. There are two groups of readers: authors and readers.  Among the authors, we have the following reader groups:

1. The Casual: an individual who as an interesting perpective on a certain topic with a small following. Writing to have a small passive income stream but not their main project in life.
2. The Expert: this is an individual like Ben Thompson or Benedict Evans who spends most of their time creating incisive analysis on a particular topic.
3. The Journalist: Journalism is this individual's professional career. They write columns in newspapers and magazines and are steeped in the art of writing.

Let's try to segment the reader groups further. We have the following:

1. Deep-diver Donald: Donald wants to learn as much as possible about one particular subject and read as much as possible from the leading voices in the field.
2. Broad-minded Belle: Belle wants to learn about different topics from authors she thinks are interesting. She has no particular affiliation to a subject and just wants to learn more.

Substack has room to improve for both authors and readers, but I believe that Substack should focus on readers a little more without sacrificing content quality. Specifically, the persona of deep-diver Donald is something I want to tackle.

Thinking more deeply about this problem, I have come up with the following pain points:

* Hard to find authors who are deeply specialized in a particular field: if I was interested in entreprenuership, I need to know who are the leaders in the field, who publishes newsletters, and who publishes on Substack. This 'newsletter funnel' is hard to navigate as a reader who just wants quality content.
* Inbox overflow: so many people to follow leads to inbox overflow, which leads to fewer newsletters read and writer effort wasted.
* Community: As a reader, I want to talk to others who are reading the newsletter who might have interesting commentary on what the author wrote.

I am going to prioritize the first pain point for the following reasons:

* This has a two-sided impact: it allows readers to find relevant authors while also brining authors a new source of readers
* Inbox overflow is a very complex problem that would most likely hurt the distribution of newsletters
* Community is somewhat addressed as people are able to find authors that write about similar things. However, this isn't a must-have and mainly helps the readers.

Some ideas that I thought of to address the first pain point:

1. Create a 'similar authors' tab at the end of a newsletter: this would encourage readers to easily explore new authors. To prevent overwhelming the reader, maybe the profile pictures of 3 individuals with similar writing interests could be displayed at the end of the newsletter
2. Create a reader's portal: create a portal that allows the reader to explore the writers on Substack and the different topics avaliable to read about
3. Encourage authors to backlink to other newsletters: Substack could create a small feature to quote other Substack authors in an extraordinarily easy fashion. I am imagining a small embedding, similar to how tweets are embedded in different media. The author who was quoted could use this as an additional tracking point. This would address the pain point as it is likely that newletter that is quoting and the newsletter that was quoted are similar to each other and talk about the same topic.

I would prioritize the similar authors feature, then newsletter embedding and finally the reader portal. The issue with the portal is that it requires a lot of engineering effort as you need to envision the UX of a group of people that is not the primary focus of the Substack platform. The first feature is simple to implement and can easily be tracked (metrics to look for would include average percentage of traffic from similar authors for all newsletters or the conversion metrics from similar authors to subscription). 

# Business Recommendations

Substack was built at the right time: newsletters are making a huge resurgence. There are two important questions that the company must address:

1. How do we gain a 10-100x benefit of this rising trend over competitors?
2. How do we prevent competitors from sharing this benefit?

Substack has a lot of advantages as a first-mover so it should spend more of its time seeking bold, creative moves that can continue to revolutionize this field. There are three aspects that Substack should focus on that I believe will address both of the above questions (inspired from my reading on [7 Powers](https://aaronabraham311.gitbook.io/aaron-s-thoughts/books/7-powers-foundation-of-business-strategy#switching-costs)):

1. **Make the author user experience as smooth as possible**: Other services are focusing on the experience of the reader, but this unique user focus for Substack is a great strategy. The reason why is because switching costs for readers are hard to build; after all, content can be found in several channels. Switching costs are much easier to build for writers as they can build a platform that no-one else can compete with.
2. **Foster a community**: Notion did an excellent job with this, as it has nourished a flourishing Reddit, Twitter and Facebook groups. Substack should do the same to tap into the network effect and grow the company as a author-focused startup.
3. **Use scale economies**: I am not an expert in the financial position of Substack, but I believe that they can grow their authorship to the point where they can benefit from scale economies. This would allow the company to reduce subscription prices, which in turn will boost reader numbers. Building a massive network should be a big priority.
4. **Use star power**: Having famous journalists or authors (imagine the boost Substack would get if Malcolm Gladwell published newsletters through the platform!) would create a massive first-move advantage. If Substack can even get the authors to sign non-compete contracts, it could create an unimaginable advantage that other competitors couldn't begin to beat.

# Conclusion

I hope the above article was somewhat interesting and a peek into why Substack has taken the tech world by storm. If you have any comments/suggestions, please let me know!

## Credits
https://thegeyser.substack.com/p/interview-a-co-founder-of-substack
https://a16z.com/2019/07/16/substack/
https://digiday.com/media/how-substack-has-spawned-a-new-class-of-newsletter-entrepreneurs/
https://inspirefirst.com/the-benefits-of-publishing-on-substack/
https://www.indiehackers.com/post/why-do-people-use-substack-medium-e406ce021b
