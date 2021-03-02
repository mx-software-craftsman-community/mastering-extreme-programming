# Single Code Base

Although Kent Beck classifies _Single Code Base_ as a corollary practice, my experience has learn me that this is one of the first practices that **MUST** be adopted for XP teams (or other agile or not agile teams!). The _Single Code Base_ practice will save you a lot of wasted time and headaches caused by an untrusted code base that will slow down software development and make it prone to errors (even serious ones). Moreover, there are concrete and proven ways to implement this practice, so there are no excuses.  

I think that below are the most important statements that Kent Beck put down in _XP Explained_ about the _Single Code Base_ practice:

> "_There is only one code stream. You can develop in a temporary branch, but never let it live longer than a few hours._"  
>
> "_Multiple code streams are an enormous source of waste in software development._"  
>
> "_Rather than add more code bases, fix the underlying design problem that is preventing you from running from a single code base._"

First, talk about the two last points.  

## "_Multiple code streams are an enormous source of waste in software development._"  

It's true, having uncontrolled multiples code streams is a huge source of wasted time, and also, an easy way to be in trouble. I bet that almost every developer has found a project with a lot of branches, where nobody knows which is the branch with the source code running in production, and nobody knows when and why each branch was deployed in production (if they ever deployed!).

I went through that. An important project of a company where I worked had that problem. That caused problems like these:

- Slow down delivery time. Whether the team was working on a new feature or fixing a bug, they first must spend time (sometimes a lot) researching and determining which branch should be taken as code base to begin development.
- If the team was wrong in choosing the code base branch, features and fixes previously deployed in production were lost until someone identifies that something was broken. This caused service interruptions, damaged trust, and generated a stressful environment.

All of them, perfectly avoidable problems. We decided to put hands-on and tackle the root cause: The messy and uncontrolled source code repository. The mess was huge! It took us three weeks of hard work, but finally, we got a trusted single code base. How did we do it? I'll talk about it later in this post.

