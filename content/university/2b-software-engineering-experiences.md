---
title: 2B Software Engineering Experiences
date: 2021-08-22
---
"2B or not 2B, that is the question" - SE upper years. Coming into this term, I had no idea what I was getting myself into. The majority of upper years believe that 2B is the toughest term of SE. Comparing this term to all previous terms, I have to agree.

I will split up this review into the following sections:

1. Academics
2. Extracurriculars
3. Co-op
4. Resources

# Academics

I found that this term was by far the most difficult term that I have done to date. 1B physics courses pale in comparison to 2B CS and math courses. While some of the difficulty could be attributed to my own choices (eg. taking on a difficult stats course, taking on some extracurricular commitments), most of my peers tend to agree with me when we say 2B is a very tough term. After thinking about this issue, I believe there are some reasons why 2B is so difficult:

* **Huge workload**: For some reason, courses this term tended to give out far more assessments than previous courses. For example, certain courses had 3 major tests, weekly assignments and more. What made this even worse was that all of these assessments were weighted the same, so a student cannot sacrifice anything if they want to achieve a decent mark. Combining this with a lack of a reading week, this quickly spiralled into non-stop work throughout the term. I would recommend students to seek easier electives and try to lessen their workload outside of school during 2B.
* **Theoretical courses**: I found that many course offerings this term were far too theoretical, which I tend to despise. This was also our first introduction to more formal CS classes, where algorithmic proofs are markedly different than previous CS course experiences. I found that several parts of these classes were harder to relate to real-life industry experiences and wasn't entirely sure why we were even learning the content presented. Seeing how CS courses taught by the Faculty of Mathematics are run, I am now more firmly on the side that SE is a better fit for me than CS.
* **Novelty**: the course that gave most students difficulty was MATH 239, which is all about combinatorics and graph theory. Since high school barely scratches the surface of combinatorics, the vast majority of this course was quite new to most students, which obviously contributed to it's difficulty. As mentioned before, this was also our first time writing CS proofs, which made CS 240 and CS 348 more difficult as well.

Despite the difficulty of the term, some parts of some courses were highly useful for interview prep and general engineering know-how. The tough part was working through the more tedious portions of the term and sticking it out for the useful moments of courses.

Let's dive into each course:

## CS 240: Data Structures and Data Management

This course gives students a crash course on the major data structures that software engineers must work with on a daily basis. This is a far more in-depth look at data structures  compared to CS 138 and is more theoretical, as a large portion of this course is reserved to proving certain data structures will have certain runtimes on different input.

Here is a general overview of the concepts you will learn in this course:

* Asymptotic analysis: how do you write big O proofs? How do you analyze an algorithm?
* Heaps and priority queues
* Sorting: comparison-based sorting (specifically quick sort) and non-comparison-based sorting
* Comparison-based dictionaries: AVL trees and skip lists
* Non-comparison-based dictionaries: tries, hash-maps
* Performing range searching on dictionaries via quad-trees, kd-trees and range-trees
* String matching algorithms: Knuth-Morris, KMP, Boyer-Moore, suffix trees
* Compression algorithms: Huffman encoding, run length encoding, LZW, various transforms
* External memory model and algorithms: d-way merge sort, (a,b)-trees and B-trees

Other students like to call this course Leetcode 101 but I would push back on that definition. While this course is certainly useful for interview prep given that it goes over almost all major data structures, it doesn't teach us many of the common algorithms that are widely used in Leetcode problems (eg. graph algorithms, dynamic programming). Furthermore, many of the concepts that were taught have a very low likelihood coming up in an interview question (eg. AVL trees, compression, range searching). Perhaps a more accurate label would be Leetcode 101 Part 1 (with CS 341 finishing it up).

During the S21 offering of this course, we had around 5 assignments, 3 programming assesments (C++), 4 quizzes, a midterm and a final exam. The vast majority of questions often required students to take existing data structures and change them in some manner, either in terms of the input data the structure is storing or using them in an non-obvious algorithm. Having a thorough understanding of the intricacies of each data structure in this couse is incredibly important to do well in the course.

I found that this course was at a medium difficulty for me. Much of the algorithmic analysis portions were quite new and required intuition that took a lot of time and practice. Given the nature of this course, practice problems were often hard to come by, so there was a limited amount of materials that a student could use to develop that intuition. However, the course content was presented in a great manner and instructional staff were always willing to help.

Some tips for success in this course:

* **Be extremely thorough in every single data structure**: when should a data structure be used? When should it not be used? What are the best/worse/expected run times? Having a strong baseline understanding of all presented data structures will give you a significant boost when facing non-trivial assesment questions
* **Understand proof techniques**: I find big O proofs quite challenging as there are several strategies that the course possibly cannot cover. The professors overcame this challenge by introducing these strategies as they proved the runtime of each data structure in lectures and tutorials. Pay special attention to these proofs. These tidbits were quite useful when I was solving assesment questions
* **Ask lots of questions**: this course continually builds off previous knowledge. Having a hole in your foundation will be catastrophic as you move later through the course.

Here are some sample questions that we used in our midterm/final practice:

![[image (4) (1) (1).png]]

![[image (5) (1).png]]

![[image (6).png]]

## MATH 239: Introduction to Combinatorics

MATH 239 is a rigorous introduction to two major fields of math: combinatorics (how to count objects) and graph theory. This course will teach you how to construct combinatorial proofs and how to analyze various aspects of graphs. As such, this is a proof-based math course, very similar to how MATH 135 is run.

Here is a general overview of concepts in MATH 239:

* Combinatorics:
  * Combinatorial proofs (bijective proofs and double counting)
  * Generating series and compositions
  * Binary strings and recursive strings
  * Recurrence relations
* Graph theory
  * Basics of graphs (degrees, components, connectedness, cycles, Eulerian circuits)
  * Trees and spanning trees
  * Planar graphs
  * Matchings and covers

This was by far the hardest course that I have taken so far in my undergraduate degree. Since high school, I have had lots of difficulty in this field of math and this compounded to create some real problems for me this term. Throughout the majority of this course, I found that one needed to have a really solid intuition on how to construct combinatorial and graph proofs, which is quite difficult when the majority of the content is new. There was plenty of practice problems given to train this intuition, but we never got any answers to practice problems. This meant that our class had to rely on each other to provide solutions. This isn't necessarily bad, but we weren't ever sure whether our proofs used the correct methodology. To add on, course assesments were quite difficult not only due to content but also due to strict time constraints which made rigorous proof writing difficult.

Overall, I did not like this course. Granted, the beginning of graph theory was quite useful in understanding how to solve graph problems in algorithmic interviews (I had two graph theory interview problems this term, which was my first time ever doing graph coding problems) and recurrence relations were useful in developing a mindset necessary to solve recursive/DP problems, but the course felt far too theoretical and ultimately useless for engineering students. Perhaps my initial difficulty in combinatorics in high school has biased me too much against this branch of mathematics.

Some practical tips for success in this course:

* **Review pre-midterm content for MATH 135:** if you are unsure about how to write proper  rigorous proofs, I recommend brushing up on proof writing that you practiced in MATH 135, up to and including induction.
* **Practice class proofs**: This is a proof-based course, so spamming practice problems is not always the best use of time if you don't understand the basics of how proofs work. I encourage students to find the common proof patterns (eg. basic generating series strategies, removing and adding edges, longest path, induction, how to construct partitions) presented in class lectures and figure out when to apply those patterns. Recognizing these patterns are crucial if you want to succeed in timed assesments.
* **Attend tutorials**: in the online offering of this course, tutorials were the only major way for students to interact with professors and understand different proof techniques. I found them quite useful when preparing for major assesments.

Here are some sample problems that you can expect in this course:

![[image (8).png]]

![[image (9).png]]

## CS 247: Principles of Software Engineering

This course gives a great overview of object-oriented design and best practices in C++ development. This is probably the most useful course that I have taken so far. Major concepts students learn include:

* Special member functions of classes
* Modularization and Makefiles
* Error handling in C++
* Design patterns: Singleton, Template, Command, Strategy, Composition, Facade,... (too many design patterns to name)
* UML diagrams
* Refactoring and code smells
* STL containers and algorithms
* C++ functors and lambdas

This course is packed with useful programming information that is language-agnostic (eg. design patterns, how to collaborate in a codebase effectively). In this offering of the course, we had 5 assignments and 2 projects. Our last project involved making a variant of Tetris; while it was tedious and at times difficult, it was a great practice of our coding skills. This course was one of my favorites this term.

However, I found that this course was quite disorganized. Lectures were often pulled up to account for assignments, which sometimes meant studying 3-4 units a week. There was a great amount of ambiguity in assignment specifications as well, but fortunately the ISAs usually clarified it in a timely manner. My biggest gripe of this course was the amount of content that we learned. At times, I felt that we learned far too much and we didn't really have a deep understanding of all the topics. Some of the content that we learned could have been easily pushed into CS 138, leaving us more room to actually understand the lectures.

Some tips for success in this course:

* **Start assignments early**: some of the assignments can be quite tedious and might require a lot of thought and debugging. I remember one assignment taking almost 2 days to debug due to all the memory leaks that I had. Many of my peers tried pushing assignments to the last minute, which never fared well. As I mention in every term review, always start your assignments early to give yourself buffer room in case things go awry
* **Understand UML diagrams really well**: if you understand UML diagrams, a good majority of the course will be quite easy for you. This is probably the keystone concept of the course

I have no sample problems due to university policy
## CS 348: Introduction to Databases

This course introduces students to databases and data management. This is somewhat useful for backend and infra developers who regularly interact with databases. Content one can expect to learn include:

* Mathematical foundations of databases: relational calculus and relational algebra
* SQL queries and embedded SQL
* Database design and normalization theory
* Concurrency and transaction management
* Physical and logical design optimizations

This is one of the easier courses of 2B. If you have written SQL in the past or have worked in data engineering, much of these concepts will be easily digestible. However, I found this course to be extremely dry. Many of the concepts taught seemed far too theoretical compared to actual implementation. For example, we learned about different mathematical methodologies to normalize databases but no one really does this in industry. This course has some serious potential given the rise of data engineering and new data technologies (eg. NoSQL), but the slides and content haven't been updated in years (eg. we used IBM DB2, which is super outdated and no one uses this in industry). We also got audio recordings of lectures, which made this course even worse and I ultimately resorted to just reading slides. To be quite honest, I was disappointed in this course.

Some tips for success:

* **Learn SQL**: if you haven't already, just learn it. It will not only make this course easier, but  it is widely used in industry
* **Read the textbook**: the textbook clarified a lot of the verbose explanations in the slides.
* **Read through predicate logic and set theory from SE 212**: CS 348 sometimes gave us proof problems (I was quite suprised that there were even things to prove in the first place), but SE 212 gives a great foundation. Re-reading those notes would be somewhat useful.

Here are some sample problems from the textbook:

![[image (10) (1).png]]

![[image (11).png]]

## ECE 192: Engineering Economics

This half-credit course teaches students about cash flow analysis and comparing different engineering projects based solely on its net present/annual/future worth. This course is only in the SE curriculum to satisfy Canadian engineering requirements.

Concepts learned include:

* Cash flow analysis
* Comparison of different projects via discounted cash flows
* Depreciation
* Handling risk in projects

To me, this was the easiest course of 2B. Does this have much utility for software engineers? Somewhat. I have never seen cash flow analysis of different software technologies to date, but this might be somewhat relevant for senior engineers who make design decisions. Note that this isn't really an economics course; it's more of an accounting course. If you were interested in learning about supply and demand and other foundational concepts in economics, this is not the course for you.

However, this course is actually quite useful for personal finance. I have taken some time to read about value investing, where one invests in undervalued companies on the market, Warren Buffet style. Much of the concepts that we learn in ECE 192 is useful for this type of investing. To future students, don't completely throw away this course; use this to learn more about personal finance.

Some tips for success:

* **Learn basic Excel**: everyone should know how to work in Excel. It is super simple and will take you no more than 30 minutes to learn the basics of formulas, which is akin to programming.
* **Practice tutorial problems**: the tutorial problems are extremely similar to actual exam problems and solutions often introduce techniques to speed up problem solving.

Some sample problems:

![[image (12).png]]

![[image (13) (1).png]]

## STAT 330: Mathematical Statistics

This is a course that I took to satisfy my statistics minor requirements. STAT 330 teaches students all about the mathematical underpinnings of several statistical methods and extend analysis to multiple random variables (which are far more common in practice).

Concepts a student can expect to learn include:

* Multivariate random variable analysis: variance, expectation, joint PDFs/PMFs, moment generating functions, independence, conditional distributions and more. Basically all statistical analysis of single variables is extended to multiple variables.
* New distributions: Gamma, Bivariate Normal, Multinomial
* Transforming random variables: CDF technique, MGF technique, 1-1 transformation
* Special transformations on a Normal variable
* Limiting and asymptotic distributions
* Limit theorems: Markov's Inequality, Chebyshev's Inequality, Continuous Mapping Theorem, Slutsky's Theorem, Delta Method
* Central limit theorem
* Point estimation via method of moments and maximum likelihood functions

This was by far my favourite course of 2B, which is suprising given that a vast majority of the content was theoretical. I had a great professor (Prof. Lucy Gao) who organized this course extremely well and often related theoretical concepts to applied statistical concepts. That being said, this is not an easy course. STAT 330 requires a lot of previous calculus knowledge and is not intuitive. This was also my first time writing statistical proofs, which can be slightly tricky at times.

Some of the academic advisors warned me that this course would be tough since I skipped STAT 230 and 231 using STAT 206. I would push back on this. STAT 206 gave an excellent foundation for STAT 330. For students in software engineering looking to pursue a statistics minor, I really don't think it is necessary to do STAT 230 and STAT 231 unless you want to take your time learning foundational statistics. Personally, I don't think it would have helped me at all since I used the STAT 230 and 231 textbooks heavily when I was in STAT 206. Since STAT 206 covers 80% of the content in 230 and 231, students should be fine.

Some tips for success in this course:

* **Practice, practice, practice**: STAT 330 is filled with a lot of unintuitive theory, so practice is crucial for doing well in this course. Unlike MATH 239, this course actually provides answers to practice problems and textbook problems (thank goodness)
* **Focus on strategies**: While there are a lot of theorems, solving STAT 330 problems requires only a few strategies. If you can nail these strategies, you will do quite well as all problems will come down to unique applications of these strategies. For example, any problem with limiting distributions requires some usage of either continous mapping theorem or Slutsky's theorem, and then requires some random variable transformation, usually involving the central limit theorem. Practicting this strategy over and over again is a surefire path to success.
* **Take your time to digest proofs**: The proofs presented in this class also incorporate a lot of useful problem strategies. Make sure you understand how to derive each line in every proof; you will be golden if you can do this.
* **Review your MATH 237 and STAT 206/230/231 notes**: there is quite a bit of calculus compared to STAT 230/231/206, so be sure to review multivariate integration and partial derivatives. Furthermore, the beginning of this course is really an extension of previous statistics courses, so make sure you remember the majority of STAT 206 or STAT 230/231.

Some sample problems:

![[image (14) (1).png]]

![[image (15).png]]

# Extracurriculars

I was involved in three extracurriculars this term:

**UW Blueprint**: Since January 2021, I was a PM on the Distress Centre Calgary team. We were building a Figma-like software for users to create their own virtual escape rooms; this software would be distributed to non-profits who are looking to build highly engaging and interactive experiences to teach students about various topics. When I first started, this project was extremely ambiguous: we barely did any technical research, didn't have a solid idea on what users wanted and severely underestimated the amount of design work needed. This was exactly the project that I wanted to work on. Slowly but surely, we managed to create a plan and execute. We discovered the world of 3D design, Blender and WebVR technologies like A-frame. By the end of this term, we not only had a fully functional Figma-like editor for creating escape rooms, but we also built our own room designed to teach students about mental health, which we iterated through many times as we tested it with users. This was a taxing role and required a lot of time and investment, but it was fully worth it. I learned an incredible amount about product management, leadership and working in the grey, while also utilizing my technical skills to assist in system design and some coding sprints. Here are a few screenshots of the escape room we built:

![[image (18).png]]

![[image (20).png]]

As this project is an FYDP project, we are handing it off to the team in August 2021 for final touches and launching the software with a mental health organization in Calgary.

Next term, I will be taking on the VP Product role for Blueprint, where I hope to improve product processes at Blueprint and continue to strengthen the PM role.

**SE Society**: this term, I was elected as a class representative as well as President for SE Soc starting in Winter 2022. Due to the heavy workload of 2B combined with the intensity of Blueprint, I wasn't able to do much as a class representative as most of us were quite busy. However, I have spent some time planning on what SE Soc could improve on as I take on the presidency in the upcoming winter.

**Concept**: Concept is a student entrepreneurship incubator at UWaterloo. Due to my interest in entrepreneurship, I wanted to help out Concept in improving their student offerings. This was about a 2hr/week commitment where I watched intro sessions where Concept introduced entrepreneurship concepts to students as well as writing up feedback and timestamps for Concept. At the end, I gave a list of recommendations that Concept could use to improve their student offerings based off my own experiences and some of the intro sessions. Overall, it was an interesting experience as I dove further into the entrepreneurship ecosystem in Waterloo.

# Co-op

This co-op season was a whirlwind of activity. I applied for more external roles than usual because I wanted to avoid WaterlooWorks shenanigans and also wanted to secure a job before school hit me a truck. While I was able to go through several external processes and landed a couple of offers, there was no way I could realistically get a job before school started. A few of my friends were able to do so since they applied for fall positions way back in February or March 2021, but I wasn't as forward-thinking during that time. Given the heavy nature of 2B, I advise future SE students to try their hardest to secure jobs before the term starts so that you have more time to spend towards building foundational knowledge in your courses.

Deciding between my external offers was a little difficult due to conflicting opinions on brand , pay, roles and more but I decided to choose a place that was doing some incredibly interesting things and is growing extremely quickly. I will be joining Clearco as a PM intern on their Core/CX pod, where I will be working with PMs, engineers, designers and other cross-functional partners to improve Clearco's core product offering and customer experience for thousands of entrpreneurs around the world. I decided to join Clearco due to their hypergrowth rocket trajectory (as opposed to big companies where interns are shielded from growth; further reasoning can be found [here](https://breakoutlist.com/why/)), my personal interest in entrepreneurship and my career plans. The story of how I landed this internship is somewhat interesting, but I will save it for another post.

Throughout the entire term, I was applying for positions for Summer 2022. Yes, you heard that right: if you want to get a job externally (which I would highly recommend), job searching usually starts an entire year early. As OAs and interviews started streaming in through July and August, it became slightly overwhelming when trying to balance my studies and extracurriculars with interviews. Job searching intensified as August came around, just as finals started. Although this is a less-than-ideal situation, it is one of those scenarios that students just need to accept and grind. Please make sure you take care of yourself and take appropriate breaks during 2B; without breaks, the term will quickly become miserable.

# Resources

As always, I have a list of resources that I found useful when I was going through 2B:

* **CS 240**: The CS 240 textbook is pretty good, but it is quite dense. Some instructors like to pick small details in the textbook during quizzes, so I recommend skimming through chapters before assesments. I supplemented my studying with [Abdul Bari's YouTube channel](https://www.youtube.com/channel/UCZCFT11CWBi3MHNlGf019nw) (which is an absolute gem of a channel) and course notes from [MIT 6.046J](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-046j-introduction-to-algorithms-sma-5503-fall-2005/index.htm) (really useful in its discussion of skip lists, algorithmic analysis and external memory algorithms)
* **STAT 330**: students can probably get by just fine with the course textbook and practice problems. [Penn State's STAT 414](https://online.stat.psu.edu/stat414/lesson/introduction-stat-414) was also a very useful resource when I wanted to understand certain proof techniques.
* **MATH 239**: The textbook was semi-useful, but the lack of answers was a huge bummer. Online resources also varied drastically in quality. One resource that was somewhat useful was this [YouTube series](https://www.youtube.com/watch?v=RBhqV0ZXYi0), although it didn't go into much depth with proof techniques. Some students have made their own course notes (which were actually super useful in understanding proof techniques and at times better than the textbook). I've linked the 2 that I used the most below:
  * [Gabriel Wong](https://www.gabrielwong.net/notes/math239\_notes.pdf)
  * [Richard Wu](https://www.richardwu.ca/notes/math239-notes.pdf)
* **CS 348**: The textbook is pretty useful and the only resource you need. Fortunately, the authors put up a vast majority of practice problem solutions [here](https://www.db-book.com/db7/Practice-Exercises/index-solu.html)
* **ECE 192**: lectures and tutorials are all you really need
* **CS 247**: lectures and tutorials are all you really need

Notes from my 2B term can be found [here](https://github.com/aaronabraham311/Notes/tree/master/2B).
