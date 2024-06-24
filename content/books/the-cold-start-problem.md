---
description: This book was gifted to me by my amazing Clearco manager and Director of Product, Walid Koleilat. Thanks, Walid!
title: The Cold Start Problem
date: 2022-05-05
tags:
  - business
---
# Network Effects

## What's a network effect anyway?
* Basic definition: a product which becomes more valuable as more people use it
    * Eg: Uber became more valuable as more drivers & riders used it, telephone is also a networked product
* The product's network is distinct from the actual product. Product is physical/software; network is made of people
* Most successful tech products make use of the network effect
* Network effects are made up of the network and the effect
    * The network is defined by the people and their creations. Companies don't own anything in this network; they just connect different people really well
    * The effect part is how the network makes more action more valuable
* It is now really difficult to launch a product, but network effects lends itself to virality (which plays well in the zero-sum attention era)
* Network effects act as a great defensive moat. It is easy to copy a product, but it is not easy to copy the network of a product

## A brief history
* Metcalfe's Law: the value of a network grows by the square of the number of users in the network
    * This is very simplistic and leaves out a lot about network quality, how to start a network, etc. This was the model of thinking in the 90s
* A better mental model is that of social animals
    * Below a certain threshold of users, the network is not very usable. Above the threshold, the network can grow
    * The network has a carrying capacity. You can do various things (eg. spam detection, bot deletion) to grow the carrying capacity of a network
    * At a certain point, if the network overextends, it can collapse spectacularly

## Cold start theory
* 5 primary stages in building a network:
    * The cold start problem: most new networks fail. You need to find a way to provide value immediately to users in the network
    * Tipping point: atomic network is established and provides value, which immediately makes new networks easier to create
    * Escape velocity: companies scale up to create sustain network growth, trying to improve its acquisition, engagement and monetization effects
    * Hitting the ceiling: negative forces in the network multiply and growth slows. This is usually solved and another growth spurt occurs, over and over again
    * The moat: networks are used as defense/offense against other companies

# The Cold Start Problem

## Tiny speck
* Your first priority should be to build a singular, small atomic network that is self-sustaining
* Eg: Slack built a networked product. First used IRC for internal comms when team was building Glitch. Then focused on IRC tool and seeded it within friends' companies, which was the atomic network

## Anti-network effects
* If the network is too small, people will leave. This leaves us with the classic chicken-and-egg problem
* If you plot network size on the x-axis and various metrics on the y-axis, you will see a kink in the network. That kink is your threshold that you need to pass
    * If that threshold is high, it will be hard but far more defensible if you can succeed
* You need to have density and interconnectedness in your first network. 10 people in the same team using Slack is far better than 10 people in 10 different teams

## The atomic network
* Networked products often start with small networks and gradually build up (eg. one campus, one company, one city)
* Eg: Bank of America pioneered credit card and started launch in Fresno by sending a few thousand people a free credit card and signing up small merchants
    * This expanded throughout California
* This small atomic network needs to have enough density and interconnectedness to overcome anti-network effects
* Usually networked products are extremely minimal, extremely focused on the atomic network and use unscalable techniques to grow
* You can use growth hacks to launch and build an atomic network
* Networked products usually target a niche, making them seem like a toy. This is an underestimation
* To start a network, you need to focus on the smallest network possible (eg. Uber focused on a very small radius around a particular train station at a particular time)
* If the atomic network doesn't require lots of people, it's easy to go viral and grow, but its not as defensible
* Building one atomic network makes the next one even easier

## The hard side
* The "hard side" of your network are the users who contribute the most value but are the hardest to retain
    * Eg: contributors on Wikipedia, content creators on YouTube, doc creators, app developers
    * Usually governed by power law
* You need to keep these users happy in order to generate network effects within your atomic network
* Eg: Only 0.02% of total viewers on Wikipedia consistently contribute 
* Networks have hard sides because there are parts of the network that require work. Contributors expect value as well and will try multiple resources before settling
* You need to understand the motivations of the hard side of users so you can cater to them right from the beginning

## Solve a hard problem
* Your first step in creating an atomic network is attracting the hard side. This requires satisfying a hard problem for this group of users
* Eg: Tinder solved the issue for attractive women by combining location-based dating, trust signals via Facebook and easy swiping to drastically reduce the work needed to do online dating
    * Previous iterations of dating software made it difficult for attractive women to select dates
* For most marketplace software, the supply side is usually the hard side
* In order to figure out the hard problem for the hard side, you need to understand which problems are they engaging with but has not been addressed well
    * Segment your underserved audience as much as you can and look at their side hustles and things they do in their free time

## The killer product
* Networked products are different because they facilitate relationships between users in a network, which is very different from traditional software
* These products also need to balance the needs between hard side users and easy side users
* The richness of a networked product comes from the quality of the network and the ability for network nodes to interact with each other, not the features of the product itself
    * Because of this, networked product are usually quite simple
* Usually products that are trying to build networks use a freemium model to reduce the barrier of building a network

## Magic moments
* A product that has solved the cold start problem can start to deliver on its core value prop
    * Eg: Clubhouse in its heyday had so many chat rooms that you could use spontaneously
* You can also try to quantify how often non-magical moments are happening, termed as "zeroes"
    * "Zeroes" are the worst possible experience on the software. Users who go through this often churn out. Keep a close watch on these metrics
* Magic moments require a great product and a great network

# The Tipping Point

## Tinder
* Once you have gotten the atomic network down, you need to start scaling and building new networks in order to reap network effects
* Tinder's initial strategy was to throw parties for popular, hyperconnected students on college campuses. The catch was that all partiers had to have Tinder
    * They scaled this approach by continuing to throw parties around campuses or other areas of dense social connections
* The tipping point is when you transition from creating atomic networks to tipping entire markets over to your software. Momentum is on your side

## Invite-only
* Invite mechanics are useful because a curated network will invite people similar to them, making a stronger network. It's like a copy-paste mechanism
* LinkedIn used this mechanism to make a curated network of professionals who would actually connect with others. This made sure people could be trusted and the network quality was high
* Another pro for this mechanism is that you can create a better onboarding experience because they were invited, and so there is already some trust
* Invites also create hype and can help teams build infrastructure for more people as the network grows
* To curate these high quality networks, use ratings, high-touch onboarding or collect more information during waitlist signups

## Come for the tool, stay for the network
* If you can provide good value for just 1 user but then is complemented with a great network, this can kickstart growth
* Instagram was initially hyped out for its great photo filtering experience, but it always had a network. Now, most pictures don't have filters and people stayed for the social network
* This strategy greatly eases the cold start problem because the threshold for utility is quite low
* Major clusters of tool + network combo:
    * Create + share
    * Organize + collaborate
    * System of record + keep up to date with others
    * Look up + contribute with others
* Transitioning a product from tool to network is tough! There must be clear, direct links between the network and the product

## Paying up for launch
* Many companies drive up cost in order to get their network into a tipping point, at which point money is not needed to provide momentum
* Eg: when coupons were just beginning, companies would give out free samples of their product, which incentivized grocers (the hard side) to stock up
    * This eventually led to regular customer traffic -> regular stocking at groceries
* Uber did this to get drivers in a new city: they guaranteed a base salary and used give/get referrals to incentivize people to join
* You should only use money for growth once you have a product and market figured out and know exactly how you want to scale your atomic networks
* Crypto did the same by incentivizing initial miners with large sums of Bitcoin and gradually tapering off rewards for miners
* Microsoft did the same by partnering up with IBM to sell its first OS. Even though there was a cost of doing so, it helped them establish a network
* Unprofitability in the short term may lead to dominance in the long term

## Flintstoning
* Flintstoning: incomplete product is made complete by having a Wizard-of-Oz functionality of humans running various functions
    * Once a network is formed, you then automate yourself out
* Usually, you try to imitate the hard side as you prop up your network. Reddit did this by having the founders post interesting articles
* Flintstoning can be combined with software to make it scalable
    * Eg: PayPal used bots on Ebay that would only pay through PayPal to force EBay to use PayPal
* Once the cold start problem is solved, stop flintstoning. It may hurt

## Always be hustlin'
* You need to bre creative when figuring out how to reach the tipping point

# Escape Velocity

## Dropbox
* When the cold start problem and the network tips over, your product will start to have runaway hockey-stick growth
    * This doesn't mean everything is great: you have to maintain high levels of growth and maintain network quality
* When Dropbox hit escape velocity, it focused on certain user segments (esp. high-value businesses) in order to maintain runway for big projects

## The trio of forces
* When a product hits escape velocity, you will most likely need to scale up your team
* The network effect is made up of:
    * Acquisition effect: the network makes it easier for new users to sign up. 
    * Engagement effect: dense networks allow for more stickiness and usage by users
    * Economic effect: network improves monetization
* These work in loops and will grow stronger as the network grows in strength, creating a positive feedback loop

## The engagement effect
* Cohort retention curves are extremely important, as they determine how sticky your product is
* Most products have a 60% retention after day 1, 30% after day 7 and 15% after day 30. Networked products sometimes beat these numbers because the product becomes more sticky
* Sometimes, product use cases will become more apparent with a larger network. The product should try to make these use cases clear
* To figure out how to nudge users to be more engaging, you need to segment based on levels of enagagement and figure out the different needs for users
* Once you have segmented users, you can run different A/B tests to see if the cohorts have different behaviour based on changes you made
    * Based off this, you can find characteristics that separate great users from mediocre users
* Networked products often have engagement loops, where actions make actions further down more likely and it creates a cycle
    * Eg: When a content creator posts on Instagram, they get likes & comments from followers, which gives social validation for the creator to post more
    * If you understand your product's engagement loop, try finding ways to improve each step of the loop
* The enagagement effect can often reactivate users if they see that their network is using the product

## The acquisition effect
* Networked products will often have viral growth which are baked into the product itself
    * Eg: PayPal & Dropbox products are only useful if you have people to send money/documents to
* How do you make acquisition easy? Figure out the funnel and optimize via A/B tests
* To measure this effect, we can use the viral factor: out of the users in a particular time period, how many referred others into the app?
* Retention usually helps a lot with acquisition
* A network can have a strong acquistion effect and a weak engagement effect
* Usually, networked products that have the acquisition effect have health
ier networks because there is interdependency between nodes in the network

## The economic effect
* Sometimes driven by data network effects, where the value & costs of customers are better understood as the network grows larger
    * Eg: credit bureaus expanded from local to international, which helped improve the ability for bureaus to determine if someone was trustworthy for credit
    * Bigger network -> more data -> more personalized
* Bigger networks often mean that any spend can be extended to far more users.
* You can structure premiums on your service such that it is more useful with more people, so bigger networks naturally go premium
* Networks provide big defense because the switching cost becomes high

# The Ceiling
## Twitch
* As product grows to scale, growth starts to slow, so product teams need to find new ways to create growth
    * Justin.tv focused in on gamers and streamer technology, which kicked off intense growth after stalling
    * Facebook used growth teams to grow after plateauing at 90M users
    * Many B2B startups go afer big enterprises during times of stagnation

## Rocketship growth
* Generally, rocketship companies will get $2M ARR -> triple -> triple -> double -> double -> double (getting to $144M)
    * This is based off the assumption that the company wants to get 1B valuation in 10 years (typical in VC-funded businesses)
    * This is quite hard to do for any company since the pace of growth needs to be roughly the same throughout all years
* When you hit a ceiling, it's imperative to find a way to reignite growth as it can dry up investment, engineers leave, etc. 
* Networked products are fare more likely to sustain rocketship growth

## Saturation
* Sometimes, your product will be able to serve everyone until there are very few left. Focus should shift on revenue generation and layering services
* Eg: Ebay started offering new ways of buying items (fixed prices rather than auctions) and kept layering new products -> revenue growth
* A network's growth can stop due to market saturation (almost everyone is on it) and network saturation (diminishing returns of new nodes in the network)
    * Can counteract by thinking about the set of adjacent users who are not as healthy as the core users of the product
* Can also have new formats for the same product offering (eg. Snap stories)
* Can launch in new geographies
    * Works well if geographies share users, but beware of different cultures and attitudes
* Acquisition is another strategy that companies can use to combat saturation

## The law of shitty clickthroughs
* Law: marketing channel performance degrades over time, which will impact growth trajectories
    * Why? Humans ignore ads after seeing it for so long
* This is a serious problem for networks because this will have huge impact on the bottom of the funnel and can even impact engagement
* Solution is to layer on new marketing channels all the time and focus on making the network healthy

## When the network revolts
* Networks have a backbone of power users who start to professionalize and eventually will push back against the product
* These network professionals are either home-grown or were professional before they entered
* There's no choice but to embrace these professionals, even through their protests

## Eternal September
* Usenet ws like an early version of Reddit. When more consumers got access to the Internet, they flooded Usenet with bad content which killed it
* Every network has netiquette, but if too many networks brought in at once, netiquette can break down since there's too many contexts
* You can build tools that enable people to create different contexts and avoid issues (eg. private stories, finstas, Slack warning about time zones)
* Can leverage the network to monitor good behaviour (eg. Reddit uses downvotes to know if something is bad)
* Centralized software usually outperforms here; decentralized software can't coordinate to fight off bad actors

## Overcrowding
* When a network becomes too crowded, it becomes much harder to use
* Eg: YouTube faced this issue and initially relied on manual curation; now it uses algorithms
* Another issue that happens when a network is overcrowded is that new node additions become much more difficult
* Networks naturally have lots of data, which means that developing good algorithms for curation is much easier

# The Moat

## Wimdu versus AirBnB
* Wimdu was a European clone of AirBnB and was much larger and had more employees. They failed because their supply was nowhere near as good as AirBnB
* AirBnB fought against Wimdu by quickly internationalizing their product and team
* This section is all about how networks compete

## Vicious cycle, virtuous cycle
* The cold start problem acts as an initial defense for networked products
* It is quite difficult to compete against a network as it keeps growing and steals supply from you. It's even more difficult when the network is integrated well
    * Uber is easier to tackle than AirBnB because Uber's networks are primarily city-based, while AirBnB are global
* Network competition leads to winner-takes-all, so it is a high-stakes competition
    * This is not necessarily a product competition, but more of a network dynamics competition (eg. which network grows faster and has better quality)
* Just because you have a network doesn't mean that you have a magical defense. It's all about which network is amplifying their acquisition, engagement and monetization effects better
* Network competition leads to vicious cycles for losing companies since the network quality degrades as people leave

## Cherry picking
* When networked products get large, it might not be able to serve all parts of the network equally well. Startups can notice dissatisfied groups and use them as their audience
* These upstarts can build a denser subnetwork than the larger network and people will switch over. Network quality & density >>> network size
* This is very painful for large networks because it is hard to regain networks & they need to solve the Cold Start Problem again, but this time with competition
* If you cherry pick to the point where the network you develop is dependent on a larger network, you run into dependency issues

## Big bang failures
* Big companies love to go all out when launching networked products with a big, wide launch. This often fails (eg. Google+)
    * It usually failes because the networks that develop are weak and shallow
* Big bang approaches for launch are usually not targeted and use broadcast channels, which leads to lots of users but weak interconnections
    * Harder to assess if network is growing well
* Larger companies try to target the biggest market possible, but smaller startups can go for niches and build far more resilient networks

## Competing over the hard side
* When networks compete, it's usually over the hard side
* A good strategy that many companies used is to attract hard side individuals from competitor's network to theirs
    * Uber used incentives and bonuses to attract drivers from other apps to theirs
* Competitive intelligence is worth it's weight in gold. Uber used anonymous reports from credit card bureaus, email agencies and even reverse engineered APIs for intelligence
* If products have similar networks and not significantly differentiated, you cannot really have a winner-takes-all

## Bundling
* Bigger products can cross-sell other products easily, which can help them quickly get over the cold start problem
* Bundling doesn't work if the products it is cross-selling is poor quality
* Good bundling allows different products to talk to each other and use each other's networks
    * Eg: Instagram and Facebook are now heavily integrated, such it's easier for networks to communicate with each other
* Bundling is powerful but it can create clutter and poor product decisions