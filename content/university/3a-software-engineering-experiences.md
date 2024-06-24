---
title: 3A Software Engineering Experiences
date: 2022-04-25
---
As I was boarding the plane from Calgary in early January, there was a sense of dread for the upcoming 3A term. It had been 2 years since I last did an in-person school term and the first time I am living outside of dorm. This was also paired with excitement of finally going to in-person classes and seeing friends that I wasn't able to talk with in-person for years.

Looking back now that 3A is over, this was probably my most fun and enjoyable term at UWaterloo to date. The in-person was far better than all of my online terms and I really hope that we don't need to go back to online school.

Like my past reviews, I have divided my review into 4 parts:

1. Academics
2. Extracurriculars
3. Co-op
4. Resources

# Academics

This term was far lighter than 2B in terms of workload. The courses were more interesting and practical for us as software engineers. I greatly enjoyed the course selection this term.

Let's get into the courses:

## SE 350: Operating Systems

SE 350 is a high-level introduction to operating systems. An OS is a fundamental part of computer systems that provides abstractions for software to interact with hardware, like I/O devices, memory and more. Concepts covered include:

* Processes and threads
* Multithreaded programs: mutexes, semaphores, monitors and implementation
* Address translation between virtual memory to phyical memory
* Caching
* Demand paging: how/when do we swap memory from our RAM to our disk/SSD?
* I/O devices: how does the OS interact with I/O devices, disks and SSD?
* Filesystems

Alongside the voluminous content of this course, we completed three major labs this term. The labs guided us in building a very basic kernel in C responsible for process scheduling, memory management, inter-process communication and I/O handling. SE 350 labs are extremely time consuming and frequently caused frustration among groups. While the lab manuals and lab instructors were extremely helpful, many of the error messages and bugs that we faced were extremely difficult to understand, partially as a consequence of the low-level nature of the lab. SE 350 labs are to date the most strenuous labs I have done to date, but it was really useful in cementing class knowledge.

Overall, the course was on a medium-high level of difficulty. This course builds upon a lot of the concepts from ECE 222 and taught me a lot about kernels, which I had no knowledge prior to this term. Assesments require you to have a really good understanding of why certain tradeoffs were made in kernel development and an understanding of how to can code multithreaded programs without causing deadlocks. This was a very useful course for software engineers as kernels underpin much of modern software development.

Some tips for success in this course:

* **Plan and do labs early:** This is the most important tip in this course. The bugs that you will face in the labs are very difficult to detect and require time to solve. Our group usually spent an hour planning the lab, a week to actually finish the lab content and then allocated an entire week just to debug. This worked pretty well for us and prevented a lot of stressful late nights.
* **Brush up on memorization:** by the nature of the course content, students are expected to memorize a lot of facts. You will need to use your memorization skills extensively in course assessments
* **Take time to understand synchronization**: this will probably be the first time that students are introduced to multithreading and it can be difficult to understand. Much of the course assements require a good understanding of synchronization, so take your time!

Some example problems:

![[image (24).png]]

![[image (33).png]]

## CS 341: Algorithms

This course is a rigorous and proof-intensive exploration of several standard algorithmic paradigms that are extensively used in solving problems. It also goes into CS theory of NP-completeness. The following concepts are covered:

* Basic algorithmic analysis and computational models(quick repeat of CS 240 algorithmic analysis)
* Algorithmic paradigms
  * Reductions: how to turn one problem into another problem
  * Divide and conquer, recursion and Master's Theorem
  * Greedy algorithms
  * Dynamic programming
* Graph algorithms:
  * Traversals: BFS, DFS
  * Minimum spanning tree algorithms: Kruskal's and Prim's algorithms
  * Shortest path in a graph algorithms: Djikstra's, topological sorting, Bellman-Ford, Floyd-Warshall
* NP
  * Exact solutions via backtracking
  * Definition of NP completeness
  * NP complete problems
  * Undecidability

This was definitely my hardest course in 3A. This course is very much like CS 240 in that it is very theory and proof heavy. I never really liked proof-based courses so it was a slog to get through it. There were weekly assignments (much like my MATH 239 offering) offering some practice for the algorithms that we learned above.

Overall, this is a very useful course. Many of these algorithms are used in coding interviews and it gave a lot of recipes for solving typical problems that we encounter. The graph and NP algorithms were extremely interesting and I learned a lot about this field of algorithms. After doing this course and CS 240, I am far more confident in my abilities to tackle coding interviews.

My top tips for this course:

* **Pay attention to lecture proofs**: CS 341 expects that you prove algorithmic correctness, which requires specific proof techniques. These techniques are taught in lectures pretty well, so make sure to pay attention during those proofs!
* **Practice Leetcode**: the course unfortunately does not give a lot of practice problems. Not only does Leetcode have tons of problems, but many of the assignment and exam problems were variations of common Leetcode questions. Leetcode also teaches you certain tricks when solving problems (eg. binary search modifications, two pointer, etc.) that can be useful in assignment problems.
* **Brush up on CS 240 and MATH 239**: this course requires a good amount of knowledge from the algorithmic analysis section from 240 and the graph theory section from 239. Pay attention to the graph theory proofs that you used in 239; it may come in handy again.

Some example problems that I found in past exams in the engineering exam bank:

![[image (28).png]]

![[image (25).png]]

![[image (30).png]]

![[image (29).png]]

## SE 465: Software Testing and Quality Assurance

This course is our first SE-specific course. SE 465 teaches students how to properly test code and specific techniques in creating robust test suites. Topics covered include:

* Coverage
  * Code graph coverage
  * Data flow coverage
  * DFA coverage for compilers
  * State machine coverage
  * Logic coverage
* Proper testing practices
* Test input reduction techniques
* Testing the test suite via mutation testing
* Static testing and testing tools (mostly in Java)

This course was an extremely practical take on the topic of testing, with very little theory involved. While creating tests can be annoying, this course drills into you why testing is necessary. Besides lectures, there were 3 assignments and a larger project in Java. All the assignments and projects were extremely fair and didn't take much time to complete.

Overall, this was a decent course. I definitely learned a lot about testing, but I am not sure how often I will use this content as a SWE. At times, it felt more like a research course when we discuss state of the art techniques that aren't often used in industry. Regardless, it was interesting.

My only tip in this course is to use practice exams wisely. You can find several exams from the links that I have included in the resources section. This is a very straightforward course, even for students like me who don't have previous Java experience.

Some sample problems can be found below:

![[image (34).png]]

![[image (23) (1).png]]![[image (26) (1).png]]

## MATH 213: Signals, Systems and Differential Equations

This is an infamous course in the software engineering program due to its percieved difficulty. This course teaches us standard techniques for solving differential equations and how this can be applied to systems that take in continuous or discrete signals. Content that you will learn include:

* Introduction to homogenous, ordinary differential equations
* Methods of solving such equations: Ansatz method and Laplace transform method
* Analyzing signals and systems: stablity, causality, linearity, time invariance
* Finding the output signal of a linear and time-invariant system given an input signal
* Analysis of output signals via Bode plots
* Decomposition of signals into periodic, sinusoidal signals via Fourier transforms

I personally found this course really interesting. Differential equations are an elegant way to describe a wide variety of systems, including those that take in feedback. I personally have a lot of interest in system-based thinking and have encountered a lot of literature in the past regarding differential equations' applicability to real-life systems, so I had a great time in the course. I didn't find this course difficult, primarily because I was able to find plenty of practice for this course and self-taught a lot of the material.

Many of my peers didn't really like this course, which is a fair take. It doesn't have a lot of immediate applicability to software engineering, but I assume it will be quite useful in control theory, which is important in certain areas of software engineering. Differential equations are what controls autodriving in Tesla cars, help SpaceX boosters land,[ enable solar panels to follow the sun](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3355400/) and even [helped Shopify handle high write traffic](https://shopify.engineering/surviving-flashes-of-high-write-traffic-using-scriptable-load-balancers-part-ii). These applications were unfortunately lost on us in this offering of the course.

Some tips for success in this course:

* **Deliberately practice problems from the textbook/exams**: this course is primarily computation focused, which means that you don't need to be creative and crank out proofs like other math courses. If you can master the limited number of problem types and strategies, you will be able to quite well in this course
* **Self-study is required**: many of my upper-year friends have told me that this course is often taught poorly, and my term wasn't an exception. Fortunately, the content of this course isn't unique and can be found online. Take time to find high-yield material in the very beginning and you should be able to have a solid understanding.

Here are some sample problems:

![[image (31).png]]

![[image (35).png]]

## CS 349: User Interfaces

This course attempts to teach students about proper user interface design through the use of practical projects. Topics include:

* Basic user interface history up to GUIs
* Design models
* Layout and MVC patterns
* Graphics, transformations and animations
* Input devices and mobile UI
* Responsiveness and accessibility
* Android, JavaFX and Kotlin

This was probably my easiest course this semester. The content wasn't very difficult but it did require memorization in the exams. The content was applied in 4 assignments: 3 of them involved creating a desktop application using the JavaFX framework and 1 involved creating an Android application using Kotlin. This course taught me a lot about how user interfaces are supposed to be implemented and was quite practical.

While CS 349 was easy, I didn't like it very much. It didn't teach me many principles and instead focused far too much on design implementation. I didn't really learn how to appreciate good design in an application, which is a bummer. This was a course I was looking forward to, as I thought I would learn about how to design good interfaces; instead, I spent most of my time coding away without really caring too deeply about design principles. If you are taking this course thinking that you will be able to learn design best practices, this probably isn't the best course for you.

Tips for success in this course:

* **Start your assignments early**: CS 349 assignments can be quite chunky and there can be a lot of criteria to satisfy. Make sure to plan accordingly and start as early as you can to prevent last minute stress
* **Memorize course content as you go:** I didn't realize that the 349 exam would require so much memorization and it was somewhat annoying preparing for it. Make sure to keep memorizing as you go so you aren't crunching a bunch of facts at the very end.

I have no sample problems due to course policy.

## STAT 331: Applied Linear Models

STAT 331 is a course all about linear regression, one of the most used results from the field of statistics. Content includes:

* Simple linear regression
* Multiple linear regression
* ANOVA analysis
* General linear hypothesis
* Assumption and residual analysis
* Outliers and influential data points
* Building and evaluating linear models

This was another course in my journey to complete my statistics minor and is not mandatory for software engineering students. Regardless, this was my favourite course of this term. Our professor (Prof. Leilei Zeng) had extremely structured lectures with a great balance of application and theory. This course definitely leans harder into application, which is what I prefer.

I found this course to be an easier course than I expected. There was a bit of catch-up that I had to do to remember my linear algebra knowledge, but the course was well-paced and provided sample problems for practice.

My top tips for success in this course would be:

* **Brush up on linear algebra**: remember how to take determinants, how to take matrix inverses, how to multiply matrices and vectors together and basic proof structures in linear algebra. You don't need to take MATH 235 for this course (MATH 115 will serve you well), but brushing up on the content is recommended
* **Pay attention to proofs in lectures and the textbook**: certain proof problems can be solved through the same techniques. Pay attention to these common techniques and you should be fine in those types of questions in this course.

Here are some sample problems that I found in the MathSoc exam bank:

![[image (32).png]]

![[image (27) (1).png]]

# Extracurriculars

This term was definitely lighter in my extracurricular sphere. As a leader at both of my extracurricular commitments, my responsibilities have shifted from execution work to strategy and delegation.

As VP Product at UW Blueprint, I was guiding 7 projects in successfully launching products for non-profit organizations across Canada. My work mostly translated to running 1:1s to help diagnose product issues and guide PMs in making good decisions as well as running retros and socials. An additional responsibility that I picked up was leading our UW Blueprint website redesign. With the help of some of our most dedicated members at Blueprint, we managed to launch a completely new and modern version of the Blueprint website with a modern tech stack. We wanted to launch a new website to show our new directions as a club and modernize our website content management. The website should serve Blueprint well for a few years before another redesign is needed.

I was also the president for SE Society this term. With the help of 6 cohort reps and 3 other execs, we ran resume critiques, interview workshops, in-person socials, a mentorship program and more. One exciting part of this term was running an SE-wide annual survey. These surveys used to run under Prof. Patrick Lam, but was not taken up during his year-long sabattical. We got a lot of information and data and passed it up to SE admin in case they want to take action.

Overall, I really enjoyed the impact that I was able to bring to my two extracurriculars. I have to admit, seeing some of the other clubs in Waterloo makes me want to join more, but I don't want to repeat the same mistakes that I did in high school. Focusing on a few commitments and doing really well is better than being spread thin.

# Co-op

I was quite fortunate to have secured offers in Fall 2021 and early Winter 2022 and managed to avoid WaterlooWorks. As students get older, the value of WaterlooWorks starts to recede as we can start to get interviews and offers externally. I would highly encourage students to start applying externally as soon as they can. It requires preparation and being early (applications usually open the summer before the year of the internship), but it is well worth the effort. Due to my fall grind, I didn't have much stress over jobs this term.

I decided to return back to being a SWE for the next term. While I definitely meshed well with my PM role at Clearco, I wanted to get back to building and using my software skills (plus, external product internships are hard to come by due to the nature of the role). I am now more confused about what I truly want to do after university, as I am not sure if either SWE or PM is a perfect fit for me. Perhaps no role will ever be perfect for me. I may need to mold myself into these roles or change the role itself and find a unique skill combination that will lead to career success.

I will be a SWE at Twitch this summer delving into the world of distributed systems. I'm pretty excited as this will be my first in-person co-op experience in SF! I'm hoping to learn lots and meet some cool, smart people.

# Resources

Here is a list of resources that I found useful throughout 3A:

* **SE 350**: the [course website](https://ece.uwaterloo.ca/\~smzahedi/crs/se350/) and this [UC Berkeley exam bank](https://inst.eecs.berkeley.edu/\~cs162/su20/static/exams/) is all you need. I would definitely lean into using the course website and the past exams that are available.
* **CS 341**: I wasn't able to find a lot of problems from different universities that matched our rigour or content. CLRS (the standard algorithms textbook) and the course notes should be enough. I found a useful [guide](https://web.stanford.edu/class/archive/cs/cs161/cs161.1138/handouts/120%20Guide%20to%20Greedy%20Algorithms.pdf) on greedy algorithm proofs from Stanford as well.
* **SE 465**: Prof. Patrick Lam has uploaded a lot of his old course content which includes plenty of practice midterms and finals ([2015](https://github.com/patricklam/stqam-2015), [2017](https://github.com/patricklam/stqam-2017), [2019](https://github.com/patricklam/stqam-2019)). While Patrick did teach different content, there was a lot of overlap between our course and Patrick's offerings. I wish more professors did what Patrick had done; having these practice exam troves are incredibly useful for students
* **MATH 213**: If you want a solid understanding of differential equations, I would recommend going through the material from [this past offering](https://ece.uwaterloo.ca/\~math213/) of MATH 213. The material from this offering was extremely light on the systems and signals part of the course. Thus, I complemented this past material with the textbook (Systems and Signals by Oppenheim) and practice exams from [this UOttawa course](https://www.site.uottawa.ca/\~jpyao/courses/E3125\_Fall\_2021.html).
* **CS 349:** No extra resources are needed for this course
* **STAT 331**: The textbook from the course (Introduction to Regression Analysis by Bovas Abraham) had lots of practice problems, with some of them showing up in our assesments. The MathSoc exam bank also had a few practice exams that were quite useful for preparation.

As always, my notes for my 3A term can be found [here](https://github.com/aaronabraham311/Notes/tree/master/3A).
