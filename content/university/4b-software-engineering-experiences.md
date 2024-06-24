---
description: "Published: April 27, 2024"
title: 4B Software Engineering Experiences
date: 2024-04-27
---
4B was 100% the best term ever, but also my most bittersweet term. Writing out this piece is really reminding me that I am forever done university. Let's jump right into it.
# Academics

4B was the easiest on-campus semester that I had to date. I mostly took electives, so the workload was quite manageable. This was also done by design; I wanted 4B to be a lot more relaxed so that I had more time to hang out with friends. I would strongly recommend students to keep their last semester light so that you can deepen your friendships.

## STAT 443: Forecasting

This course applies a statistical rigour to the art of forecasting time series data. Forecasting is used in all sorts of industries, including finance, construction, weather, social media and more. Concepts learned include:

* Linear polynomial regression: This is mostly a review of STAT 331, but there is little bit more theoretical rigour
* Residual diagnostics
* Regularization models
* Stationary processes
* Removing trend and seasonality via smoothing: moving average filters, exponential smoothing, regression, differencing, Holt-Winters algorithm
* Box-Jenkins modelling: moving average models, autoregressive models, SARIMA modelling

My prof (Prof. Reza Ramezan) was extremely knowledgeable and made going to lectures interesting. There are 3 assignments for this course, 2 tests and 1 final project. The final project made this course a little annoying, as it was extremely vague and required a lot of work for teams.

Overall, I had a pleasant experience with this upper-year stat course. I wanted to take forecasting because I have seen my mom using forecasting for cost control in certain oilfield projects, so I was really curious how it was done. I certainly learned a lot and hopefully can use it sometime in the future. I also used this course for my open slot in the advanced technical elective after convincing SE faculty to do so.

Some tips for this course:

* **Be thorough with your proofs**: This course lends itself to a lot of theoretical questions. Make sure you understand all the proof techniques and work through theoretical questions in your own time
* **Start your project early**: It is a lot of work, especially near the end where you need to record a video and make a report. You want to ensure that you choose a good group who are at least as conscientious as you

Here are some sample questions:

![[image (39).png]]

![[image (40).png]]

## STAT 332: Experimental Design and Sampling

This course is all about how to effectively create and analyze experiments. We also learned how to correct statistical analysis based on finite population sampling. Topics explored include:

* ANOVA analysis: Multiple treatments and blocking
* Factorial experimental analysis
* Analysis of sampling without replacement: how to construct tests and confidence intervals for population parameters
* Ratio and regression estimators for simple random sampling: can we use X's relationship with Z and Z's relationship to Y to have a better estimate of Y using X?
* Stratified random sampling analysis

This ranks in one of the easier statistics courses that I have taken throughout university. Prof. Reza Ramezan was my prof for this course again and made it somewhat interesting (even though the course content is bone-dry). The course itself is pretty light, with only 2 tests and 3 assignments.

I honestly believe that statistics students shouldn't have too much of a problem with this course. It is also pretty useful, as experimental analysis is very commonly used in industry. Even if the specific techniques are not always used, this course gave a great theoretical understanding of why we use certain analysis techniques and how to correct our analysis based on our sampling technique. I would recommend this course to other statistics students if they can stick through the dryness of the content.

Some tips for success in this course:

* **Practice computation questions:** A lot of mistakes made by students in this course was fat-fingering their calculator or forgetting important formuals. These are very easy yet expensive mistakes. It is especially common in this course as it is very applied
* **Understand the theory**: Even though this is a more computation-heavy math course, the professor can easily change the problem and make you solve a completely different problem if you are not familiar with the underlying theoretical principles

Here are some sample problems:

![[image (41).png]]

![[image (42).png]]

## CS 451: Data-intensive Distributed Computing

Most of the courses that we have taken so far have elaborated on how we can optimize software to deal with compute heavy load (eg. SE 350, CS 343), but engineers need to use different mental models when our software has to deal with data-intensive workloads. This course teaches those mental models. Concepts learned include:

* MapReduce
* Apache Spark
* Text processing: creating and storing reverse indices, Boolean and ranked retrieval
* Analyzing graphs: PageRank and modifications
* Data mining and ML: how to create and evaluate ML models, solving the nearest-neighbor problem via min-hashing, clustering
* Relational databases: how to take a SQL query and convert it into efficient Spark code, columnar databases
* Streaming
* NoSQL

Personally, I regret taking this course as I already learned a lot of this from co-ops. Sometimes, it felt that we were learning concepts that didn't really have much bearing to the whole data-intensive computing theme, like min-hashing. It was an easy course though, with just 7 MapReduce or Spark assignments. I took this as my CS ATE; I should have chosen something slightly more interesting or something that I could only learn in university. If you have not dealt with data engineering or designing data-intensive systems, then this course may be useful.

I don't have any problems to share for this course, unfortunately. As for tips:

* **Start assignments early**: I have said this in literally every term, but it is important in this course because you will be testing your assignments on shared computing clusters. If you leave your assignment to the last minute, you will not have the compute resources necessary to test your assignment
* **Pseudocode your assignments**: The best way to practice for the final exam, asides from reviewing your theory, is to pseudocode all the assignments and understand why every line of Spark/MapReduce was used. The final is very lenient, so syntax is not that important.

## CS 445: Software Requirements, Specifications and Analysis

This course discusses how to create requirements for software projects. Topics explained include:

* Requirements engineering process: elicitation, stakeholder management
* Domain modelling via UML class diagrams
* Use case and scenario modelling
* Sequence diagrams
* Functional modelling
* Object constraint language
* Behavioural modelling of a system via state diagrams
* Prioritization techniques
* Cost estimation techniques
* Risk analysis
* Linear temporal logic

This was taken simply because I missed the SE equivalent course due to co-op. I did not like this course very much at all; it taught me absolutely nothing useful. Many of the techniques that we are taught are never used in industry. It felt as if we are overcomplicating a very simple concept: make sure you know what you want to build before you build it. I don't think there is much need to add a bunch of modelling and math on top of it. For what it is worth, I will applaud the professor for including relevant software examples in examples, so it wasn't a total bore creating requirements.

This course offering has 6 assignments all linked to an imaginary software system that you create with your group of 5-6 students.

As for tips, I don't really have much. This is an incredibly straightforward and easy course. There should be no difficulties in doing well in this course.

Here are a couple of sample problems:

![[image (43).png]]

![[image (44).png]]

## SE 491: FYDP

My 2 friends and I have been working on an FYDP project since September 2023. We worked with Prof. Weiyi Shang to productionize a log parser that he developed called PILAR. His log parser is accurate and simple, but it was not engineered to work at the scale of modern software companies. We rearchitected his tool and released a [plugin](https://github.com/aaronabraham311/logstash-filter-pilar) for the Logstash log processing framework.

Since we already did most of the coding work for the project last semester over exchange, we spent most of this term doing various logistical work, such as setting up for our symposium. We also submitted a research abstract to the Foundations of Software Engineering Conference Student Research Competition and we recently heard that we have been conditionally accepted!

The actual course didn't have many deliverables asides from an abstract and a poster. The class requirements are very chill, but the difficulty depends on your project. I knew of several groups that had to grind until the very last minute on their projects.

Some tips:

* **Frontload your FYDP:** You will have 4A and 4B to work on your project. I would strongly recommend doing at least 80% of the work in 4A as you will lose steam in 4B. You will also have much less stress.
* **Choose well-scoped projects**: The best FYDP projects were actually simpler and required less work; they just chose great problem spaces and had unique software. You don't need to create an FYDP the scale of UWFlow; it is an outlier FYDP. I would strongly suggest looking into research projects, as they are often already well-scoped and have good mentorship. To do a research project:
  * Step 1: Identify professors that may have projects to work on (eg. CrySP lab, software language analysis, etc.)
  * Step 2: Look at their papers and propose topics that you could potentially work on. Don't ask the profs for projects, as they probably won't have any
  * Step 3: Meet and discuss your project proposal.
* **Take initiative**: The FYDP course can be poorly organized, so be on top of things and work on deliverables even if its published. For example, we realized our poster was due within 2 weeks yet our course instructor did not inform us. We worked on it at a comfortable pace. The instructor finally published this deadline within a few days of the deadline, putting a lot of teams in a stressful place.

Our poster (made on Figma):

![[image (45).png]]

# Non-academics

Since I withdrew from extracurriculars in 2022, I was left with a lot of free time this semester. I am incredibly grateful for this foresight, because it allowed me to have maximum fun this semester. Things that I did with this time include:

* Engineering events: DUSTED (drink a random pub dry), Iron Ring Shindig (massive party after getting your iron ring), Grad Ball
* Hanging out with friends
  * Lots of walks in Waterloo Park and Columbia Lake
  * Exploring as many food places as possible before we left Waterloo
  * Cooking each other dinners and hanging out
  * Movie nights
  * Overnight eclipse trip: we stayed in Paris for one night to stargaze and then headed out to Port Burwell to catch the total solar eclipse
  * Game nights
  * Random gatherings
* Going deeper into my hobbies of cooking and gymming
* Side projects: I have been building some personal software projects. I built an [Instacart receipt splitter](https://github.com/aaronabraham311/hannibal) and a AI-powered time blocker (not public at time of writing)
  * Some of this was inspired by [Socratica](https://www.socratica.info/), an organization encouraging students to create things (not just tech) in their free time. I would strongly recommend checking it out!
* Visiting relatives and friends
  * Went to Austin for a wedding
  * Went to Boston to visit a friend

Here's a random assortment of pictures from this term:

![[IMG 9984.jpeg|Solar eclipse]]

 ![[IMG 9526.jpeg|Embracing Texan culture at the wedding]]

 ![[IMG 9849.jpeg|Sunrise]]

![[IMG 9815.jpeg|Indian Spice (goated restaurant)]]

![[IMG 9817.jpeg|Lancaster Smokehouse]]

![[IMG 9790.jpeg|Making dinner with friends]]

![[IMG 9744.jpeg|Harvard]]

![[IMG 9655.jpeg|Iron Ring Shindig]]

![[IMG 9647.jpeg|Finally ringed up]]

# Final Reflections

Overall, university has been a blast. I still remember moving into V1 in 1A and anxiously thinking how I will survive university with no high school friends at UWaterloo coupled with an intense academic workload. Looking back, everything worked out well for me and I am incredibly grateful for it. I have incredible friends, I was able to take setbacks in stride and life opportunities came at me unexpectedly, but I was able to use them effectively.

For the incoming Waterloo students who are reading this, know this: Waterloo is difficult, but your experience is completely determined by you. You have the power to make the next 5 years fun and a foundation for a flourishing adult life, or you can give up and retreat. This university has taught me to take challenges head on, grab it by the horns and use it to better myself. There are a lot of opportunities at this school and it is up to you to take the initiative.

I am most grateful for the friends I have made along the way. They have cheered me on at my best and have counselled me at my worst. My number one piece of advice for first years is to find your people. Without that, university will be incredibly difficult.

For now, I will be doing a grad trip with my friends through Japan, Taiwan and Thailand. I hope to post updates in the Travels section of this blog. Afterwards, convocation, then travelling back to India and lastly starting work back at Ramp in August. This is university Aaron signing off :)

# Resources

None of the courses require outside material to succeed. I have updated my [notes repository](https://github.com/aaronabraham311/Notes).
