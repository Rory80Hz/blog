# Micro-service War Stories 
Richard Rodger

Initial intro, generally greatness exist in micro services, people can be more productive, you can adapt better etc.

This talk is generally coming from experience gained using node.

## What are micro-services made of?

Lots of little processes on many machines.
All services can see all messages and react to ones they care about.
Services communicate using asynchronous messages.

As a developer all you should care about incoming and outgoing messages, thats it.

Messages should just be JSON documents, properties are key value pairs.

```json
{
	"info": "user",
	"what":	"login",
	"when":	"2014-10-10T10:10:10",
	"user":	{....}}
```

Use pattern matching to react to the right message.

> As an aside, Unix pipes are the greatest APIs...they are just streams of bytes, you can't add complexity. Same should apply to micro-services and communication between them

Using micro-services you get real software components, finally.

## Characteristics of Software Components
* Re-usable
* Extensible
* Encapsulated and Loosely Coupled
* Well Defined Interface	
	* Does not mean strict!

If by splitting apart an application into micro-services, all you have are just "virtual" functions then you aren't gaining a lot.

## When?
For example, below each would be a micro-service

```
cmd:salestax
cmd:salestax, country:UK
cmd:salestax, country:IE
cmd:salestax, country:US, state:NY
```

Write more micro-services when you need to specialise. Add specific patterns for more fine-grained functionality.

You get service composition when you use pattern matching (again remember, every service gets every message) basically think of building things by adding interceptors / message handlers.

Makes it easy to compose things. For example, If you are writing code that imports memcached or redis or whatever to cache within a service that does something else, this is probably wrong.

## An example
[NodeZoo](http://nodezoo.com/)

An example system big enough to be interesting.

Check it out.

## 💩- Sad Times

Lots of little web servers talking to each other, this never ends well.

Defining schemas for things...remember accept junk, send good stuff...Be liberal in what you etc.

Using any language! Hooray! Maybe sometimes not so cool (not sure about this) but at least pick a language and stick with it, but actually, you can use this approach to get out of jail. I guess the point here is consider maintainability.

Be prepared for boxes and arrows not working anymore to represent your system, it can be hard to understand. Existing patterns may not be relevant or re-usable.

Don't keep state in services. This is totally not cool.

Beware the cargo cult mentality...think about it properly, don't just ape what others are doing.

## 🚀- Awesome Times
Something not mentioned was that this is all predicated on messages and message stores, and all of the important things like idempotency and safety. (missed these points in what was said.)

You can easily swop out components.

Persistence is not as much of a thing, you can use in memory databases etc. You have the truth in the messages.

Enables quicker continuous deployment. The services are the unit of deployment.

You can ensure they work by running old and new side by side, see James talk about blue green deployments, and Michal's talk where he mentioned Shadow Deployment...run both, route both and ensure by monitoring the new version works! Badass. On this point i'd suggest reading a bit about actual proper scientific A/B testing...having proper measurements etc. (Will find blog posts about this later). Pushing this to the extreme your QA process is this measurement of performance (in the broad sense) on production.

## Some technologies
* [senecajs.org](senecajs.org)
* [nodejs.org](nodejs.org)
* [nearform.com/nscale](nearform.com/nscale)
* [docker](https://www.docker.com/)

For Java see:

* [Hystrix](https://github.com/Netflix/Hystrix)

.NET see 

* [NServiceBus](http://particular.net/nservicebus)