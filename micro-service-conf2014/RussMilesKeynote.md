# Keynote: On the Origin of Services by Means of Natural Selection, or the Preservation of Favoured Features in the Struggle for Life 
Russ Miles


## Intro
Change happens.

Deal with it.

PO requests change, lies happen....uh, couple of weeks "refactoring"..."uh oh, technical debt means this is hard, have to pay that back"

This isn't the real issue, the issue is figuring what is alive or dead, what can change without resistance.

Start by assessing your objectives, not just blindly enforcing or demanding change, are you actually experiencing problems> µ-services are not an objective, they are an approach or principle.

Principles need to be communicated, and enforced (but in a good way, not by threat of real ultimate death). For example Netflix Simian Army (on purpose disruption to detect people not following these principles).

The best principle is simplicity, people cant focus on more than one thing.

This seems a bit weird if you have thousands of µ-services...BUT they must be single purpose. But, we can deal with thousands of these single purpose things...

## Russ has 3 rules.

Organise - Decompose
Reduce - Single purpose
Encapsulate - 

O.R.E(some)

See Michael A. "shamon" Jackson, on why we love complex solutions/answer....it makes it more interesting! (Meta Work...Neal Ford)

Life Preserver Tool << ?? (Book)

Microservices & Reactive community are trying to do the same thing...

Often we have the monolithic Boulder we are trying to move...think of it more in terms of pebbles, it is easier to move around.


## Microservices Myths

SLOC! Less than x lines of code does not qualify...uh no, size doesn't matter. Can this thing react to change is what its about.

ASYNC OR DIE! Nah, thats an option, you can go for that, it is freakin hard, but it is not some knockout clause.

THEY ARE HTTP! Eh no, again not a qualifier...yes lots do, but the main thing is can the system evolve easily?

Really, it is about agility and being able to adapt not some set of golden qualifiers.


## Emerging Architecture Principles?
Focus on ability to change...
### The King
Focus on the ability for humans to comprehend.
### The Queen.
Mechanical Sympathy...optimise it for the machine.

### Some principles
* Immutability. (Events in the system drive state, Databases are just views on things)
* Events. Key to understand Idempotency (input N times it does the same thing) and safety (we know if we are changing system state or not)
* Separation of Concerns. Do one thing, do it well.
* Loose Coupling (Only do this around change friction (ask about this...))
* Antifragility. (Don't be in a state where you are afraid of failure, think of failure to start with, not about being more robust, these systems resist change.)

## Outcomes
* Reactive Microservices
* Cloud Native
* Data Flows and Science (Ties into Ralph's talk - more on that later), structure is a consequence

## How do you sell this?
Key is ability to change, ability to adapt.
Bottom line is you are more competitive. (For GOV, we can react to citizens needs better and faster)

Always remember, that µ-services are an outcome, not an objective. Do the right thing to build the right thing, right?



Russ Miles Book: Antifragile Software
