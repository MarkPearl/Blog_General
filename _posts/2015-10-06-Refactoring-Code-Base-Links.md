---
layout: post
title: Refactoring Code Notes
tags: Refactoring
category: Misc
---

> It’s easy to look at work that came before you and decide it’s no good and that you can do better. This is the wrong attitude. It will lead you down a very dangerous path.  

#### 7 Key takeaways for refactoring legacy code

1. Never judge legacy code or change it until you’ve taken the time to fully understand it.  
2. Sequence diagrams are your friend.  
3. Prefer small, incremental improvements over wholesale re-writes or changes.  
4. Each change should attempt to leave the code a little better off than it was when you found it.  
5. If you need to make big changes, make a business case and get approval first.  
6. When adding new features, try to “go with the flow.”  
7. If you need to take the code in a new direction, isolate your changes and use the Adapter Pattern to integrate.  

#### Questions to ask before refactoring code

1. What is my goal in doing the refactor project?  
2. How will I know if I've accomplished the goal?  
3. What will be different if I accomplish the goal?  
4. How much time and money should be invested in this goal?  
5. What is the ramifications if I postpone the refactoring project for six months?  

Source: Marcus Blakenship

#### Characterisation Tests

These are useful for nailing down the behavior of the existing code. They are different from test driven tests - revealing intent is not necessarily a primary objective.

### Refactoring Articles ###

[Martin Fowlers Catalog of Refactorings](http://refactoring.com/catalog/)  
[How to conque legacy code](https://medium.freecodecamp.com/conquer-legacy-code-f9e23a6ab758#.pyn3q1fet)  
[Shims, Jigs, and other woodworking concepts to conquer technical debt](http://firstround.com/review/shims-jigs-and-other-woodworking-concepts-to-conquer-technical-debt/)  

### Refactoring Code Base Links ###

Below are a set of links to code bases that are useful for refactoring exercises.  

[Gilded Rose Kata](https://github.com/emilybache/GildedRose-Refactoring-Kata)  
[Legacy Code Retreat Trivia Game](https://github.com/jbrains/trivia)  
[Rob Meyers C# Refactoring Lab](https://github.com/AgileInstitute/labs-csharp-nunit)  
