# ADR 1: High-Level Overview

* [Table of contents](#)
  * [Context](#context)
  * [Decision](#decision)
  * [Status](#status)
  * [More reading](#more-reading)

## Context

Understanding any software emergency attributes is complicated. Any application can grow exponentially and become extremely hard to understand. Also, there is a massive gap between the engineering understanding of any product and the business team.

## Decision

To reduce that gap, we've decided to use the Domain-Driven Design technique (as you can see [here](../patterns/003-domain-driven-design.md)).

We've divided our domain architecture into two scopes:

1. **High-Level Overview:** As you can see here, an overview of our architecture, considering only the most relevant entities.
2. **Local Domain Overview:** Every other file in this `domain` folder. They're only considering their domain, with a more detailed view and exploring their inner objects and considering only external entities that affect them.

You can see this domain architecture live in [our Mural](https://app.mural.co/t/d4c6342/m/d4c6342/1602287089483/2d511fb73f993a8ac25d25d1450a8b5a5b37d6c4), but I've added a snapshot below:
![Snapshot of last know state of our domain architecture 2020-10-09](assets/001-high-level-concept-overview/domain-architecture.png)

## Status

Always changing.

## Consequences

The primary consequence we can have is an outdated domain architecture. So, keep it simple to update. Nothing lasts forever, so our domain architecture changes every day.

---

## More reading

* [Live Domain Architecture](https://app.mural.co/t/d4c6342/m/d4c6342/1602287089483/2d511fb73f993a8ac25d25d1450a8b5a5b37d6c4)
