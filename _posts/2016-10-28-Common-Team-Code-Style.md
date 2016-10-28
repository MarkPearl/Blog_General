---
layout: post
title: Initial conflict in a mob
tags: Mobbing
category: Unpublished
---

When you start mob programming for the first time there will be conflict. More than often this conflict exists because there is a discrepency in the coding standards and approaches amongst the individuals in your team. 

Before, having a consistent team coding standard and approach was hard. If you were in teams similar to the ones I was in, you probably had a team document outlining stylistic code prefences, a peer review process when someone completed a feature, or even practiced pair programming. While all these practices are good, they are not as good as mob programming at achieving a consistentcy. 

It comes down to two things that mob programming does that other practices do not do at the same level:

1. Near zero latency between the code being written and people reviewing it  
2. High diversity in the feedback with multiple people giving their input

### The challenge of near instant feedback

The challenge of near instant feedback from people who have never coded as a group before is conflict. This conflict most often manifests itself in stylistic code preferences (turns out most programmers are passionate about the code they write and how they write it). If the conflict is not managed effectively it escalates. As it escalates you risk people getting jaded and not wanting to participate in the mob again. Having an explicit strategy for handling conflict in a mob is crucial.

### See initial conflict in a mob as a good thing

First, it helps for a team to recognize that initial conflict in a mob is a good thing. It shows that the people in your team care about the code they write.

Secondly, you are having conflict because there were previously discrepencies in how you as a team were doing things. Tackling these discrepencies will lead to a happier team.  

For instance, if your team tackles the conflict around stylistic code preferences properly you will end up with a consistent team code standard. Opening up a code base and not being able to differentiate between the code you wrote and the code someone else wrote because the code is consistent makes most developers very happy and productive.

### Defer in depth stylistic discussion for later

Defer in depth stylistic discussions for after the mob session. It's easy for a mob to loose momentum when discussing stylistic preferences on code (trying to resolve what particular syntax you use for branching logic is not going to be solved in any short time). 

If you can't get full agreement on specific stylistic preferences within a short amount of time - say two minutes - defer the discussion for later and go with what the majority of the mob feels is the preferred style.

> It is useful to get agreement before a mob starts that when there are differences of opinion, we will go with the mob majority vote.

When hitting a stylistic difference and getting a majority vote from the mob, if an individual in the mob still feels strongly that they want to discuss the topic, the issue should be noted and deferred. We've found putting these "items to discuss" on post it notes on a whiteboard near the mob station and then making sure we discuss them at some point in the near future allows the mob to move forward with solving the problem at hand.

### There are no I's in mob 

Sometimes you are going to be in a mob, find an approach or technique that you are really passionate about that other people in the mob just don't see the value or agree. Fight the urge to put yourself ahead of the team. Just as there are no I's in team, there are no I's in a mob. Put the mob first. 

If there is a stylistic preference the mob doesn't value that you do, you should look for opportunities to 