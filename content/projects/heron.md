---
title: "Heron: Lessons From Building A Vibe-Coded Personal Project In 8 Hours"
date: 2025-06-13
tags:
  - technical
---
# What is Heron?
My interest in the stock markets was triggered in Grade 8 when I signed up for a personal finance class as an elective course. The teacher set up a semester-long stock picking contest to help motivate our initial forays into stock markets. My dad, a stock market aficionado, taught me the basic rules of evaluating companies, technical patterns to watch out for and the importance of compounding.

One of the core rules that I learned from him is patience in stocks. Never buy when the price is high; wait when it comes to a level you're OK with buying. However, this necessarily meant that I would have to continuously check interesting stocks and hit the buy button when it hit my target price level, or I would have to set a long-running limit order. I wasn't very comfortable with either option.

Recently, I have been wanting to allocate some more capital to individual stocks and this problem was really plaguing me. I decided to make a tool for myself to check a stock list every day and send me an email alert when a stock is within my buy range.

There were a couple principles that I followed when building this project:
1. **This is a personal project**: In my opinion, this is not a hair-on-fire problem that would be worth shipping to other users. It was an annoying itch I wanted to scratch for myself. This helped significantly simplify my project.
2. **I wanted to ship this fast**: Having built a few personal projects now, I know that speed is actually incredibly important. Speed creates momentum, which creates motivation. I could write a whole post why speed is such a central tenet to my world philosophy.
3. **Full-send AI**: As a corollary to the above point, AI is one of the best ways of quickly shipping out projects. Having developed skills to handle AI at Ramp, I wanted to apply them in my personal domain as well.
# How I built Heron
The first thing I did was create a plan. From my experience at Ramp, I know how important it is to create some sort of plan that AI can follow when implementing that it can constantly reference. I set up a Claude Project and did the following:
1. Set up an initial prompt and asked Claude to help refine the prompt for me ![[Pasted image 20250613123351.png]]
2. I put the refined prompt into Claude Research and let it work on an artifact for a few minutes, which I then copied over into the Claude Project
3. After reading the artifact, I went over each point over thoroughly and asked questions to Claude when I didn't understand something, such as authentication strategies. I asked Claude to create artifacts so that these results can be put into the project context
4. Asked Claude to make a detailed implementation plan for a coding agent and refined after taking a thorough look![[Pasted image 20250613123823.png]]
All of this took me about an hour of prompting. However, this is well-worth your time as it gives guidelines and rails for AI to actually code your project effectively. I can then chuck these Markdown files into my project that AI can continuously reference as it builds up my project.

I also chose the stack such that I could ship this quickly:
- Next.js for frontend and backend
- Prisma for ORM
- Supabase for database and authentication
- Google OAuth
- Trigger.dev for asynchronous tasks
- Resend for email sending
- Vercel for deployment
All of these are cloud technologies which require minimal setup and can be easily tested locally. I particularly wanted to shoutout Trigger.dev for such a smooth development experience, especially locally! Testing asynchronous tasks has always been a bit of a pain in my past.

Next, I opened up Cursor and methodically worked through each implementation task by simple prompting. This is where my software engineering knowledge came in use, as I could effectively review diffs and guide the AI to structure code effectively. I also plugged in Supabase, Prisma and Trigger.dev docs when necessary. All of this made coding super easy and fast, taking about 4 hours to set up everything in code.

To set up the frontend, I used v0.dev to create a template. I again used the same prompting strategy, where I used my Claude project to refine my prompt before I plugged it into v0. This helped me one-shot a great design that I could simply plug into my project without much of a problem. I then used Cursor to integrate the v0.dev design into the APIs that I built.

The most annoying aspect of this project was deployment, as that can't be easily handled by AI. However, I used Claude enormously to help me debug issues with deployment and used Cursor to refactor code when necessary. Having a local setup and a quick deployment process due to the tools I selected helped me solve my deployment bugs. This took me about 2.5 hours.

Here's the final product!

Signup page (super barebones, since it's only for me):
![[Screenshot 2025-06-13 at 12.48.23 PM.png]]
The only other page on the app – a dashboard:
![[Screenshot 2025-06-13 at 12.48.50 PM.png]]
Email that I would get when the chosen stock falls below the alert threshold I set
![[Pasted image 20250613125024.png]]
# Lessons on building with AI
1. **Super bullish on building personal projects**: The level of effort on building products for yourself has drastically dropped. Before capable AI like Claude, it would have taken me at least 2-3 days to ship out something like this given my relative lack of knowledge with Next.js. I am planning to ship out a lot more ideas now that execution costs are so low.
	1. Skills in building personal projects are now solely on project management. Have you sufficiently scoped down your initial requirements? Are you using a tech stack that you are comfortable reviewing?
2. **Planning is critical**: Couple of thoughts on this
	1. We can now easily prototype ideas and create artificial plans with artifacts. This is super useful in determining if a particular idea is worth building out. I had a couple of other ideas I wanted to build in a sprint and Claude helped me check my core assumptions and determine whether the idea was even worth building in the first place
	2. Planning provides a lot of guardrails for AI. What I have noticed time and time again is that AI is really good at performing focused tasks. Asking Cursor or Claude Code to one-shot an app usually fails as it cannot handle task-breakdown as easily given its limited context. That is where humans come into play. We can guide plans and breakdown ambiguous tasks into smaller pieces.
	3. Integrating your core principles into planning helps AI make decisions. There were several times when Cursor chose a swifter execution plan given my constraints that this was a project designed for a few users only and that I prioritized speed of shipping. This is akin to the importance of culture in companies. By integrating core cultural principles and vision in employees, we can help individuals act in-line with the broader company culture and make tough decisions that others in the company would generally agree with.
3. **Refine research prompts with LLMs**: Research prompts really work when the prompt is extremely detailed on what exactly you want, which resources you prefer looking into, and what criteria you would use to judge sources. Working with LLMs to create such research prompts are extremely helpful in eliciting this information. Prompt construction transitions from a solo task of writing out requirements to a rich conversation that LLMs can condense into a good research prompt. Frankly, it's far more fun.
4. **Short, focused chats are superior**: Context management is increasingly becoming an important skill when working with LLMs. In my experience, chats with too much context and too many goals often lead to more haywire execution plans by the AI. Keeping it focused on a singular goal and providing the relevant context for that goal can help the AI move a lot faster and in the correct direction.
5. **Use multiple LLMs**: I often battle-tested my prompts with ChatGPT to make sure it also agreed with the conclusions that Claude offered. This Socratic-esque style of LLM usage can help uncover important decision points that might require some human intervention. I do this often at work since we have access to a lot of AI tools.

There are so many more tips shared in [r/ClaudeAI](https://www.reddit.com/r/ClaudeAI/) that I have used to help optimize my project development process ([post 1](https://www.reddit.com/r/ClaudeAI/comments/1la5kp4/am_i_the_only_one_who_finds_the_secrets_to/), [post 2](https://www.reddit.com/r/ClaudeAI/comments/1l1uea1/after_6_months_of_daily_ai_pair_programming_heres/)). In my next project, I really want to use Claude Code more now that it is available for Pro and have generally found it better than Cursor in general coding tasks at work. 

All in all, I am super bullish on vibe-coding with AI and hoping to ship out a lot more projects (maybe even projects that others can use!). If you really want to use Heron and too lazy to vibe-code this yourself, message me.