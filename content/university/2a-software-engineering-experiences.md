---
title: 2A Software Engineering Experiences
date: 2020-12-19
---
2A was an interesting term to say the least. A fully online experience with very little interaction with peers and different testing/assignment polices...definitely a term to remember.

Let's get straight into the review. There are 5 parts to this post:

1. Academics
2. Extracurriculars
3. Coop
4. Dealing with online school
5. Resources

# Academics

In comparison to 1B, 2A courses are much more interesting and are actually applicable to our lives as software engineers. What I thoroughly enjoyed in this term is how some our courses blended content together, such as our compilers introduction course in CS 241 and our computer architecture course in ECE 222. It seems weird to say this, but I actually enjoyed listening to the lectures and going in-depth about the various idiosyncrasies of each course.

However, there was much to dislike with the online academic experience. I found that there was a marked increase in time that I had to spend in order to get the same marks as before. Difficulty did not increase compared to 1B, but the time cost was significantly higher. I attribute this mainly to the inordinate amount of assignments and projects in each course: a typical week consisted of 1 lab, 1-2 quizzes, 3-4 assignments and possibly a 2-week project. Furthermore, each of these long assignments actually mattered quite a lot to your overall academic performance. Back in 1A and 1B, I could simply not finish an assignment if I felt that I was spending too much time on it and my time could be better invested elsewhere; this would not have a huge impact on my grades. However, every assignment and project mattered this term, sometimes painfully so. Not a huge fan of this.

Professors are still adjusting to this new environment and asking them to shift from an exam-based course to a more assignment-based course is quite difficult. Every single instructional team for each course did a stellar job and tried to make the transition as smooth as possible. Hopefully, some of the kinks will be ironed out for the next online term.

Let's dive deeper into some of these courses:

## SE 212: Logic and Computation

I like to descibe this course as the CS version of MATH 135. This course teaches students how to prove logical arguments and prove that the programs that we write will work. This is a pretty important course if you are interested in safety-critical systems where you need to guarantee that your system will work (i.e. the software that runs the automatic landing of SpaceX boosters).

Here is a general overview of the concepts that you will learn in this course

* Propositional logic (an extension of MATH 135 Boolean logic)
* Predicate logic
* Proof theories: transformational proofs, natural deduction, semantic tableaux
* Set theory and relations
* Z schemas (a way to mathematically define how any system should work)
* Program correctness

I found that if you have a solid understanding of constructing proofs in the pre-midterm content in MATH 135, this course should not be extremely difficult. The content is interesting and the professor did an excellent job teaching some of the more difficult parts of this course, such as soundness vs. completeness or program correctness.

This was by far my most time consuming course. We had a few assignments paired with 3 major projects (a satisfiability proof checker, a proof for a game of Mastermind and a Z schema of a library system) which took ages to complete.

Some tips for success in this course:

* Deliberate practice is extremely important. Like MATH 135, some proof techniques are non-intuitive (disproofs were very weird for me) and the only way to get better at it is through targeted practice on your mistakes. Use your MATH 135 study skills for this course.
* Start your assignments early: this is just general advice for all courses but I would say that this is particularly the case with SE 212. You will inevitably get stuck on proofs, which may require you to take a long break before you take another crack at it. It will be stressful if you keep these assignments to the last minute
* Terminology may get very confusing very quick. I would highly suggest going to the office hours of this course if you feel that you are confused at any moment. 212 content continues to build on itself, so maintaining a solid foundation is incredibly important.

Here are a few examples of problems from our homework to give you a taste of what we did:

![[Screen Shot 2020-12-19 at 9.25.28 AM.png]]

![[Screen Shot 2020-12-19 at 9.26.22 AM.png]]

## ECE 222: Digital Computers

For anyone like me who has no idea how a computer works, what computer caches do or how our C++ code is actually executed on a CPU, this course will be enlightening. This course covers how CPUs work, how we access memory and the interfaces that we use in order to execute operations. By the end of the course, you should be able to recognize why Apple's new M1 chips are so revolutionary or any of the hardware-related news that pops up in tech articles.

Here is an overview of the content you will cover:

* Computer performance
* ARM instruction sets
* Datapath and controls of a CPU
* Memory access and implementation
* Cache access and implementation
* Pipelining

Like all ECE courses, this course also has a lab component. Compared to 124 labs, this lab was a lot more chill and was somewhat interesting. Code is written in ARM, which is a low-level assembly language. While at first you might complain about using this language, I think every software engineer needs to use it at least once. At the very least, it makes you appreciate all the abstraction that higher-level languages provide, like C++ and Java. If you are interested in embedded/low-level programming, learning ARM would be extremely important. Another plus is that you will most likely cover MIPS in CS 241 which works on the exact same principles as ARM. Thus, you will already have a solid foundation before you start the 222 labs.

I also feel that this course has a few myths to it that I heard from upper years which is not always true:

* ECE 222 exams are like biology exams; just memorize as much as you can: This is totally dependent on your professor. Our exams were much more focused on problem solving, like determing the performance of a certain segment of C code or discovering hardware hazards given a sequence of instructions.
* You need to do well in 124 to do well in 222: That's not true. None of the Mealy or Moore state machines ever popped up in this course. You just need to understand how AND and OR gates work as well as how muxes work.

In my experience, my best tip for success is rigorously prepare tutorial problems. The style of tutorial problems matched exam problems so I at least knew how to approach the problems. I also think having a strong grasp of ARM is essential to do well in exams.

As always, here are a few examples of problems that we would regularly solve in this course (pulled from our textbook):

![[Screen Shot 2020-12-19 at 9.57.34 AM.png]]

![[Screen Shot 2020-12-19 at 9.58.41 AM.png]]

## CS 241: Foundations of Sequential Programs

This is our baby compilers course. Over the course of several assignments, we built our own scanner, parser, context checker and assembler in C++/Racket. In our term, we also built our own heap allocater and linker. This course pairs quite well with ECE 222 as it covers similar content.

Here is an overview of the course:

* MIPS machine language
* Regular and context-free languages
* Top-down and bottom-up parsing
* Context-sensitive analysis
* Code generation
* Compiler optimizations
* Memory management
* Loading and linking

My experience with CS 241 was overall quite pleasant. The content can get quite theoretical at times (especially when you get introduced to DFAs) but the assignments helped me internalize much of the content in our course notes. So far in my university life, debugging assignments have been the most painful in 241 as you may have to debug binary outputs.

Students have the option to take the enhanced version of 241. At the time of this post, 241E uses Scala as opposed to C++ to build the exact same tools. There were some other differences in the 241E course compared to 241:

* Marks are only from Marmoset public test cases. In other words, 241E had no quizzes and no secret test cases.This does not mean it is any easier to perform better in 241E compared to 241; it is still challenging.
* You will learn a lot more about functional programming, such as closures

If you are thinking about taking 241 vs. 241E, analyze the following factors:

* **Time**: 241E assignments seem to take longer to complete than 241 assignments since you are not only learning new content, but also a whole new language. This was primary reason why I did not take 241E.
* **Interest**: If you are interested in compilers or functional programming paradigms, 241E might be of interest to you.

This was one of the easier 2A courses. If you can stay up-to-speed with lectures (which can be challenging at times), this course should be relatively OK for everyone.

Here are examples of theoretical problems as presented in our course notes

![[Screen Shot 2020-12-19 at 10.12.26 AM.png]]

![[Screen Shot 2020-12-19 at 10.14.05 AM.png]]
## STAT 206: Statistics for Software Engineering

This is a combination of STAT 230 and 231 and essentially AP Stats with some more distributions and calculus. Here are some of the major concepts you will learn

* Counting (it's harder than you think)
* Probability laws: conditional probability, Bayes' Theorem, total probability
* Random variables
* Discrete distributions: binomial, geometric, negative binomial, hypergeometric, Poisson
* Multivariate distributions and relationships
* Continuous distributions: Uniform, exponential, normal, chi-squared, student's t
* Maximum likelihood estimation
* Confidence intervals and relative likelihood intervals
* One and two population tests
* Goodness of fit tests

If you have previously taken a statistics/data course in high school, most of the course will not be new. The addition of calculus is still very simplistic and you can get by with your MATH 117 knowledge. I highly recommend reviewing the STAT 230 and 231 textbooks as you complete this course as many of the questions on assignments and exams are pulled from these textbooks

Sample problems:

![[Screen Shot 2020-12-19 at 10.24.00 AM.png]]

## CHE 102: Chemistry for Engineers

This is basically AP Chemistry or Grade 12 chemistry. This should hopefully be a very easy course as there is little new content introduced in this course.

Here's a quick overview of what we learned:

* Stoichiometry
* States of matter
* Reaction rates
* Phase equilibrium
* Reaction equilibrium
* Electrochemistry

I don't have much to say for this course. It is pretty useless for SE students and it is only used to fulfill a natural science requirement for our engineering accreditation. Fortunately, our professors realized how little we care about the course and put all material online so that we could review it at our own pace. There were 6 unit tests that were also relatively straightforward. The course itself did not consume much time at all, which I really appreciate.

My only advice for this course is to look through the tutorial problems if you want to understand how quiz problems will be structured. They usually pull the same type of questions and change up the reaction/elements/numbers, but those are relatively trivial changes if you understand the major concepts.

## MATH 237: Calculus 3

First off, this is not a required course for SE students; I took this course as a requirement for my Statistics minor. If you have taken MATH 119, MATH 237 is a repeat of everything previous to the MATH 119 midterm, so it should be extremely straightforward for most SE students.

Here is the content for 237:

* Scalar function graphs
* Multivariable limits
* Continuity and differentiability with multiple variables
* Linear approximations and partial derivatives
* Multivariable chain rule
* Directional derivatives
* Optimization
* Mappings and coordinate systems
* Double and triple integrals

The main difference between 237 and 119 is that there is a heavier emphasis on proofs. These proofs are not like the delta-epsilon proofs you learned in 117 and are not extremely difficult to learn. Furthermore, 237 has a much better explanation on the reasons why we perform certain operations in multivariable calculus, like the Jacobian scaling of integrals.

This was my most smoothly run course this term. All content was found on Learn with self-paced material. There were biweekly assignments that were at the right difficulty level and a longer final assessment. The instructors posted several resources including YouTube recaps of content and offered extensive help sessions for those who needed it. Overall, I was quite pleased with how 237 turned out!

Some sample problems in 237 that you will not find in MATH 119:

![[Screen Shot 2020-12-20 at 10.40.43 AM.png]]

![[Screen Shot 2020-12-20 at 10.22.25 AM.png]]

## Review

Generally speaking, 2A academics was easier than 1B academics in terms of content, but required a lot more time than 1B. The issue is that there are several confounding factors for this increase in time cost that I cannot easily separate:

* Coronavirus led to different assignment and testing policies, which led to more assignments
* Some courses, like CS 241, were already assignment heavy from before
* It was much easier for students to work for long hours as there was no clear separation between studying and personal time

Online schooling has taught me a bunch of lessons going forwards:

* **Having a strong friend group is incredibly helpful:** My friends and I often relied on each other for help on course content. Without my friends, I don't think this term would have gone as smoothly as it did
* **Be your own tyrant**: One of the biggest issues with online learning are the plentiful distractions on the internet that can severly derail your learning progress. I found it especially hard to focus on course content when YouTube videos and articles were just a Google search away. Over time, I started to develop more strategies for self-control in order to boost my focus. Focus management is becoming more and more crucial in the digital age. I have written a post about it [here](https://aaronabraham311.gitbook.io/aaron-s-thoughts/miscellaneous/focus-the-most-valuable-mental-commodity) if you are interested.
* **Time management is key**: Without a system of any sort, online term will be really challenging. Listening to lectures, doing homework problems and finishing your assignments are now purely under your own purview. This requires exceptional time management. I wrote a [post](https://app.gitbook.com/@aaronabraham311/s/aaron-s-thoughts/\~/drafts/-MOvjvASz6jqyldFBrrL/university/studying-in-university) about this dedicated to first years and another [post](https://aaronabraham311.gitbook.io/aaron-s-thoughts/books/how-to-become-a-straight-a-student) with notes on some excellent time management books. If you are looking for a solid guide on developing a time management system, checkout Havin Leung's [post](https://havinleung.com/2020/04/21/how-to-study-a-guide-for-struggling-students/)!
* **Do things asides from studying**: Coding up web applications at UW Blueprint or running events as part of SE Soc was a nice break from the constant grind of school work. From my experience with online school, it is a lot easier to continuously grind on school work, which will lead to eventual burnout, which makes breaks even more valuable than before. Please take care of yourself and take a step back occasionally to go two steps forward.

# Extracurriculars

Due to crazy amount of time school took, I was unfortunately not able to be involved with extracurriculars as much as I wanted. However, I still managed to accomplish some incredible stuff as part of UW Blueprint and Software Engineering Society

* UW Blueprint: I was asked to lead development on one of our North Star features, namely Google Maps integration with our application. This required a huge amount of research and technical planning before I could actually start to work on it. I was able to make some good progress and will be finished with my work by early January.
  * There was a lot of PM-type work with this project. It required me to dive deeper into user interactions and understand the why behind the features we wanted to build, which was quite interesting and a nice change from monkeying around with React and JS.
* Software Engineering Society: helped organize resume critiques, game nights as well as a class dinner. These experiences helped me realize how difficult it is to foster connections over Zoom. It's a unique challenge that we are working to overcome.

I will be spending a little bit more time on extracurriculars next term. I will be a product manager on Blueprint and scoping out one of our newest projects in the space of mental health and also restarting our SE Society podcasts. Super excited for what's to come!

# Co-op

I entered the term expecting an extremely dry job-market as the job market for Fall 2020 was quite poor from the perspectives of upper years. However, my friends and I were pleasantly surprised that the job market was rebounding, especially for tech jobs.

As of late December 2020, the SE 2A cohort is enjoying an employment of 93%, which is significantly higher than the other engineering programs. It is incredibly difficult for majors that are more hands-on, like nanotechnology and mechanical engineering, to secure coops at this time. Hopefully, the non-tech job market will rebound soon given the hopeful news of a coronavirus vaccine.

I had two goals for my Winter 2021 coops and I applied to positions that exclusively met these two goals:

* **Scale**: I wanted to learn how to build systems/analyze data at massive scale. I have worked most of my life on smaller projects with small impact. Learning how to design scalable systems is truly the essence of software engineering and thus I only applied to positions that I felt could offer me this opportunity.
* **Product management**: I have become more enamoured with PM as a career after my experimentations over summer with leading product efforts at Phoenix Data Consulting. I wanted to try out one coop in this field for Winter 2021.

At the end of the term, I had the opportunity to do a PM coop at a mid-size company as well as a data science coop at a large-scale company. Choosing between the two opportunities was quite tough, but after consulting with my upper year PM friends and using some of my other decision making strategies, I decided to accept the data science coop offer. Thus, I will be interning at Wish as a Data Scientist for Winter 2021. I am in no position to offer any advice regarding this decision given my inexperience, but I might make a post sometime later going over my decision making process.

I also tried my hand in external recruitment. The main issue I had was getting an interview in the first place. There were several factors in this:

* I did not have a huge amount of referrals and the referrals that I did have were from interns. These are still incredibly useful but the utility is not as high as full-time referrals.
* My graduation year of 2024 meant that I was considered as a freshman for many internship programs, which was unfortunate
* My technical skills are still not up to par to do a stellar job on some of the coding assesments. Taking these online assessments has taught me what I need to focus on for next recruitment season, which I am grateful for.

Overall, I am quite pleased with this co-op recruitment session. I have learned quite a lot about recruitment and will try my best to prepare for the upcoming coop hunt for Fall 2021.

# Resources

As always, I have a collection of resources that I hope will help future SE students in 2A coursework.

* SE 212: For propositional logic, I used this [tool from Stanford](https://web.stanford.edu/class/cs103/tools/truth-table-tool/) to speed up my  proof discovery process. Since this course content is unique, I was unable to find external resources that matched the quality of resources given to us. I would highly recommend students to practice the homework problems and assignment questions rigorously if you want to do well in the exam.
* ECE 222:  Tutorial problems were the best model for ECE 222 exams, so pay attention to those and grind them out before your exams. I found [this video series](https://www.youtube.com/watch?v=qcBIvnQt0Bw\&list=PLiwt1iVUib9s2Uo5BeYmwkDFUh70fJPxX) quite useful in understanding virtual memory and [this video](https://www.youtube.com/watch?v=OweJGixJVtU) useful when learning about data hazards. The textbook is also a decent resource if you are ever confused about a particular topic.
* CS 241: Course notes are all you need
* STAT 206: The STAT 230 and STAT 231 textbooks are the best resources that you can use to prepare for the 206 exams. There are several practice exams in these textbooks that mimic the test quite well (in fact, two questions on our final were pulled from these practice tests). 206 can be non-intuitive at times, so [this channel](https://www.youtube.com/user/jbstatistics/videos) may be helpful.
* CHE 102: Course notes are all you need
* MATH 237: Course notes are all you need. You may want to use [Geogebra](https://www.geogebra.org/3d?lang=en) to model equations. Also watch out for YouTube videos posted by the instructors which often have helpful hints and tips for solving 237 problems.

Notes for my 2A term can be found [here](https://github.com/aaronabraham311/Notes/tree/master/2A).
