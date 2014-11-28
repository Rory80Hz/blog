# The Future of Microservices 
Greg Young


SOA returns to its original meaning.

## Event sourcing
Event Sourcing is awesome, it allows for increased agility.

Akka.Persistence -> Event sources your Actors.

Replaying your own events to fix yourself, this helps loads when versioning.

Don't create an event sourced architecture, you make this decision on a "per service" basis. Go have a look at Erlang.

Concurrency Model, a service should be single threaded. The actor model does this well.

Also great for read based services, why? The service has all its data in memory..service dies you can replay messages get back to your original state.

Atom Feeds for integration. (See EventStore or Kafka) Well known and well used.

Eventsource protocol (streaming protocol over http)

### Authentication
Cross service authentication. -> OAuth2 is widely adopted but no standard right now.

### Service discovery
What does your service do? Needs to be some sort of service discovery...maybe include something like myservice/disco return maybe some hosing

```json
{
	link {
			rel: "update",
			href: "http://blah",
			contentType:"application/json",
			action:"POST"
		}}
```
Danger here that the more you build, the more difficult it is to make sure people aren't duplicating effort.

Again Atom can help with this. [Atom Enabled](http://atomenabled.org/)
	
maybe have

http://myorg.org/disco

returns a catalog that links to the service disco feed, again this needs to be Standardised. Implementing this provides transparency of location.

### Cross Micro Service Transaction
Uh. Ok. This is a real problem (maybe one to avoid totally), and there are terrible solutions (see JBoss) but again this needs to be standardised. This is mental.

## The future of Microservices
Eventually, as we move across the chasm of technology adoption, the big guys will get involved, and things may start to go bad.

![Crossing the Chasm](http://paulgstacey.files.wordpress.com/2010/09/technologyadoptionlifecycle3.jpg)

Eventually you will get people building tools, or making another version of the same old standards like before, aka ws* etc.

It turns into absolute junk, the early adopters are looking sweet right now, but it will start to fall apart.

The less competent in the adoption lifecycle will get involved, and the tooling with make it easier for them, doing all the bad ideas.

Point is this, these are not entirely new ideas, and there are lessons to be learned from how this cycle works. We need to make sure we don't repeat the same mistakes, you could either have no standards, which in itself brings problems, or you have masses of standards.