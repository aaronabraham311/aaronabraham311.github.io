---
title: 3B Software Engineering Experiences
date: 2022-12-21
---
Coming into 3B after a very fun summer, I was nervous to say the least. Every SE student has heard that 3B is the toughest term of the program, but now that I have gotten through it, it's not as bad as I thought!

As usual, feel free to skip through the following sections:

1. Academics
2. Extracurriculars
3. Co-op
4. Exchange
5. Resources

# Academics

3B was definitely a lot lighter in course load than I initially expected, but concepts were arguably harder than other terms. I still believe 2B and 3A were more difficult than 3B due to the course load, but this could have been influenced by the pandemic. Regardless, I really enjoyed the content that we learned in this term compared to many of my previous courses. It all felt somewhat relevant and practical, as compared to previous theoretical courses that focused on proof-based learning.

Let's get into the courses.

## SE 380: Introduction to Feedback Controls

SE 380 is one of the most notorious courses of the SE program. It builds on the knowledge we gained from MATH 213 in 3A to analyze and control systems where feedback plays an important role.

Here's a list of topics that we learned:

* Mathematical representation of a system: differential equations, state space representations, Laplace-domain equations and multi-dimensional systems
* Linear system theory: stability, system performance metrics, first order, second order and higher order systems
* Analysis of feedback control systems: Routh-Hurwitz criterion, fundamental theory of frequency response and Bode plots, Nyquist plots, Nyquist stability and Bode stability criteria
* Controller synthesis: loop shaping, lead, lag and lead-lag compensators, PID controllers, root locus, state space controllers

I personally really enjoyed SE 380. Control systems are some of the most complex software that have been developed and they are widespread in industry. Control theory is prevalent in software engineering too; our CPU scheduling algorithms, the [Go garbage collector](https://speakerdeck.com/madhavjivrajani/control-theory-and-concurrent-garbage-collection-a-deep-dive-into-the-go-gc-pacer) and the [Go scheduler](https://www.cockroachlabs.com/blog/rubbing-control-theory/) use this field of math. Furthermore, many of the hard tech companies specializing in areas like nuclear fusion and space use control theory extensively. I liked this course even more than MATH 213 since this course taught us how to use math to make a system behave to your liking.

Typically, students of this course have complained about the irrelevance of SE 380 to software engineers, but there has been a lot of improvement. For one, our labs are no longer like ECE 380 labs that focus on motor control; our labs use MATLAB to control various systems that are already coded up for us. The professor of our course (Prof. Gennaro Notomista) introduced new concepts that are used extensively in actual control engineering like state-space controllers.  The professor had even invited an industry robotics specialist to talk about controls in software. As someone who has been privy to course curriculum discussions, I am expecting that this course will continue to become better as time passes.

In terms of coursework, this course was quite manageable. We had weekly assignments, a midterm, a few "labs" (we didn't need to go into the lab for anything) and a final project where we built a controller for a robot in RoboHub. Some tips for success in this course:

* **Review MATH 213 and parts of MATH 115**: You will use a lot of concepts taught in 213. Also remember how to take vector-matrix cross and dot products, inverses, determinants and eigenvalues from 115. Without a solid understanding of these courses, you may find it hard to keep up in the very beginning of the course.
* **Do not restrict yourself to course content**: SE 380 teaches the same content that you would find in any introductory control theory course. Please do scour the Internet for resources to practice and understand concepts, because this course doesn't have much practice
* **Intuitive understanding is quite important**: Many students in this course got thrown off during assessments when asked theoretical questions about control systems. I believe it's because many of us didn't truly understand the intuition behind the concepts of controls (I for one had a tough time with developing intuition). Try to develop as much of a solid understanding as you can so that you can perform well in theoretical and computational assessment questions.

Here are some sample questions to help you understand what types of questions we were typically asked:

![[image (5).png]]

![[image (4) (1).png]]

## CS 343: Concurrent and Parallel Programming

For most of university, we have been dealing with programs that are run sequentially on one processor, but most industry programs are actually run on multiple processors concurrently. This course goes into the specifics of how to construct programs that can be run concurrently. Topics taught include:

* Non-local transfer: using labels effectively and exceptional returns
* Coroutines: programs that have their own stack, enabling pause & resume semantics
* Threading
* Software and hardware locks
* Concurrent errors: starvation, deadlock and livelock
* Indirect communication via monitors
* Direct task-to-task communication
* Server-side and client-side concurrency optimizations
* General programming optimizations and other approaches to concurrency

CS 343 was the hardest course for me this term. Not only was much of the concepts new to me, but there was a lot of work associated with this course. There are 5 major assignments with one final group project, where each assignment took almost 2 weeks to complete.  These assignments are notorious to debug since it is very hard to replicate concurrent behaviour. This course took up a lot of my free time in 3B.

Despite the difficulties of this course, I greatly enjoyed the content. I learned a lot of different concurrency concepts and how to apply principles in any language. This leads me to the main point of criticism with this course: the usage of uC++ for all assignments. This language is an augmented version of C++ that implements a great majority of concurrency constructs. At times, I have felt that this is a uC++ course rather than a concurrency course, but looking back, I can see how difficult it is to teach concurrency when each modern language has their specific style of concurrency. The professor (Prof. Peter Buhr, one of my favorite all time profs) took the approach of introducing generic concurrency principles rather than practical industry-relevant code, as it is much harder to teach the theory of parallel programming than the practicalities of threading libraries. After going through this course, I can see why any other approach to teaching concurrent programming wouldn't have done justice to concurrency.

Some tips for success in this course:

* **Use TA office hours**: Many of my friends used the CS 343 TA to get help on bugs in their programs. Furthermore, the majority of our marks for assignments come from hand-marking. Talking to a TA can often reveal some of the things they are looking for in an assignment. It has saved me a few marks!
* **Start assignments early**: I say this in every term review, but please don't keep these assignments to the end. They are very difficult to cram and painful to debug
* **Build easy-to-debug programs**: Because concurrent programs rely on non-deterministic CPU allocation to different tasks, it is hard to always get the same result for the same input. Ensure that you build programs that are easy to understand and dissect when you run into an inevitable bug. Be disciplined in your debugging; start small and gradually build up to larger test cases.
* **Pay attention to every line in the course notes**: One aspect of this course that I didn't like is the amount of useless trivia in exams. This requires students to put in a lot of time memorizing random uC++ facts. This is the unfortunate reality of the course, so be prepared to use those memorization skills.

Here are some example problems from a past exam:

![[image (1) (1) (1) (1).png]]

![[image (14).png]]

## ECE 358: Computer Networks

This course teaches everything you need to know about how the Internet works. We approached our study on the Internet by looking at various layers:

* Application layer: HTTP & DNS
* Transport layer: Demuxing, UDP, principles of reliable data transfer, TCP
* Network layer: routing, forwarding and various methods of determining and communicating best paths to forward packets (Djikstra's, OHCP, BGP)
* Link & physical layers: frames, Ethernet, switches

This course was one of my favorite courses to date. The course was very well structured, course load was very light and the content was extremely useful. I would highly recommend this course for people who are not in ECE/SE for an elective, as knowledge of the Internet is quite important for software engineers.

In terms of course load, we only had 3 "labs", where we played around with various internet utilities or created small scripts. This is possibly the lightest ECE course I have ever taken. Exams were also very reasonable and the course staff provided plenty of practice problems. My advice for this course is:

* **Don't restrict yourself to university content**: While there's plenty of problems and extra explanations given by course staff, almost all networking courses around the world use the same textbook as us; it is the standard. Given that, you can look at problems and content from any university and it's quite likely that it will match with what is taught at UW.
* **Use memorization techniques**: There's a lot of concepts and terminology in this course as one would expect out of something as complex as the Internet. Use whatever technique you use to memorize concepts for this course. Course assessments sometimes require you to answer trivia.

Here are some examples of exam problems taken from an old exam:

![[image (23).png]]![[image (27).png]]

## SE 464: Software Design and Architecture

This course attempts to teach engineers how to design large-scale codebases through the use of design patterns and architecture styles. Content include:

* Design pattern overview
* Architectural style overview
* Architectural modelling
* Security principles
* SOLID, DRY, STUPID principles
* Type systems
* Case studies: Google Chrome sandboxing, LLVM

To put it bluntly: I really hated this course. As someone who has had the privilege of designing scalable, low-latency systems during co-op, I was expecting a totally different course coming in. I was hoping that it would teach us to build scalable **systems** rather than **code bases**. I guess that's why this course focuses on design patterns, because it does actually help programmers in the creation of large code bases. Frankly, that's not what software engineers need anymore; system design is what has become more of a necessity.

This course has a huge amount of overlap with CS 247, especially in the discussion of design patterns, SOLID and DRY. Any additional content introduced often didn't make thematic sense with the rest of the course content. I realized this after my second class and decided to never enter the class again. This course got me sufficiently fed up to the point where my friend and I petitioned for a curriculum change. We proposed that there should be a complete course redesign centred around system design rather than code design and gave a bunch of recommendations on what students what to see in an architecture course. There's a lot of positive attention within SE faculty about these suggestions, so I am hoping that this course will change starting next year.

I don't really have much advice for this course asides from reading course slides. If the course is anything like what I experienced this term, I would honestly recommend skipping class and reading slides by yourself to save time. I don't have any practice examples of questions for this course.

## SE 390: Design Project Planning

This course introduces students to FYDP by mandating that students create 3 "mini-projects" throughout the term. Mini-projects are often done in a group of 3 or 4 and require us to build a small project scoped to 2-3 weeks. You don't even necessarily have to code; a mini-project could also include market validation, design mockups or user studies. At the end of the 3 week cycle, you present your project to the instructor and get peer feedback. Afterwards, you can switch up or stay with your project. You can also switch your team if you don't vibe with them.

My 3 projects were:

* Design mockup of a Chrome extension to make online shopping easier
* Contributing to PyTorch's port-over to Metal
* Building out a new UI component for Airflow configuration management

This is a very chill and easy course, with most people cranking something out the week before the project is due. Furthermore, this course can be done asynchronously; there was only 1 lecture we needed to attend in-person.

I would recommend future students to take SE 390 as a chance to explore and do things without the burden of marks. Our group decided to pursue open source projects since there are plenty of well-scoped issues. The course is explicitly designed for students to explore different things and different teams. If you do want to dive deep into one project, you should consider planning out your project ahead of time and ensuring that your 3 mini-projects all feed into the same project.

## STAT 341: Computational Statistics and Data Analysis

This course is all about taking statistical concepts learned in STAT 230 & 231 and applying a computational lens on it, specifically through R. Concepts taught include:

* Population attributes, transformations and effects of changing population variates via sensitivity curve analysis
* Solutions of optimization problems via gradient descent, Newton, Newton-Raphson and iteratively reweighted least square methods.
* Sampling: errors & bias, various sampling designs, population estimates via Hurvitz-Thompson estimates
* Inference: designing a randomization test, random and confidence intervals, bootstrapping and bootstrap intervals
* Prediction: APSE (average predictive squared error) analysis

This is not a mandatory course for SE students; I took this as part of my statistics minor journey. Out of all the courses I have done in my statistics minor, this is the course that I enjoyed the least. There wasn't anything incredibly novel in the course and it just seemed to be a repeat of concepts that we learned in STAT 231, but with R added on top (asides from bootstrapping). Content also seemed quite disjoint and I am not sure why this was all stuck into one course. The lectures were also quite lacklustre since a large part of lectures was just reviewing pre-written code. Given my total lack of interest and the lack of challenge in this course, I only showed up to 3 of these classes for the entire term :p.

The course load was quite light, with about 4 assignments and 2 term tests. I don't particularly like the math faculty's approach of having 2 tests instead of 1 midterm as it extends my midterm season quite a lot compared to other SE students, but that's mostly out of my control.

Advice for this course:

* **Scour tutorial and lecture code for assignments**: Often times, assignment questions are just minor variations of problems covered in tutorials and lectures. Knowing this sped up my assignments significantly
* **Create "recipes" for solving questions**: Test question formats don't change very much year after year, so if you can develop an algorithm to approach every problem, you should have no issue. Common patterns I learned to solve are: formulating optimization problems in terms for Newton's method, sensitivity curve analysis for piece-wise attributes and Hurvitz-Thompson estimates of attributes which are functions of population totals.
* **Make extensive use of Discord**: the class typically uses Discord as a substitute of Piazza and the instructors are quite quick to respond to any question. I greatly appreciated this as it helped me resolve a lot of personal confusion about course topics.

Here are some sample problems:

![[image (2) (1) (1).png]]![[image (19).png]]![[image (10).png]]
# Extracurriculars

At the beginning of this term, I resolved that 3B will be my last term where I partake in extracurriculars. This was for the following reasons:

* **Leadership positions**: I was president for SE Soc and UW Blueprint this term and it took quite a lot out of me. I really enjoyed it and was able to make meaningful impact, but being a leader requires a tremendous amount of time and organizational awareness. I did not want to spend that time and energy on clubs during my last 2 terms on Waterloo; I wanted to direct these to other pursuits.
* **Gain**: As I talked about in my [[the-importance-of-extracurriculars|post about extracurriculars]], I mainly joined them because I could grow myself as a person and meet a lot of people. To be completely honest, I think I have been hitting marginal gains after the first 3 years on these extracurriculars. Knowing this, the reason for staying on these clubs started to fade.
* **Fresh blood**: One thing that I greatly fear about myself and everything that I involve myself in is stagnancy. I have had a feeling for a long time that organizations at UWaterloo (not just the ones I am involved in) have been getting more stagnant with less fresh ideas. One way to reinvigorate these clubs is to encourage new members to take the helm and guide the ship to a new destination. I think it was due time that I step away and mentor a new generation of leadership to take calculated risks and push these two clubs in a way that they see fit.

These reasons gave me motivation to make a lasting changes in the clubs that I was involved in. Some things that I accomplished include:

* Blueprint
  * Setting up a maintenance alumni team for Blueprint to maintain shipped projects
  * Instituting a documentation culture for execs to ease operational load during recruitment, onboarding and off-boarding
  * Setting up a structure to finally start in-person activities after the pandemic (we're also going to have a fully in-person team next term!! Very excited to see this)
* SE Soc
  * Various in-person socials, resume critiques and panels
  * Set up a maintenance team for FYDP project maintenance
  * Got an ad-hoc approval for SE students to switch sequences in their last year such that their last fall co-op can be switched to summer instead. This was huge for our class and I am positive this change will last for future students. Since summer co-op has far more options and fall usually has new grad recruiting, this sequence change will be the best for most students. This single change probably prevented a good portion of our class from switching to CS.
  * Pushed for curriculum changes in SE 464 (which I am really excited about!!)
  * Consulted for SE 380 curriculum changes
  * Consulted for wider curriculum changes coming to SE. There's a lot of very exciting things happening that I think will benefit students enormously, especially in the third and fourth years. I can't reveal much as it hasn't been fully approved.

Even though this term marks the end of a chapter in terms of extracurricular involvement, I really did enjoy the whole experience. For anyone reading this, I cannot recommend enough in getting involved in campus club leadership if you want to meet new people and grow as a leader.

# Co-op

My co-op grind for 2023 started, as usual, back in June 2022. This summer was the ideal recruitment season for me since I am 2 years out from graduation (intern to full-time conversion is way easier), have relevant experience and I started preparation well before internship applications opened.

I started brushing up on Leetcode during June, using [Grind 75](https://www.techinterviewhandbook.org/grind75) to get my patterns down. As soon as applications started opening in July, I started applying. I applied to as many companies as I could; for companies I was particularly interested in, I followed up with cold emails to recruiters.

This approach was relatively successful, albeit hard while I was doing my co-op at Twitch. Scheduling interviews to make sure it didn't overlap with meetings was annoying, but this is just the name of the game. Regardless, my early grind in June paid off, with offers lined up by end of September. I also used WaterlooWorks and only applied to a handful of companies and got a few offers from there as well.

At the end, I had to make a few hard decisions. Here were my decision criteria:

* **New grad**: I really wanted to choose co-ops that I believe would also be a great place to work for full-time. Ideally, this would be a fast-paced company with high growth, autonomous but directed leadership, a good place to grow as a software engineer and financially secure (especially in the recent downturn).
* **Skills**: I wanted to build up on my technical leadership and system design skill. Any company that specialized in that made it to the top of my list
* **Future plans**: I've realized that way down in the future, I want to lead a company, either as a founder/early employee or as a leader at a fast-growing company. Joining firms where I wasn't exposed to that type of risk or building up the capabilities to bring my plan to fruition is a very foolish idea for me.

Given all of this, I whittled down my offers to 2 companies. I will be joining Databricks for W23. I'll talk about my co-op choice for S23 in a later post.

# Exchange

I have one exciting thing to add to my usual term updates. I applied to exchange in late October looking to do an exchange term for my 4A. There were a few reasons why:

* Exchange seemed like a once in a lifetime opportunity and I really didn't want to miss out.
* I have always been looking to immerse myself in a culture without the burdens of school or co-op, and this seemed like the perfect opportunity to do so
* During the application time, it was still uncertain if SE admin would allow for sequence shifting. You can force a sequence shift if you take an exchange term during your 4A term and ask for it to be shifted to fall. This was a fail-safe that I used.

Fortunately, I got matched with UC3M in Madrid for Fall 2023. It's quite likely that I will accept after I do some financial planning for next year.

# Resources

Here are some resources that I used during my 3B term

* SE 380: I used [Brian Douglas](https://www.youtube.com/@ControlLectures) videos extensively after the midterm. He has very high quality videos that go through a lot of control theory. For exam practice, I looked at other program's control courses in EngSoc. I also looked at a previous offering's course notes to go over confusing parts of SE 380 (eg. matrix exponentials). This is uploaded in my notes repository. You can also refer to [Steve Brunton's lectures](https://www.youtube.com/playlist?list=PLMrJAkhIeNNR20Mz-VpzgfQs5zrYi085m) on control theory for some theoretical backing of concepts in this course.
* ECE 358: There was plenty of practice provided within course content, so I didn't really need to search for extra resources. Also, there are some practice problems in the EngSoc exam bank.
* CS 343: Prof. Buhr usually provides some practice exams. I complemented this with exams found on MathSoc's exam bank.
  * Hack: UWaterloo has put Duo auth on SSH, which makes it quite annoying to develop on their servers. I used [this hack](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-ubuntu-22-04) to reduce the annoyance.
* SE 464: Slides are sufficient.
* STAT 341: Lecture notes are sufficient.
* SE 390: You don't need any resources, just your creativity :). 

My notes for this term can be found [here](https://github.com/aaronabraham311/Notes).
