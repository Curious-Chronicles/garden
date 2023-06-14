---
index: BC101
tags: programming-fundamentals, system-design, zero-knowledge
status: started
created: NaN
updated: NaN
---
Related: {{related}}
URL: 
- [Introduction to System Design | System Design Tutorials | Part 1 | 2020](https://www.youtube.com/watch?v=FSR1s2b-l_I&list=PLTCrU9sGyburBw9wNOHebv9SjlE4Elv5a)
- 

---

# Introduction to System Design

System can be defined as: 
1. User of system
2. Requirement of user.
3. Types of component used to achieve those requirement. 

Design can be defined as: Connecting the user, requirement and its component to achieve the objectives. 


# Importance of System Design

1. How we approach the problem. 

Do: 
1. Understand the problem
2. Requirements
3. Design

Problem -> Reframe -> Analyze -> Solution

Consider the following things: 
1. Scalability 
2. Latency
3. Availability 
4. Consistency

We should also be able to explain the reasoning behind choosing certain flows.


# System Design 101

Product Requirement Docs -> Features / abstract concepts -> Data definition -> Objects -> Data base.

So once you know what type of data you need to store, you can then begin to define the types of endpoint required to achieve this goals. 

You also need to know which of the product requirements are important. Also need to think about the various failure point in the system. 

## Extensibility 

It means how easy it is modify the code based on the requirement. 

## Testing

You also need to test the system design, with edge cases and happy paths. 

21:48