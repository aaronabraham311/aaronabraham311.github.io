---
title: "Software Engineering Interview Advice: From The Other Side"
draft: false
date: 2025-10-15
tags:
  - career
---
As part of my increased responsibilities as a full-time engineer, I have been asked to interview candidates, which has been an eye-opening experience. It gave me a much better understanding of what an ideal interview should look like. After seeing the same mistakes being made by engineers of all levels, I thought a small guide would be helpful for anyone who chances on this.
# Structure your interview like an essay
The purpose of an interview is to ensure that candidates have the qualities to succeed at their position. The ability to take an ambiguous problem, define requirements and work through components of the problem while communicating clearly is the essence of being a software engineer and that is what most interviews are testing for. Top candidates understand what they are being tested for and change the way they interview. To them, interviews are not tests; they are a way to communicate your thought process and work with a fellow engineer on a problem. Demonstrating problem solving capabilities and communication is the most important thing in the interview, not whether you get the most optimal solution that solves every single edge case in the very first try.

The number one tell that a candidate has a clear thinking process is when they communicate a disciplined approach to breaking down the problem into components. Top candidates often follow this script:
1. Read the problem
2. Rephrase the problem in your own words
3. Clarify all requirements: pepper the interviewer with as many questions as possible, making sure to understand both the functional and non-functional requirements
4. Go through possible approaches at the problem
	1. Break down the problem into component parts if needed and solve each component one by one
	2. Write some basic pseudocode or make basic diagrams
	3. Agree with the interviewer which approach is the best
5. Implement the approach
6. Test the approach
7. Be ready to answer follow-up questions

This structure has a few benefits:
1. **The candidate is able to derisk their solution ahead of time**: by extracting requirements, breaking down the problem and writing pseudocode, candidates waste very little time making sure their proposed solution actually solves the problem
2. **The interviewer is able to follow the candidate**: many candidates often ramble on their approach or jump straight into the problem. Both of these approaches often confuse the interviewer and prevents the interviewer from helping the candidate get out of tricky assumptions.
The most important parts of this script is steps 3 and 4, and top candidates spend the most amount of time on these steps. It's this part that demonstrates whether the candidate has a good mental model of the problem, while the latter parts are more of a test of execution abilities that most candidates already have.

As someone with a debate and public speaking background, one tip that seriously elevates your interview experience is signposting. This is when you explicitly call out your structure in your interview and note to the interviewer where you are in your thought process. As an example:
```
Interviewer: <gives problem>

Candidate: Thanks. I am going to approach this problem by first reading through this problem in my own words, then clarifying requirements. After that, I'll work through a few sample approaches via pseudocode. Once we decide on one approach, I'll go ahead and implement and test it. How does that sound?

Interviewer: Sounds good!

Candidate: Ok, let me first read through the problem. 
...
Candidate: Great, read through the problem. Now let me go through a few requirements.
...
Candidate: So I read through the problem and I got a list of requirements. Let me think of a few approaches and get back to you.
...
Candidate: I thought of three approaches. I am going to write up some pseudocode to demonstrate what I am thinking about and then I am going to choose one and implement it.
...
```
In this script, there are few notable things:
- Signposting helps the interviewer understand where they are in the interview and they can remember specific points much easier. Rambling through the problem is not a gift for anyone's memory
- The candidate is driving the interview with this structure. They can lean on it to move forward, which implicitly shows their ability to own and solve a problem.
Signposting is heavily used in public speech as it helps audiences understand a speech better. The brain handles structure really well, so continuously reinforcing that structure is a huge tactical gain for your interview.
## Communicate during your interview
When interviewers say "I am looking for good communication", there's two components:
1. (most important) Can you structure your overall thought process?
2. Can you speak through your code?
The first point is handled above. The second point is a bit trickier. I know its challenging for individuals to talk while they are coding. My advice here is you don't need to be constantly jabbering away while writing. I usually would just take small pauses during execution and briefly explain what I am doing. Here's a sample script:
```
Candidate: Let's get on with implementation. First, I am going to create a dataclass to store this data in a structured form.
...
Candidate: Cool, got the dataclass done. Now, let me write a small script to parse the data into the dataclass.
...
Candidate: Awesome. Let's now get the algorithm working. As I mentioned earlier, I need to set up some sort of priority queue. Let's get that algorithm working.
...
```
This gives the candidate a bit of time to actually think through what they are building and allows singular focus on execution rather than trying to balance both thinking aloud and coding.
# Get something working 
The worst candidates in my opinion are ones that think of a complex solution but are not able to get it working in time. They often go with more complex approaches to common problems, like immediately implementing binary search. I often coax people into choosing the simplest solution first, getting it working, and then iterating on the solution to get it more optimal.

This is akin to how coding works on the job. When we are given a problem, we are looking for an 80/20 solution, one that is simple enough to give us the most results for the least amount of effort. Once we have shipped out the first version, we can get feedback and iterate further. Speed of implementation is crucial on the job as it helps the company verify assumptions with actual customer feedback; spending time developing the most complex and optimal algorithm is not bringing value to others. Similarly in an interview, aim for a quick solution that can help you get to testing assumptions faster.
# Test early, test often, debug like a detective
One of the worst situations I have encountered is when a candidate completes their entire interview but made a critical error in the earlier parts of their interview that forces a rethink of their entire code. Senior engineers that I have interviewed always make sure to test every single component of their solution as they build it out to avoid making this mistake. For example, if they implemented an interesting way of traversing a list, they make sure that the traversal works first before moving on to the rest of the problem. By nipping problems in the bud, you avoid bad assumptions from leaking through the rest of your code and causing extremely difficult refactors.

Inevitably, your solution may have bugs. Your debug process is a window into your problem-solving abilities, so I would make sure you spend time practicing debugging. Like I mentioned before, having a structured approach is crucial; with debugging, that often comes down to using a hypothesis-driven approach. It comes down to the following structure:

1. **Set up test cases post implementation**: to make sure your implementation is correct, top candidates spend time being exhaustive with their test cases, making sure to cover any edge cases
2. **On getting a bug, set up a minimal repro example**: Setting up a test case with a minimal example that triggers the bug is essential to avoid distracting you from other issues
3. **Instrument your code**: Reasoning through code lines is not going to help you understand why your bug is happening, especially if its a logic error and its nontrivial. What I would usually do is set up a debug flag variable that you can turn on. Print statements would then be activated on an activated debug flag.
4. **Reason through your data to arrive at a conclusion**: This is where your problem solving abilities need to kick in to reason through why your data plus your logic leads to an incorrect solution
5. **Make the change and make your test case pass**

Some notes about the above:
- There is a structure in place, guiding the candidate to get to a solution faster and in a more logical way. Junior engineers often come up with a bunch of different hypotheses without every confirming what actually is wrong with the code they wrote. This wastes time
- This structure is exactly like how an engineer at work solves a bug. The most important step is creating a minimal repro example and then methodically stepping through code to figure out what is actually causing the issue. Emulating real-world debugging is important in an interview
- Debugging takes up a significant amount of an engineer's bandwidth. Demonstrating your savviness at this part will give you brownie points with your interviewer, guaranteed.
# Conclusion
Any person reading through this post will realize that what I am pushing for with interviews is exactly like how features are developed at real companies. When an engineer is building out a feature, they don't immediately hop into implementation, go for the most complex and optimal solution or ship out untested code. They spend the time cooking up a plan, going for an 80/20 approach with their implementation and setting up a variety of test cases to catch edge cases. Emulating the communication, implementation and debugging habits of a working engineer in your interview will have a step-level impact on your ability to pass an interview.