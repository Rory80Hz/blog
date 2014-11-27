# Microservices - choices and challenges 
James Lewis

## Why?

* cheap to replace
* quick to scale
* withstand failure

What does evolutionary architecture mean?
Think about your future version of yourself (they are smarter than you)

Why do we build such massive things?

Seems like this stuff emerged around 2011...was on thought works tech radar in March 2012.

Beware µ-services envy (not using in the right places/times)

See:

[Microservices - M.Fowler and J.Lewis](http://martinfowler.com/articles/microservices.html)

## Characteristics
### Componentisation via services
Previously, this was achieved by libraries, but all imported into one big thing. Keep em separate

### Organised around business capabilities
Systems should fit into how the business works (slightly analogous to DDD). Danger though is that if you have a badly structured organisation, it may lead to a badly constructed system.

### Decentralised Data Management
Bring the data to where it is needed, partition it, don't have the mega schema, decompose it. Netflix is the crazy huge example of this, they share the wealth via open source.

### Products / Services not Projects
Basically what GOV.uk are doing...build it and run it. Not lets have an awesome product, now we are done hey support ENJOI LOL.

### Decentralised Governance
Correlates to agile manifesto, this is about empowering people to do the right thing, not for ENTRPIZ sales of MICROPRISE Products.

### Smart Endpoints Dumb Pipes
Simple transport mechanisms, and context aware endpoints.

## Characteristics 
### Evolutionary Design
Life can be understood backwards, but must be lived forwards.

Example worked through is fictional "Create your own adventure book"

Product owner wants some cool new thing...

#### Choice 1: Walking Skeleton
We opted to choose the walking skeleton, over some analysis paralysis.

Alaistair Cockburn's suggestion you build something that is as thing as possible, but actually....runs.

Something put together and make it run...this is massively great.

#### Magic Box
Oh snap, we have some XML do deal with.

Ooh, just dodged xml translation inside the skeleton and built a new thing outside of it to do it! Go new magic architectural box!

But now! Content is slow, what do we do next?

#### Aieee! Caching choice now...
Cache at a lower or higher level...

Point being we keep having to make choices. Future version of you knows way more about this. Hmmm....what to do next.

Lets put a cache in between skeleton and content...nice http cache.

#### HTTP Cache Effective!
We just fixed that problem...

But oh noes...it has to be rebuilt all the time...more options! They both have upsides and downsides.

Future guy would know more about this again! Damn that guy...choice now is to suffer the long tail, or update stuff....

#### Long tail.
Crap. dead. Should have improved performance.


#### What did that all mean?
The theme of the above, is that you constantly have to make choices, they always lead to new choices.

There is no such thing as the right way, let "future you" worry about that when you know more. Be comfortable with uncertainty, you will never know the right answers.

#### When do you use µ-services
Well, it sort of depends really?

You are a startup? Sometimes lots more things is slower if you don't have a mature team.

Are you exploring your domain (easier to refactor monoliths), maybe don't start straight away with tiny services...

Do you want some options later (there is always a cost)?

Really it boils down to this.

More options for Replacing, More options for Scaling. More options for deploying.

### Design for Failure
Again refer to Russ' talk. See Hystrix, patterns like Circuit Breakers, bulkheads and all that good lets assume stuff breaks patterns.

> The internet is not Five 9's fabric
> 
> 	Some Google person

Truly resilient systems are a myth.

> Every socket, process, pipe or remote procedure call can and will hang
>
> M. Nygard, Release It!

In distributed systems how do you know if it is up or down? A monolith is either broken or not, but harder to know when spread out! Same goes for performance...

### Infrastructure Automation
See explosion in Puppet, Chef, Ansible, Docker (largely from 2004 and amazons build it run it approach)

Monitor all the things. (From GDS)

Blue/Green deploys (grey: old, green: new, blue: current)

## Summary
See:

[The 17 rules of UNIX programming](http://en.wikipedia.org/wiki/Unix_philosophy#Eric_Raymond.E2.80.99s_17_Unix_Rules)

> Rule of Diversity
> 
> Distrust all claims for "One True Way"