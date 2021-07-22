# Contributing to Architecture Decision Log

On this file, you'll learn how to write company-wide Architecture Decision Records (ADR). Please, read all the following content before submitting any decision for any service. It is important to have a common language, usage, and pattern between all the ADRs to make it easier for new contributions.

In short, an architectural decision record (ADR) is a document that captures an important architectural decision made along with its context and consequences.

On this document you will find the following topics:

* [What is an architecture decision record?](#what-is-an-architecture-decision-record)
* [How to start using ADRs](#how-to-start-using-adrs)
* [How to write my own ADR](#how-to-write-my-own-adr)
* [ADR file name conventions](#adr-file-name-conventions)
* [ADR and ADG folder organization](#adr-and-adg-folder-organization)
* [Default ADGs](#default-adgs)
* [Suggestions for writing good ADRs](#suggestions-for-writing-good-adrs)
* [For more information](#for-more-information)


## What is an architecture decision record?

An **architecture decision record** (ADR) is a document that captures an important architectural decision made along with its context and consequences.

An **architecture decision** (AD) is a software design choice that addresses a significant requirement.

An **architecture decision log** (ADL) is the collection of all ADRs created and maintained for a particular project (or organization).

An **architecturally-significant requirement** (ASR) is a requirement that has a measurable effect on a software system’s architecture.

All these are within the topic of **architecture knowledge management** (AKM).

The goal of this document is to provide a fast overview of ADRs, how to create them, and where to look for more information.

Abbreviations:

  * **AD**: architecture decision
  * **ADL**: architecture decision log
  * **ADR**: architecture decision record
  * **AKM**: architecture knowledge management
  * **ASR**: architecturally-significant requirement

## How to write my own ADR

Before writting your own ADR decide where you're going to store it. You have two options:

1. **If your ADR is related to the entire company,** you should keep it here.
2. **If it is related to a given topic or domain,** you should place it inside `docs/adl` at your project's repository.

After that, you can use [our company's ADR template](TEMPLATE.md) to write your ADR. It is divided into the following sections:

* **Title:** These documents have names that are short noun phrases. For example, "ADR 1: Deployment on Ruby on Rails 3.0.10" or "ADR 9: LDAP for Multitenant Integration"
* **Context:** This section describes the forces at play, including technological, political, social, and project local. These forces are probably in tension, and should be called out as such. The language in this section is value-neutral. It is simply describing facts.
* **Decision:** This section describes our response to these forces. It is stated in full sentences, with active voice. "We will …"
* **Status:** A decision may be "proposed" if the project stakeholders haven't agreed with it yet, or "accepted" once it is agreed. If a later ADR changes or reverses a decision, it may be marked as "deprecated" or "superseded" with a reference to its replacement.
* **Consequences:** This section describes the resulting context, after applying the decision. All consequences should be listed here, not just the "positive" ones. A particular decision may have positive, negative, and neutral consequences, but all of them affect the team and project in the future.
* **Experience report:** _(optional)_ This section allow you to record experiences that you had while implementing/using the given architecture.
* **More reading:** _(optional)_ Any attachment/relevant content for your ADR.

You can create your own markdown file following that template, and save it at `records/<your-context>/<your-ADR-name>.md`. **Before deicing a name,** take a look at the [ADR file name conventions](#adr-file-name-conventions) section at this file.

## ADR file name conventions

Our ADRs are typical text files. So, we must normalize the name convention of those files. Each file has a three digit number prefix, followed by `-`. That prefix helps us to understand the point in time and order of our ADRs. Also, the name convention should use `kebab-case`.

Examples:

  * 001-choose-database.md
  * 002-format-timestamps.md
  * 003-manage-passwords.md
  * 004-handle-exceptions.md

Our file name convention:

  * The name has a present tense imperative verb phrase. This helps readability and matches our commit message format.
  * The name uses lowercase and hyphens (same as this repo). This is a balance of readability and system usability.
  * The extension is markdown. This can be useful for easy formatting.

## ADR and ADG folder organization

After creating a new ADR, you **must** keep it inside the [adr](./adr) folder. That folder is a imutable record of **all our ADRs**. If you wish, you can add that ADR to an Architecture Decision Group (ADG). To do so, you can simply create a symbolic link from your original file to the group inside the [adg](./adg) folder.

That organization makes our structure more flexible and easier to change.

## Default ADGs

Although ADGs can be created ad-hoc and at any time, there are three default ADGs that will always exist, they are:

- [Accepted](./adg/accepted): All accepted an valid ADRs
- [Rejected](./adg/rejected): All rejected ADRs
- [Deprecated](./adg/deprecated): Any ADR that was accepted, but are not valid anymore

## Suggestions for writing good ADRs

Characteristics of a good ADR:

  * Point in Time - Identify when the AD was made
  * Rationality - Explain the reason for making the particular AD
  * Immutable record - The decisions made in a previously published ADR should not be altered
  * Specificity - Each ADR should be about a single AD

Characteristics of a good context in an ADR:

  * Explain your organization's situation and business priorities
  * Include rationale and considerations based on social and skills makeups of your teams

Characteristics of good Consequences in an ADR::

  * Right approach - "We need to start doing X instead of Y"
  * Wrong approach - Do not explain the AD in terms of "Pros" and "Cons" of having made the particular AD

A new ADR may take the place of a previous ADR:

  * When an AD is made that replaces or invalidates a previous ADR, a new ADR should be created

## For more information

Introduction:

  * [Architectural decision (wikipedia.org)](https://wikipedia.org/wiki/Architectural_decision)
  * [Architecturally significant requirements (wikipedia.org)](https://wikipedia.org/wiki/Architecturally_significant_requirements)

Other templates:

  * [Documenting architecture decisions - Michael Nygard (thinkrelevance.com)](http://thinkrelevance.com/blog/2011/11/15/documenting-architecture-decisions)
  * [Markdown Architectural Decision Records (adr.github.io)](https://adr.github.io/madr/) - provided by the [adr GitHub organization](https://adr.github.io/)
  * [Template for documenting architecture alternatives and decisions (stackoverflow.com)](http://stackoverflow.com/questions/7104735/template-for-documenting-architecture-alternatives-and-decisions)
  * [ADR template by Michael Nygard](https://github.com/joelparkerhenderson/architecture_decision_record/blob/master/adr_template_by_michael_nygard.md) (simple and popular)
  * [ADR template by Jeff Tyree and Art Akerman](https://github.com/joelparkerhenderson/architecture_decision_record/blob/master/adr_template_by_jeff_tyree_and_art_akerman.md) (more sophisticated)
  * [ADR template for Alexandrian pattern](https://github.com/joelparkerhenderson/architecture_decision_record/blob/master/adr_template_for_alexandrian_pattern.md) (simple with context specifics)
  * [ADR template for business case](https://github.com/joelparkerhenderson/architecture_decision_record/blob/master/adr_template_for_business_case.md) (more MBA-oriented, with costs, SWOT, and more opinions)
  * [ADR template MADR](https://github.com/joelparkerhenderson/architecture_decision_record/blob/master/adr_template_madr.md) (more Markdown)
  * [ADR template using Planguage](https://github.com/joelparkerhenderson/architecture_decision_record/blob/master/adr_template_using_planguage.md) (more quality assurance oriented)

In-depth:

  * [ADMentor XML project (github.com)](https://github.com/IFS-HSR/ADMentor)
  * [Architectural Decision Guidance across Projects: Problem Space Modeling, Decision Backlog Management and Cloud Computing Knowledge (ifs.hsr.ch)](https://www.ifs.hsr.ch/fileadmin/user_upload/customers/ifs.hsr.ch/Home/projekte/ADMentor-WICSA2015ubmissionv11nc.pdf)
  * [The Decision View's Role in Software Architecture Practice (computer.org)](https://www.computer.org/csdl/mags/so/2009/02/mso2009020036-abs.html)
  * [Documenting Software Architectures: Views and Beyond (resources.sei.cmu.edu)](http://resources.sei.cmu.edu/library/asset-view.cfm?assetID=30386)
  * [Architecture Decisions: Demystifying Architecture (utdallas.edu)](https://www.utdallas.edu/~chung/SA/zz-Impreso-architecture_decisions-tyree-05.pdf)
  * [ThoughtWorks Technology Radar: Lightweight Architecture Decision Records (thoughtworks.com)](https://www.thoughtworks.com/radar/techniques/lightweight-architecture-decision-records)

Tools:

  * [Command-line tools for working with Architecture Decision Records](https://github.com/npryce/adr-tools)
  * [Command line tools with python by Victor Sluiter](https://bitbucket.org/tinkerer_/adr-tools-python/src/master/)

Examples:

  * [Repository of Architecture Decision Records made for the Arachne Framework](https://github.com/arachne-framework/architecture)

See also:

  * REMAP (Representation and Maintenance of Process Knowledge)
  * DRL (Decision Representation Language)
  * IBIS (Issue-Based Information System)
  * QOC (Questions, Options, and Criteria)
  * IBM’s e-Business Reference Architecture Framework
