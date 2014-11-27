# Agile Organization – Rapid Feature Iteration with Dropwizard and Metrics
Michal Rutkowski

## Motivation
Personal story about failed projects, and lost time.

Management was bad...

Agile development process BUT (shock,horror) waterfall, top driven decision making with late or no validation of business ideas.

Instead, lets have a company that empowers engineers, and reacts to change.

He wanted to avoid this so now works at yammer.

## Agile Organisation
Check out:

* The Lean Startup
* Principles of Product Development Flow

As an organisation (or GOV service) you need to discover what customers want.

You need a process and tools that let you do this.

Thats ability matters, everything else is pointless. Classic build, measure, learn.

### Ship it Maybe?
Don't fear the FAIL. It will happen, you are buying information, and lets you learn and validate your ideas.

### Getting value
Do small projects, makes fails cheaper (analogous to smaller release cycles). Measure, always measure and monitor, otherwise failure was for nothing. Understand why. Automate the hell out of it.

## Yammer
Intro on Yammer, and what it is about...end goal was to try to disrupt hierarchy, it is about bottom up communication, not top down dictation and messaging (see town halls, mass email statements). This links into Austin Bingham's ODP where it is about communication not dictation.

In yammer, projects are short, MVP focussed, teams are small and truly cross functional.

They A/B test everything...actually more Multi Variant Testing (MVT).

They fail often, but they iterate.

EVERYONE gets a chance to be a tech lead, they rotate that function (this is kinda cool, you could do this on a sprint by sprint basis)

Team chooses the process, team delivers it whatever way they want...(doesn't have to be scrum, see Saander and Allen Holub talks about true agility)

Invested heavily in tooling that allows projects to spin up quick, and measure outcomes.

## Dropwizard and Friends
### Brief overview
Yammer started as Ruby on Rails mono-app, but it got super difficult to maintain (apparently it is one of the biggest example of one of these) and deploy, and scale.

This slowed down the ability to iterate.

The CORE metric is how quick can we deliver value.

> Drop wizard is a little bit of opinionated glue code which bangs together a set of libraries which have historically not sucked.
> Coda Hale

Little overview of Dropwizard, see here:

[http://dropwizard.io/](http://dropwizard.io/)

Also, Metrics (included in drop wizard)

### What did they get from using this?
P.O.C can be done in a day.
Easy to deploy.
Cheap to throw away stuff.

Not just that though...
Service complexity is lower, focus on API definition and boundaries.
Cost of bad code is lower, its more isolated and less brittle.


Some other cool things they use....

* Wiremock for testing http://wiremock.org
* Staging environment (aka pre-prod)
* Canary Deployment and Metrics
* Feature Flags (Experiments)
* Shadow Deployment, they push real traffic at a shadow deployment

### How do they deploy?
Typical stuff, Jenkins and Teamcity for CI
Deploymancy - packaging and deployment

### Application Resiliency
* Metrics feed into alerting systems
* Feature Toggles for MVT and A/B testing
* [Telemtry](https://github.com/yammer/telemetry) Feature tracing (we built something similar)
* [tenacity](https://github.com/yammer/tenacity) (Wrapper for Hystrix and Dropwizard)
* [breakerbox](https://github.com/yammer/breakerbox)- monitoring tool for circuit breakers

### How do they test product features?
* experiments A/B testing
* metrics used for business metrics (how often do people call a service, how long are they around etc.)

How do they measure stuff? So have a hypothesis, have data on what happens now, ensure core metrics aren't screwed up, and compare to what happens to the A/B or MVT group.

In GOV the equivalent applies to speed of transactions, dropouts etc.

## Summary
Agility (small a) must come from the organisation and how they think about things, not how the dev process is organised.
