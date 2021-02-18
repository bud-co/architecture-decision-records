# ADR 1: Model Overview

- [Table of contents](#)
  - [Context](#context)
  - [Decision](#decision)
  - [Status](#status)
  - [More reading](#more-reading)

## Context

Understanding any software emergency attributes is complicated. Any application can grow exponentially and become extremely hard to understand. Also, there is a massive gap between the engineering understanding of any product and the business team.

## Decision

To reduce that gap, we've decided to use the Domain-Driven Design technique (as you can see [here](../patterns/003-domain-driven-design.md)).

We've divided our domain architecture into two scopes:

1. **Model Overview:** As you can see here, an overview of our architecture, considering only the most relevant entities.
2. **Local Domain Overview:** Every other file in this `domain` folder. They're only considering their domain, with a more detailed view and exploring their inner objects and considering only external entities that affect them.

You can see this domain architecture live in [our Mural](https://app.mural.co/t/d4c6342/m/d4c6342/1611601743018/e66a63dbf7e08734795f60f6114313d063af9ccd), but I've added a snapshot below:
![Snapshot of last know state of our domain model 2020-10-12](assets/001-model-overview/2021-02-18-diagram.png)

## Status

Always changing.

## Consequences

The primary consequence we can have is an outdated domain architecture. So, keep it simple to update. Nothing lasts forever, so our domain architecture changes every day.

---

## More reading

- [Live Domain Architecture](https://app.mural.co/t/d4c6342/m/d4c6342/1611601743018/e66a63dbf7e08734795f60f6114313d063af9ccd)
