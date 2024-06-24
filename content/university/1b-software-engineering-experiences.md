---
title: 1B Software Engineering Experiences
date: 2020-04-30
---
TLDR: 1B was better than 1A in almost every way!

There are 5 parts to this blog post. Feel free to skip through!

1. Academics
2. Extracurriculars
3. Co-op
4. Coronavirus
5. Resources

# Academics

Overall, I found academics in 1B more intellectually stimulating and challenging than 1A.  However,  it was easier to deal with academics and I was able to hone my study strategies during this period.

I quickly realized that my experience in 1B was very different than other SE students in my cohort. Many people complained about the excessive challenge of 1B and how conceptually difficult the courses were. When I perform some self-introspection on why I found 1B better in contrast to my peers, it comes down to the foundation I laid in 1A. Even though 1A was relatively light, I set a rigorous study schedule that served me well in 1B (that's not to say that my peers didn't; it just happened that my study schedule worked out for me in 1B). For any incoming first-years reading this, please take note: **establishing a firm and robust study system in 1A should be your top priority**.

Furthermore, I did a little bit of pre-reading over my winter break when I got bored. Browsing through Khan Academy, looking at my high school physics notes and doing some problems helped out!

Let's go through the coursework. Unlike my 1A post, I want to go into depth for each course and provide some sample questions so readers can understand what I went through.

## ECE 106: Electromagnetism

For most students in SE, this is the hardest course you will take in first year. Here's a quick overview of the concepts we learned:

* Multivariable integration; differential elements
* Coulomb's law
* Electric field and Gauss' Law
* Electric potential
* Capacitance
* Biot-Savart Law and Ampere's Law
* Faraday's Law and Lenz's Law
* Magnetic flux

Unlike 105, 106 is heavily dependent on calculus. In fact, you will cover most of MATH 119 in the very first week of 106!

This course was on the medium-difficulty scale for me. If you took AP Physics 2 or AP Physics C: EM, you have already seen most of these concepts before. The challenging part was modelling questions using calculus and accounting for unintuitive behaviors in the electromagnetic domain.

Unlike 105, 106 labs are much easier and straightforward. Its all based on computer simulations as well, which was pretty cool.

Here are some sample questions:

![[Screen Shot 2020-04-30 at 7.38.55 PM.png]]

![[Screen Shot 2020-04-30 at 7.39.57 PM.png]]

## ECE 124: Digital Circuits

For me, this was the hardest course: this wasn't because of the course material itself, but rather the instructional quality. There were several communication lapses which had a huge effect on class performance. This class taught me more about self-study techniques than digital electronics. In a twisted way, I saw this is as a benefit: learning how to learn by yourself is an extremely important skill in university.

Out of all the courses, this one is probably the most useful for hardware-oriented engineers. Here are some of the concepts that we learned:

* Combinational circuits
  * Logic gates: AND, NOT, OR, XOR, NAND, NOR, NXOR
  * Logic synthesis: truth tables, lookup tables, K-maps, sum-of-product, product of sums
  * Boolean algebra
  * Arithmetic operations
  * Mux
  * Decoders and encoders
* Sequential circuits
  * Timing diagrams
  * State machines
    * Moore
    * Mealy
  * Counters
  * Sequence detectors
* Asynchronous circuits (couldn't cover due to to corona

The assignments (which are not marked) are quite difficult and the labs were absolutely killer! Writing VHDL code with no prior experience was not a fun time: I have spent more than 6 hours cumulatively for one lab to code up a temperature control monitor for a house using an FPGA. Do not underestimate the labs.

Here are some sample problems from this course:

![[Screen Shot 2020-04-30 at 7.49.57 PM.png]]

![[Screen Shot 2020-04-30 at 7.50.36 PM.png]]

### ECE 140: Linear Circuits

This course teaches you everything about traditional circuits, including AC analysis. Here are some of the topics that we covered:

* Basic circuit analysis via Kirchoff's Laws
* Nodal and mesh analysis
* Circuit transformations
* Op-amp analysis
* Capacitors and inductors
* Transient analysis
* AC analysis and power

To be honest, this course should not be very difficult at all. It is very straightforward and the textbook does a wonderful job with practice problems and notes. Fortunately, the exams are modelled around the textbook and problems done in class, unlike the other ECE courses. This course ramps up in difficulty when you hit AC analysis: doing complex number calculations can be an absolute pain. Labs in this course were not bad either!

Again, here are some problems that are typical of ECE 140:

![[Screen Shot 2020-04-30 at 7.57.45 PM.png]]

![[Screen Shot 2020-04-30 at 7.58.14 PM.png]]

## MATH 119: Multivariable Calculus

For me, this was the easiest course that I had this term. Here were the concepts that we covered

* Multivariable differentiation and integration
  * Partial derivatives
  * Optimization
  * Integration (double integrals, triple integrals)
  * Coordinate systems (polar, spherical, change-of-variable)
* Series
  * Newton's Method
  * Taylor Series
  * Convergence Tests
  * Power Series
  * Big O

Unlike MATH 117, MATH 119's intensity on exams is much lower. With a solid understanding of the concepts, you should get by just fine. Furthermore, our multivariable calculus that we learned in ECE 106 helped make the first half of MATH 119 very simple. If you have done AP Calculus BC, the second half should be a review for you

Here are some sample problems:

![[Screen Shot 2020-04-30 at 8.03.52 PM.png]]

![[Screen Shot 2020-04-30 at 8.04.59 PM.png]]

Edit (Jul 2020): I am in co-op right now as a ML engineer. If you are interested in DS or ML, pay special attention to MATH 119! It's extremely important for this field.

## CS 138: Intro to Data Abstraction and Implementation

This was by far the most useful course for software engineers in 1B. This course taught us all the basic data structures that we were tested on in interviews. This course was taught in C++. Here's a brief glance of the things we learned

* Unix history
* Dynamic arrays
* Linked lists
* Stacks
* Queues
* Priority Queues
* Heaps (max-heap)
* Hash maps
* Object-oriented programming
  * Constructors and destructors
  * Virtual functions
  * Inheritance

Unlike CS 137, CS 138 assignments are not challenging; rather, its all implementation of specific data structures that have various constraints as given in the problem. Another difference is that testing your code is your responsibility: CS 137 public test cases usually covered all edge cases, while CS 138 public test cases will only test the main functionality of your solution.

Unfortunately, I can't provide any sample problems due to university policy.

## Review

I thoroughly enjoyed most of these courses. Asides from ECE 124, they were all taught quite well and had some interesting applications.

The question whether these courses are useful for SE students is a bit more complicated. Since most of our cohort are pursuing software jobs, all the ECE courses will have no applicability to our work lives. If anything, ECE 124 will be useful for firmware positions, which are abundant on WaterlooWorks

However, I do see a utility behind these courses: they are teaching us how to learn. If we view university as solely a place to get skills for jobs, there is no difference between a well-established university and a technical school. University courses should be intellectually challenging for the sake of challenge; this is what truly develops critical thinking and pushes students to the next level.

This is also the semester where students wonder whether SE is 'worth' it: they cannot bear hardware courses and would rather transfer to CS where they can pursue their passion for code. I have several arguments for and against this decision and I have my own opinion. I'll share that in another post

# Extracurriculars

Life was a whole lot better in 1B than 1A specifically due to extracurriculars. I made new friends and was using my time in a much more constructive fashion than 1A. Here were some of the highlights:

* [UW Blueprint](https://uwblueprint.org): met an awesome team of developers. Together, we developed a web app using GraphQL, PostgreSQL, Node, Express, React and Apollo to track patients during mass-casualty events (think St. Patty's day on Ezra) for Waterloo paramedics
  * Joining Blueprint was one of the best decisions I made this year. I learned an enormous amount about software development practices, different technologies, and working in a team in a software environment (this is where you will see Git's usefulness; please do not base off your Git knowledge from the SE 101 rocketship activity!).
  * The people on my team are awesome! Finding clubs that you enjoy is extermely important; this is how you find people with similar passions as you
  * As part of UW Blueprint, you're also solving social issues across Waterloo, which is a great cause!
* [UW PM](https://www.facebook.com/uwaterloopm/): UW PM is a club that focuses on introducing the world of product management to Waterloo students. While I have no PM experience, it was a fascinating experience to learn more about the PM lifestyle and its differences with software engineers. I specifcally worked on organizing a few events and running an article series, where we interviewed a whole bunch of PMs from organizations ranging from startups to Big N companies like Google and Microsoft
* UW SE Society: As a returning representative, I was mainly involved in organizing events, from exclusive resume critiques for SE students to a technical interview workshop for my cohort. I also took on a neat intiative called Sessions by SE, which is a podcast series to bridge the gap between first-years and upper-year wisdom. You can check it out [here](https://aaronabraham311.gitbook.io/aaron-s-thoughts/projects/connecting-first-years-with-upper-year-wisdom-sessions-by-se).
* Phoenix Data Consulting: check it out [here](https://aaronabraham311.gitbook.io/aaron-s-thoughts/projects/phoenix-data-science).

I strongly believe that university is not just about getting the best grades or the Cali co-op: it's about developing soft skills and experiencing new things. Extracurriculars are a great way to do both of that. Unfortunately, many first years usually don't see the utility in extracurriculars. Hopefully we can change that.

# Co-op

I have already spoken most of my thoughts [[securing-the-first-tech-internship|here]] but I do want to elaborate on my story.

First of all, I was targeting a data science co-op: I absolutely love the field (in fact, I will be pursuing a Statistics minor as a way to pursue this passion) and I think it has great potential. I specifically applied to the data science jobs on WaterlooWorks and went from there.

I was extremely lucky to have past work experience, so getting interviews was not too difficult for me. Performance during the interviews was also decent given that most questions were behavioural.

I will be working as a Machine Learning Engineer intern at PerkinElmer, a Fortune 500 biotechnology firm involved in diagnostics. It was weird that I would be eventually working a company that was instrumental in my metabolomics research in high school. It was a perfect fit!

If I were to go back and redo approach to co-op, here's what I would change

* **More aggresive external recruitment**: I would have started much earlier in October and November and talked to recruiters. To be very honest, the pickings on WaterlooWorks are not as great as I thought it was (I had extremely high standards). One of my friends actually got Google as his very first co-op by reaching out externally. This is a good lesson for the future
* **Brush up on SQL queries**: for one of my data science interviews, I was pranked with a query question, when I was expecting a Leetcode question. Don't be me and learn how to do joins and merges using SQL
* **Rigorously practice Leetcode**: Having a comfortable knowledge of algorithms like dynamic programming and backtracking combined with your CS 138 data structures knowledge will be extremely helpful. However, don't wait for someone to teach you data structures and algorithms, go learn it by yourself from CLRS or YouTube.

# Coronavirus

This was the most unexpected way to finish off first year. I remember joking around how there was a virus named after a beer running around in China in January; fast-forward to March and I was packing up my bags and heading back to Calgary.

The transition to school life at home was a little difficult at first. Concentrating on magnetic flux problems while your younger brother runs around is no easy feat. I definintely lost a lot of my focus when I came back to Calgary but I don't regret it. It was great opportunity to relax and sit down with the family and enjoy some amazing Indian food.

After a week of nonproductive activities, I quickly ramped up back to normal studying schedules. Weirdly enough, I found that self-studying (minus the distractions) was much better than listening to in-class lectures. I could move at my own pace and focus on my own weaknesses. This has influenced how I will approach academics in Fall 2020, as this period has really refined my self-learning abilities.

MATH 119 and CS 138 had no final assesments. ECE 106 and 124 had finals, while 140 had weekly quizzes. All in all, I believe it was an extremely fair way to account for this bizarre situation.

Unfortunately, coronavirus led to high unemployment across my cohort: as I speak, the employment rate is 56%. Usually at this time in the year, SE 1B students enjoy employment rates in the 90s.

Coronavirus either brought out the best of us or the worst of us. I viewed it as a time to learn new skills, get more involved in projects, and do well in my coursework. It was certainly a change from normal school life and an anticlimatic way to finish off 1st year.

# Resources

Here are some resources/tips to help you specifically in SE coursework

1. ECE 106: This course is almost a carbon copy of MIT 8.02: many of the examples we covered in class could be found in freely published notes. Take a look at [these notes](https://web.mit.edu/8.02t/www/802TEAL3D/visualizations/coursenotes/index.htm); it offers a firm foundation for 106. Take a look at past finals posted by the instructor (can also be found on EngSoc's exam bank)
2. MATH 119: The textbook is all you need along with past finals posted by the instructor.
3. ECE 140: The textbook is all you need. I extensively used EngSoc's exam bank for this
4. CS 138: The slides are all you need. Unfortunately, there is no video repository like CS 137, so you will have to wait until the slides are available. For the midterm, there is a large component of the exam that is trivia based. I made a [Quizlet](https://quizlet.com/487474114/cs-138-flash-cards/) to help cover these questions.
5. ECE 124: [Neso Academy](https://www.youtube.com/watch?v=M0mx8S05v60\&list=PLBlnK6fEyqRjMH3mWf6kwqiTbT798eAOm) is a good resource if you have any conceptual misunderstandings. For more basic practice problems, India's GATE exams (look for Digital Electronics past papers) are a terrific resource as well. The textbook from Kennings was extremely useful as well, but it had a few mistakes.

You can check out my class notes on my GitHub repository [here](https://github.com/aaronabraham311/Notes).

I hope you enjoyed my analysis on 1B SE and that hopefully some of this will be useful for the reader.
