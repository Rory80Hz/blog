# The 7 Deadly Sins of Microservices 
Tareq Abedrabbo

This talk was based on Tareq's original post here:

[The 7 Deadly Sins of Microservices](http://www.opencredo.com/2014/11/19/7-deadly-sins-of-microservices/)

___

Below are my notes from the talk

___


Micro services aren't just the service themselves, but all the tools, processes, and patterns that support them. It is difficult to define them entirely.


## Why talk about anti-patterns?
So if we can't define totally what they are, then maybe we can define definitely what they are not.

## 1. The enterprise OSGI application service bus aka build the right thing.

There is no unique way to implement micro services.

Be explicit about your goals and you non-goals, don't add stuff you don't need.

Ask questions, do i need to support a turn of languages? Do I need a load of libraries? How dynamic or flexible should it be? This helps you avoid Meta-Work.

Keep it Simple.

## 2. Porcine Cosmetics (lipstick on a pig)
Why do we need contracts for services? 

Well, abstraction is important. So is encapsulation, think about the contract you protect yourself well, but most importantly, services are there to be composed to build a system.

Start with the contract of your service, think CDD (like TDD but for microservices)

## 3. Message in a bottle
Typically use lightweight messaging, http etc.

Don't enforce a pattern before understanding what you need.

Do I need?

* Request / Response
* Message Persistence
* Reliability
* Async Notification

Distinguish between services, external vs internal, core vs supporting.


## 4. The Single Domain of Failure
Beware the shared domain model. This is common to monolith (and its not even a best practice)

Domains are used for

* driving business objects
* mapping entities to storage
* managing input & output

Shared domain model, breaks encapsulation, and introduces coupling between services, if they share the same model are they really separate services? Or are they just a distributed monolith.

Even from a binary artefact point of view, this introduces fragility, all projects that depend on that artefact will be tightly coupled to changes in the shared binary artefact (domain).

Define Domain in terms of service interaction, not service implementation.

Resource-oriented design.

Resources are anything in the system that you think you are useful, don't build one canonical domain model, its about the representation of these things that are useful to you.

## 5. The Distributed Monolith
Beware inappropriate service boundaries. This is an application that externalises its internal services indiscriminately. 

Internal service components are not always good candidates for externalisation.

Micro services are not a removing abstraction.

If you end up with this pattern, you buy yourself all sorts of issues around deployment, maintainability etc.

Define services that have business meaning and clear boundaries, does it deliver value from a business point of view?

## 6. The Horseless Cart
Neglecting Macro System concerns.

What are Macro things?

* Updating services independently.
* Functional, performance and regression testing
* System wide behaviour including failure scenarios
	* What happens when one node fails? 

Design for a distributed system, runtime introspection, fault-tolerance, latency, failure etc.

MONITOR ALL THE THINGS.

Start with Continuous Delivery and Automated Testing from the start. This isn't an "at the end" thing.

## 7. Disregarding the human factor

In this new world, Dev's need to understand lots of new things (messaging etc.), in a monolith it was a rabbit hole.

Analogous to thinking that instead of making one big Sausage, we make lots of little sausages.

Micro services don't make up for the gaps in your skills.

Invest in your developers. If you don't, don't even bother starting.

At organisation level

> Organisations which design systems ... are constrained to produce designs which are copies of the communication structures of these organisations
>
> M. Conway

So, organisations that work in silos, won't benefit from adopting micro services.

Close collaboration is essential, see DevOps in general, also properly cross functional teams.

The essence of micro services is collaboration. If you can't get context from all parties, then you will likely fail.

## Summary
Based on the above, you should be able to have a more pragmatic view of the micro services world.