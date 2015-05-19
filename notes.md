# Notes

## @asbjornenge

Hi I'm Asbjorn couldn't get a small enough ascii of my avatar, so a unicorn it is.
I work as a system architect @ Smart Management on TagHub and lately I've been exploring
and building out some tools around containers and microservices architecture.

## microservices

If you have been working with microservices, and especially building out a framework for them,
you know there are quite a few things to keep in your head.

You need to think about things like service discovery (how do your services find oneanother),
services dependencies, centralized logging, loadbalancing, multi-host -> networking, subnets, dns and a whole bunch of :crap:

And If you've ever tried one of these "enterprise" solutions; aws, google, kubernetes, ... they have their own
set of weird abstractions to fill your head with.

I just want to make my little service and let it go. Like a butterfly...

## swarms

And sometimes it get's even worse... Stateless services are great. Spread them out, it's fine.
But you can't always avoid state. Sometimes you have nodes spead across your cluster that need 
to do some sort of coordination. We usually call these a cluster or a swarm. 
Unfortunately I have to deal with that quite a bit.

So, I started thinking about a way to make it easier. And I made a module :-P

## hyperswarm

Introducing hyperswarm.

Hyperswarm is a mdns-swarm with a shared distributed state.
It relieas heavily on multicast-dns and hyperemitter. And this is where the node/npm/js community really shines.
Using these two great modules, I was able to build a completely new abstraction in just 200 lines of code.
Anyway...

We use multicast-dns for service-discovery.

Hyperemitter is the communication channel. When hyperswarm finds a new node, it sets up a hyperemitter connection
and exchange events.

Hyperswarm uses these events much like commits, and applies these commits to a state object. 
So each hyperswarm node has this state object, and if everything is good, it's exactly the same for each node 
in the swarm.

Tradeoffs:

* Same network
* Eventual consistency (pretty much all)

With those tradeoffs however, we can make a hyperswarm node with 1 line of code.
Reducing friction is usually a good idea, with npm as a prime example, unless it's for a bad thing. I'm not sure which this is yet.

## hyperdraw

But I made a little demo, and I would love your help trying it out. First I'll just show you some code.

Ok, let's try it out :-D

*DEMO TIME*

Other use-cases; my main goal is to build a auto-clustering, auto-balancing container runner.
But I've been thinking it would be a cool module for iot stuff, and maybe even a drone swarm.
