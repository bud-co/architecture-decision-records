# ADR 11: Stack

* [Table of contents](#)
  * [Context](#context)
  * [Decision](#decision)
  * [Status](#status)
  * [Consequences](#consequences)

## Context

Since we're a new company, being consistent with our tech stack can help us training our engineering team and boosting our contributions to the community. Many companies are too flexible in their tech stack, which creates a complexity hell, with no standards, low quality, and many strange decisions.

Our stack should not be inflexible. We should decide a **primary** stack that a developer should use if there is no good reason to avoid them. For example, a developer from the economic context could choose Clojure instead of our primary stack, but the developer should have a good reason for it.

## Decision

Below, I've listed the current stack of our company. We've grouped those into layers, each one being responsible for a different part of our company:

### Presentation Layer

This layer is responsible for presenting interfaces for our customers' interaction. We currently don't have any machine interface, since most of our applications are web or mobile apps.

Based on that, here is the stack definition for our presentation layer:
* **Programming language:** Javascript
* **Runtime:** NodeJS
* **Superset:** Typescript
* **Framework:** NextJS
* **Interface Library:** React
* **State management:** Recoil
* **Design System:** Custom, based in Material-UI

### Application Layer

This layer is responsible for our API. It controls and orchestrates executions between our presentation layer, external services, and our domain layer. It must be a scalable, lightweight structure since our presentation layer would rely on it for processing.

Based on that, here is what we've chosen as our stack:
* **Language:** Rust
* **Framework:** Rocket

### Domain Layer

This layer answers for every domain execution. It handles complex logic and therefore requires a powerful and fast programming language. Most of our applications here are workers, receiving events. 

Based on those, here are our stack:
* **Language:** Rust

### Infrastructure Layer

Although most definitions for this layer resides inside the platform's repositories, some are meaningful enough to mention in this ADR:

* **Relational Database:** PostegreSQL
* **Timeseries Database:** Timescale

As I've said before, this stack is flexible, but you should have a good reason to avoid it.

## Status

Accepted.

## Consequences

Defining a solid stack will make hiring and training investments higher. But, with a well-defined stack, the quality of our architecture and code tends to improve, since we can share more knowledge between contexts.

Also, none of the defined patterns are permanent. Anyone can submit a proposal in this ADR and suggest changes to it.
