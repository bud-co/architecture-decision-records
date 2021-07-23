# Analytics Foundations

* Status: proposed
* Deciders:
  * Daniel De Lucca
  * Victor Perin
  * Marcelo Travi
* Date: 2021-07-26

Technical Story: [BU-141](https://getbud.atlassian.net/browse/BU-141)

## Context

Our company is starting to growth fast. With that growth, it is common to see the need of complex data analysis. We've solved that by installing Metabase in a read-replica of our OKR transactional database, but even that structure lacks more complex analytics. Concurrently with the previous statement, our company plans to create an analytics product for our customers, enabling real-time complex analysis of their users.

We can't ignore the need to have a proper analytics foundations inside Bud. Also, we can't afford investing a large amount of time building that infrastructure, since everything could change fast. We need to find a way to create a flexible analytics infrastructure that could:

(a) Provide meaningful data regarding our customers;
(b) Be flexible enought to integrate with multiple sources;
(c) Allow the usage from external applications.

In a nutshel, that infrastructure will be the primary source of truth of our company. We could allow customers to fetch data from it. Even our applications could use it in their scopes.

## Decision Drivers

1. Flexibility
2. How easy it is to integrate with external sources
3. Implementation difficulty

## Considered Options

### Snowplow

During my time at QuintoAndar, I've heard a lot about a tool called [Snowplow](https://snowplowanalytics.com/). It is a simple way of enriching behaviour data, creating a data pipeline that could nourish our data warehouse with enriched data. With Snowplow, we could easily fetch data from Amplitude, Hubspot, Smartlook, and others, enrich them by adding data from our transactional databases and them, finally, we could store that data in a proper database.

### Building our own ETL

A common way of solving this issue is creating our custom ETL by using available tools. By doing so, we could easily met any requirements we want, creating a complex infrastructure for that matter.

### Airbyte

While searching for viable options, I found a tool called [Airbyte](https://airbyte.io/). They're pretty new (still in alpha), but they already can integrate with 100+ sources (almost every tool that we use). Their idea is pretty simple: with Airbyte you can export data from a source, import into a destination and apply transformations to it. They call this process: ELT.

## Pros and Cons of the Options

### Snowplow

#### Pros

- Extremelly flexible
- Real-time
- Can integrate with almost every tool

#### Cons

- Can't integrate with databases (it is designed to enrich tracker's data)
- It is complex to implement
- We need to evaluate their license to see if we can create a product with it in the future

### Building our own ETL

#### Pros

- We can do anything we want
- It would be easier to create a product from it in the future
- We would know exactly how it works
- We decide how it works

#### Cons

- It would take a long time to implement
- Problably it would be worse then a especialized product

### Airbyte

#### Pros

- Flexible
- Can integrate with databases
- Easy to implement
- Can be installed in our infrastructure

#### Cons

- We would need to check their license to see if we can create a product from it
- It is still in alpha
- It is not real-time (but, you can run the integration every minute)

## Decision Outcome

After evaluating all options, we've decided to proceed with Airbyte. It meets almost every specification that we have. It is extremelly easy to implement and follows all the best standards. It isn't an in-house solution, but in the current scenario we're on that would not be a big deal with it. Also, we could learn from it and maybe create a new tool in the future, designed to met our needs.

## Open questions

- Is it a good practice to query data directly from our data warehouse? Since one of the business requirements for this project is to display an evolution graph of a given key-result progress, should we allow our platform to query data from our data warehouse?
- If we decide to integrate our platform with the data warehouse directly, should we implement an authentication layer in our analytics application? Or should we allow only our back-end application to interact with it?
