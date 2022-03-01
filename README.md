# microservice_guiding_rules

Cohesion
"the code that change together, stays together"

Coupling   
---------------------- 
* Common Coupling  
Common coupling occurs when two or more microservices make use of a common
set of data( shared database, shared memory, shared file system, etc..).  
The main issue with common coupling is that changes to the structure of the data can
impact multiple microservices at once. Sources of common coupling are also potential sources of resource contention. 
[NOTE]If you see a microservice that just looks like a thin wrapper around
database CRUD operations, that is a sign that you may have weak
cohesion and tighter coupling, as logic that should be in that ser‐
vice to manage the data is instead spread elsewhere in your system.

* Content Coupling
Content coupling describes a situation in which an upstream service reaches into the
internals of a downstream service and changes its internal state. External service accessing another microservice’s database
and changing it directly.

Aggregate: contains the line item(data items), aggregate has its own life cycle, self contained unit. One microservice should handle one Aggregate, although multiple aggregate are handled by one microservice. Ideally want to implement your aggregates in such a way that illegal state transitions are impossible.aggregate is a self-contained state machine that focuses on a single domain concept in our system.ggregates themselves don’t want to be split apart—one microservice
can manage one or more aggregates, but we don’t want one aggregate to be managed by more than one microservice.

Bounded Context: typically represents a larger organizational boundary.
prepare context diagram it will be helpful for gaining knowledge about the architecture of the entire system. 
Representing the collection of assosiated Aggregate, with explicit interface to the wider world.

Event Storming: Collaborative brainstorming exercise designed to help surface a domain model.




