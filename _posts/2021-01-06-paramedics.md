---
layout: post
title: UW Blueprint - Paramedics Web App
---

![paramedics_1](https://aaronabraham311.github.io/public/img/paramedics_1.jpg)
*Taken before COVID-19*

This is Ezra Street in Waterloo during St. Patrick's Day. People estimate these crowds range up to 30,000 people. While students are having a fun, drunken time, it's almost always the case that injuries and incidents occur. The paramedics of Waterloo do a wonderful job trying to triage patients based on the severity of cases but the system that they currently use is not scalable and they become overwhelmed with the number of people who need help. 

The paramedics were in need of a better solution to coordinate triaging across multiple collection points during mass-casualty events such as this. The organization approached UW Blueprint, a student organization at the University of Waterloo that creates tech solutions for non-profits. I had the incredibly opportunity to work on this project over an entire year and learned enormous amounts about web app development

## January - April 2020
In my first semester of university, I didn't spend a lot of time in extracurriculars as I was spending more time developing study systems and a good home base for my university endeavors. As I thought about the extracurriculars I wanted to pursue in university, I came across UW Blueprint and immediately decided to apply for the following semester and managed to secure a spot on the team.

When I first joined the team, we were just getting started with the project. While the product manager and designers were busy scoping the project and understanding the user experience, the developers were busy building the backend and endpoints needed to store and serve data to our application. After a careful analysis of our needs and our team's eagerness to learn new technologies, we decided to use a Node-based backend using PostgreSQL as a persistence layer and a GraphQL layer (at that time, relatively new) to serve requests. 
Prior to Blueprint, I had barely any experience building web apps, so this term was an incredibly journey of growth. I learned everything from Git best practices to database terminologies and tricks.

![paramedics_5](https://aaronabraham311.github.io/public/img/paramedics_5.png)
*One of many endpoints I implemented in this term*
## May - August 2020
By this time, the designers had a pretty good understanding of the paramedics' needs and developed a slick interface which was now up to us devs to implement. Our team decided to implement everything in React and TypeScript. This was great except I had no knowledge of either of the two technologies! Like my first term, I experienced huge growth and learned a huge amount about front-end development thanks to the help of my team. 

In particular, I was involved with implementing a good majority of the flow for entering and editing patients in our system. Furthermore, I was often monkeying around in the backend implementing more endpoints and new database behaviours, like cascade deletion and soft deletes. I also had the opportunity to set up our CircleCI infrastructure for our services. 
Here are some pictures from some of the PRs that I landed during this term

![paramedics_2](https://aaronabraham311.github.io/public/img/paramedics_2.png)
*A snippet of our early patient editing screen*

![paramedics_4](https://aaronabraham311.github.io/public/img/paramedics_4.png)
*Soft deletion fuctionality*
## September - December 2020
My final term involved me taking some leadership roles as I led the development of our entire maps features. The map feature is an incredibly important part of our application as it helps dispatchers determine the collection point on the ground and provide the necessary instructions for ambulances to pick up patients. 
This involved a lot of research on the Google Maps API, implementing custom components in React and designing parts of our backend to handle locations. Here is a GIF of tapping functionality I implemented using some geolocation APIs:

![paramedics_3](https://aaronabraham311.github.io/public/img/paramedics_3.gif)

By the end of this term, our application was successfully deployed to the paramedics and most of our functionality is now being tested and used!

## Review
Writing this post was incredibly insightful for myself. It's hard for an individual to understand how much progress they are making when they are in the thick of things; reflecting on these experiences often helps you realize how much growth you experienced. I had no knowledge of web app development before I joined; now I can confidently create a React app without too much difficulty.

Joining UW Blueprint was probably one of the best decisions that I made in my first year of university. It taught me a lot of the basics for software development that have helped accelerate my growth as I continued through university and provided another avenue for exploration. For students mulling over whether to apply, do it! It's an opportunity that you most likely will not regret. Far too many students build side projects just for the fun of it when their skills could actually be used to create something useful like the above. Tying that in with the mission to empower non-profits at UW Blueprint, it was a no-brainer for me. 

If you would like to learn more about UW Blueprint, check out our website [here](https://uwblueprint.org).   