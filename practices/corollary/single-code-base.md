# Single Code Base

Although Kent Beck classifies _Single Code Base_ as a corollary practice, my experience has learn me that this is one of the first practices that **MUST** be adopted for XP teams (or other agile or not agile teams!). The _Single Code Base_ practice will save you a lot of wasted time and headaches caused by an untrusted code base that will slow down software development and make it prone to errors (even serious ones). Moreover, there are concrete and proven ways to implement this practice, so there are no excuses.  

I think that below are the most important statements that Kent Beck put down in _XP Explained_ about the _Single Code Base_ practice:

<br>

> "_There is only one code stream. You can develop in a temporary branch, but never let it live longer than a few hours._"  
>
> "_Multiple code streams are an enormous source of waste in software development._"  
>
> "_Rather than add more code bases, fix the underlying design problem that is preventing you from running from a single code base._"

<br>

First, talk about the two last points.  

<br>

## "_Multiple code streams are an enormous source of waste in software development._"  

<br>
It's true, having uncontrolled multiples code streams is a huge source of wasted time, and also, an easy way to be in trouble. I bet that almost every developer has found a project with a lot of branches, where nobody knows which is the branch with the source code running in production, and nobody knows when and why each branch was deployed in production (if they ever deployed!).

I went through that. An important project of a company where I worked had that problem. That caused problems like these:

<br>

- Slow down delivery time. Whether the team was working on a new feature or fixing a bug, they first must spend time (sometimes a lot) researching and determining which branch should be taken as code base to begin development.
- If the team was wrong in choosing the code base branch, features and fixes previously deployed in production were lost until someone identifies that something was broken. This caused service interruptions, damaged trust, and generated a stressful environment.

<br>

All of them, perfectly avoidable problems. We decided to put hands-on and tackle the root cause: The messy and uncontrolled source code repository.And that's the trap in which organizations fall into when they have a system and get new customers with similar needs that the current system covers. They "reuse" the source code for every "flavor". So, when there is a new feature or bug that traverse all the code bases, in the best scenario the development must be replicated on each code base. The mess was huge! It took us three weeks of hard work, but finally, we got a trusted single code base. How did we do it? I'll talk about it later in this post.  
<br>

## "_Rather than add more code bases, fix the underlying design problem that is preventing you from running from a single code base._"

<br>

Again, I bet most of us have seen the next scenario: An organization has a software system and gets a new customer with similar needs that the current system covers. But one problem appears, the misunderstanding about what is reusability... Maybe you got it, but let's got a little deep.

Reusability is the ability of a software component to be reused without modifying it. Reusability prevents us from reinventing the wheel. A great example is the Java Collections Framework, a built-in Java library that delivers ready-to-use data structure implementations. You can reuse the features delivered by this component without the need to modify its source code. In some extraordinary cases, you could extend it. Remember the Open-Closed design principle:

<br>

> "Software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification.”

<br>

Many teams and organizations looking to develop reusable components, but quoting to Robert M. Lefkowitz, who is not at all a big fan of agile methodologies, but have interesting points: 

> "_Reusability has the best ROI of any technology, but effective reuse is not a game for amateurs. If your quality control is not top notch, then you will be reusing
garbage, and your costs will go up instead of down_"

> "_Efforts to reuse only source code do not have a particularly good ROI. Coding is
only the fourth most expensive activity when building large software applications,
and ranks behind the construction of paper documents, defect removal
activities, and even behind meetings and communication for some systems._"

<br>

Reusability is about to take advantage of the **features** delivered by a component, not making a full clone of existing source code to create a new "flavor" (that is forking, but this is another theme).

And that's the trap in which organizations fall into when they have a system and get new customers with similar needs that the current system covers. They "reuse" the source code for every "flavor". So, when there is a new feature or bug that traverses all the code bases, in the best scenario the development will be replicated on each code base. But, could happen, and will happen, that the team forgets one or more code bases and the feature or fix will not be delivered to those customers.

Designing a reusable software solution in one fell swoop is hard, even for experienced people. But there are XP practices like _Incremental Design_ and others like _Refactoring_ that addresses this issue.

So... fix the underlying design problem that is preventing you from running from a single code base.

A clue is in the practice name: **Single** Code Base. The **Single Responsability** states that a software entity (that could be an interface, class **or component**) must have only one reason to change, that is, must have only one job. And what is a source code base? Is the place where the component's source code lives. So, following this principle, you will get a natural relationship between a  Single Responsibility component and its Single Code Base.

<br>
