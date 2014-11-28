# Reactor and Reactive Streams to power your MicroService Architecture 
Stéphane Maldini [Pivotal](http://www.pivotal.io/)

## Intro
A SomethingService will always interact with

* User
* Other Services

It is about boundaries, and dealing with latency.

Uberfact, humans don't like waiting, neither do machines.

See [http://ferd.ca/queues-don-t-fix-overload.html](http://ferd.ca/queues-don-t-fix-overload.html)

## What does Latency cause
Inefficiency, aggressive scaling needed, tech team turnover.

## Reactive Programming / Architecture
A possible answer.

Event-Driven -> Fault Tolerant -> Low-latency -> Elastic

Must be resilient, split concerns to achieve error bulk-heading

Must be scalable.


## Reactor-Core Features
[A]synchronous Dispatchers -> Streams and Promises / Event Bus

Simple Abstract Method Components, tuples, timers.


## Stream
Represents a sequence of data, possibly unbounded
Provide for processing API, such as filtering and enrichment.

### Stream vs Event Bus
They work well combined.

If nested composition > 2, switch to Stream.


### Hot Stream vs Cold Stream
Hot streams are multi-cast real time signals.

Cold streams are repayable signals.


### Stuff you can use
[Akka](http://akka.io/)
[Ratpack](http://www.ratpack.io/)
[Reactor](https://github.com/reactor/reactor)
[RxJava](https://github.com/ReactiveX/RxJava)

see [Reactive Streams Spec](http://www.reactive-streams.org/)