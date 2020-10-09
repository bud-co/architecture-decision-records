# ADR 4: Event-Driven Architecture

* [Table of contents](#)
  * [Context](#context)
  * [Decision](#decision)
  * [Status](#status)
  * [Consequences](#consequences)
  * [More reading](#more-reading)

## Context

Our product has a specific security requirement: data reliability. Since we're dealing with big companies' strategies, we cannot afford to lose data. Having conflicts or problems in our data pipelines is extremely dangerous to us.

We must create extremely reliable software that is failure-proof and can make an audit easier.

## Decision

Event-Driven Architecture solves those problems with ease. When we took a look, especially at [Martin's Event-Sourcing technique](https://martinfowler.com/articles/201701-event-driven.html), we understood that we could create an event-driven application that can react only to events.

The idea is simple: since we're dealing with compliance and audit departments, we can store **every** action in the platform and restore **any** entity from scratch. Even if we suffer from a mass failure in all our servers in this architecture, we could still reconstruct every entity from their event logs.

In an event-driven architecture, every mutating action between aggregates must happen in the event store. Also, if any external source mutates an internal entity, we must track that event too. Only read events are allowed outside the event store.

## Status

Accepted.

## Consequences

Event-Driven Architecture is a pretty new concept, and most software engineers never heard of it. We must ensure that our developers have the required knowledge before changing our domain architecture.

Although this is a pretty stable architecture, it is pretty easy to break the rules and execute actions directly. We must avoid those to sustain reliable software.

Also, we must watch out for external sources of mutation. Those could break the reliability of our event structure. If any external application mutates our entities, those must produce events to notify about that change.

---

## More reading

* [Martin Fowler's blog post](https://martinfowler.com/articles/201701-event-driven.html)
