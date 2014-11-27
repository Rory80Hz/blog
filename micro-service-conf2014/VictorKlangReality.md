# Keynote: How reality shapes microservice architectures 
Viktor Klang

___

This one is pretty abstract! Hard to follow from the notes. Basically, think about systems in reality and how they work...

___

> If you cannot solve a problem without programming, you cannot solve a problem with programming.
> Klangs Conjecture

Reality > Imaginary

Sometimes its tricky to distinguish between whats real and what is imaginary.

## Reality
* Separation between space and time.
* Separation gives us
	* communication to coordinate
	* partial/local/stale knowledge
	* delays
	* partial failure

## Systems
> A set of things working tougher as parts of a mechanism and interconnecting network...a complex whole

* Complex inner workings
	* Simple on the surface, complex beneath
* Collaborating components
* Purpose is simple
* Components can be systems themselves
* As simple as is feasible, but no simpler

## Conway's Law
> Organisations which design systems ... are constrained to produce designs which are copies of the communication structures of these organisations
>
> M. Conway

## Communication
* Production and consumption of messages
* We need to be able to address recipients

## Guarantee me this
* Are we ever guaranteed delivery?
	* at-most-once
	* at-least-once
	* exactly-once

## Encoding and Medium
* It's all about protocol
* Overcome fear of using multiple media
	* Removes single point of failure
* No single encoding is one-size-fits-all
* Allow protocol to evolve over time

## Quiz
299 792 458 - Speed of light, this is the upper cap on communication.
340.29 - Speed of sound, fastest human speech can communicate at.
~0.4 - In seconds, the average human latency for visual stimulus to awareness.

## Universal Scalability Law
[See Here](http://www.perfdynamics.com/Manifesto/USLscalability.html)

[Ahmdals law](http://en.wikipedia.org/wiki/Amdahl%27s_law)

The above speaks about scalability, and coherence.

Most code doesn't scale beyond 4 cores (you hit locks and contention) transactions give you coherence, but they kill you.

> Latency is the enemy of responsiveness

## Expectation management
* Fast and Slow is about perception
	* 1 Day for a bank transfer is ok, but a page load in <5s is terrible...
* We can control that to a point
* Still, it propagates downstream
* The key is consistency

## Bursting
* Most communication is bursty
	* Some is predictable
	* Some isn't
	* requires elasticity
	* or load shedding
		* this may cause more bursting

## Littles Law
[See Here](http://en.wikipedia.org/wiki/Little%27s_law)

This is specific to queue length, and managing flow control. watch out for the hockey stick graph!

## Flow control / Back Pressure
* Buffering is only grease
	* does not solve problems
* Load shedding doesn't solve the problem, the sender doesn't have to back off
* When possible use effectively bounded, synch, non-blocking,demand-driven back pressure on a per-sender basis

### No flow control?
![](http://trekkerscrapbook.files.wordpress.com/2013/03/eyebrow-081.jpg)

## Collaboration
* Assume no malice intended
* Tend to sanity check inputs and outputs
* We cannot wait forever
* We cannot afford to actively weight
* There's always a Plan B

## Byzantine coordination
See [The Saddest Moment](http://research.microsoft.com/en-us/people/mickens/thesaddestmoment.pdf)

## Responsibility
aka why it is bad to have

* Multiple responsibility
	* creates conflict regarding priorities
	* lowers reliability
		* increases collateral damage
		* decreases predictability
		* hides the cause from the outside

## Resilience
* Never assume other entities are immortal. Things will fail.
* Treat expectation violations as failures
* Always have a Plan B
* Clients are not responsible to fix a faulty provider
* Fail fast
* Fail predictably
	* If we don't force failures how do we know what happens?

## Postel's Law
> Be conservative in what you do, be liberal in what you accept from others.
> 
> Postel's law

We do this, we reduce the chatter, lowers latency.

## Death
How do we know a component is dead?

## Zombie Apocalypse
Say 3 people have some task to co-ordinate, at what point do you clear off after one person goes out of contact?

What if the loom on the horizon, wandering forwards...slowly...

They are dead. Move on.

## Supervision
* When things go wrong, some person is responsible for sorting it out.
* Does not place burden of fixing it on collaborators
* You will get to a point when you are totally hosed

## Hard to kill
* Isolate
* Replicate
* Spread / Distribute
* Control Flow
* Predict changes in load
* React to changes in load

## Final thought
* Isolate and Contain
* SRP
* Communicate Async
* Delegate and Retain Control
* Avoid coordination
* Minimize contention
* Embrace inconsistency

Go back to the conjecture at the start.