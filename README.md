 # Failure mode bestiary

A collection of failure modes I've seen in software systems.

If you enjoy this, you may also be interested in:

(From me)
* [awesome-limits](https://github.com/lorin/awesome-limits) list of limits
* [A conjecture on why reliable systems fail](https://surfingcomplexity.blog/2017/06/24/a-conjecture-on-why-reliable-systems-fail/)


(From others)
* [The VOID (Vericia Open Incident Database)](https://www.thevoid.community/)
* [Incident Phenomena: Shorthand Names, à la Danny Ocean](https://www.adaptivecapacitylabs.com/blog/2020/12/21/incident-phenomena-shorthand-names-a-la-danny-ocean/)

## Blackholed traffic

When you accidentally route traffic to the wrong place.

## DNS

> It's not DNS
>
> There's no way it's DNS
>
> It was DNS

Attributed to Reddit user [SSbroski](https://www.reddit.com/r/homelab/comments/5i6kza/comment/db5rzub/?utm_source=share&utm_medium=web2x&context=🤽‍♂️3)

## Expired certificate

When your TLS certificate expires️, and all of the sudden clients aren't able to communicate with servers anymore.

## Fixing a small problem creates a big problem

When a manual intervention that was intended to mitigate a minor incident triggers a major incident.

## Poisoned cache

When an invalid data is stored in a cache, leading your service to error or return invalid data until the cache expires.
This can be a very disconcerting failure mode in the moment because the service starts misbehaving, and then starts behaving properly again, and you have no idea what led it to go unhealthy and no idea how it fixed itself.

## Retry storm

When a service goes temporarily unhealthy and so times out or returns errors, and then there are many retries from the clients, and the service is overwhelmed by the retries. 
This is a specific case of a *thundering herd* problem (see below).

## Saturation

Whenever the system hits some limit that it isn't able to handle.  See [awesome-limits] for all kinds of examples.

## Thundering herd

When you get an atypically large amount of traffic coming into the system. For example, let's say you have a large number of devices in the field that are all scheduled to reboot at the same time, and they all phone home on startup. This is a specific example of *saturation*.

## Unexpected behavior from a helpful system

When an incident is triggered by unexpected behavior of a subsystem whose primary purpose was to improve operations in some way (e.g., improve reliability, observability, degrade gracefully).


## Unscoped query

When a query against a database (in particular, a write) is scoped to "everything" (the equivalent of leaving out the `WHERE` clause in a SQL query.)

[awesome-limits]: https://github.com/lorin/awesome-limits