# Notes

## @asbjornenge

* hello
* twitterz/githubz
* no small ascii of my avatar
* System architect @ Smart Management 
* Exploring and tools for containers + microservice architectures

## microservices

* quite a few things to keep in mind (especially framework)
* a whole bunch of :crap:
* enterprise solutions ~ weird abstractions, lock-in, cant re-use

I just want to make my little service and let it go. Like a butterfly...

## swarms

* It gets worse
* Stateless services are great
* Stateful are PITA, but unavoidable
* When you want to spread stateful load we call that a cluster / swarm -> coordination
* Unfortunately I have to deal with that quite a bit.

So, I started thinking about a way to make it easier. And I made a module :-P

## hyperswarm

* Introducing hyperswarm.
* Hyperswarm is a mdns-swarm with a shared distributed state.
* multicast-dns ~ service discovery, pushing back into service
* hyperemitter ~ communication channel 
* 200 lines of code
** Exchanges events with new peers
** commits
** replay

* !!! OPEN WEBSITE AND SHOW

Tradeoffs:

* Same network
* Eventual consistency (pretty much all)

Thoughts

* We can now make a hyperswarm node with 1 line of code
* Reducing friction

## hyperdraw

* Show hyperdraw code
* Show wifi stuff

*DEMO TIME*

* Other usecases
** auto-clustering, auto-balancing conatiner runner
** iot
** drone swarm
