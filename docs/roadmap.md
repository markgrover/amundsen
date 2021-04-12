# Amundsen Roadmap

The following roadmap gives an overview of what we are currently working on and what we want to tackle next. This helps potential contributors understand the current status of your project and where it's going next, as well as giving them a starting point to get involved in planning.

## Amundsen Mission

> _To organize all information about data and make it universally actionable_

## Amundsen Vision
### Vision
Amundsen's vision to make it easy to find, understand and stay up-to-date on data for anyone while maintaining good data governance within the company.
We are currently focussed on analytical data present in data warehouses used for analytics, decision science, data science. We do occasionally touch upstream systems (event definitions, replication from production stores, or other third party ingests) but only to add more context to the analytical data that derives from them. We integrate with various products in the analytical ecosystem to power an automated data discovery & governance experience. We integrate with data warehouses, BI/Dashboarding tools, HR systems, Feature stores (like Feast) and more. You can find a full up-to-date list of integrations [here](../README.md#supported-entities). In future, such integrations may extend to other systems like notebooks, streams, etc.

### Personas
We are currently focussed on producers (Data Engineers, Analytics Engineers) and consumers (Analysts, Data Scientists) of data. We do cater to business users especially with our integration with dashboarding systems, howevr, our immediate roadmap is focussed on going deeper and further to aid Data Engineers, Analytics Engineers, Analysts and Data Scientists than on business users. Investments to business user workflows will come in medium and long term roadmap.

### Depth of metadata
We are investing in collecting and surfacing metadata in user's workflows. For each system, our vision is to collect and surface metadata in the below three categories (see [Ground paper](http://cidrdb.org/cidr2017/papers/p111-hellerstein-cidr17.pdf), for reference):
 1. Application context - e.g. names & descriptions of tables & columns for example, column types, etc.
 2. Behavior - e.g. what process generates a table, what table is this table generated from, or who are the users that query a table or view a dashboard.
 3. Change - e.g. how has this data or the code that populates this data changed over time, how has the lineage graph evolved.

## Roadmap
This is the immediate roadmap we are working on. The idea is to keep this list intentionally small so it's clear what the community is actively working on. Everything else is listed in an unsorted section below.

#### Native lineage integration

_What_: We want to create a native lineage integration in Amundsen, to better surface how data assets interact with each other.

_Status_: First version (Stage 0, see [merged RFC](https://github.com/amundsen-io/rfcs/pull/25)) exists. Working on second version (RFCs in progress - [backend](https://github.com/amundsen-io/rfcs/pull/32), [graph viz](https://github.com/amundsen-io/rfcs/pull/32)).

#### Neptune Databuilder support

_What_: Support ingesting metadata when using AWS Neptune backed via databuilder (`FsNeo4jCSVLoader`, `FsNeputuneCSVLoader` and various Neptune components). Details could be found in [RFC-13](https://github.com/amundsen-io/rfcs/pull/13/files).

_Status_: implementation started

#### RDS Proxy Support

_What_: Support RDS as another type of proxy for both metadata and databuilder. Details could be found in [RFC-10](https://github.com/amundsen-io/rfcs/pull/10).

_Status_: approved, implementation started


## Bulk roadmap (unsorted)

#### Integration with Data Quality systems to bring check level metadata

_What_: Integrate with different data quality system and ingest data quality check level metadata on a table and column level.

DQ integration at a table level has already been done via [programmatic descriptions](https://technology.edmunds.com/2020/05/27/Adding-Data-Quality-into-Amundsen-with-Programmatic-Descriptions/) & table reports ([presentation](https://www.youtube.com/watch?v=Fy_lRWm_IL0&t=1m22s), [slides](https://docs.google.com/presentation/d/1SLLZkPA77mxM0BCXDmclmN5o2sNZ4KR1ptB6fq5Hu1k/edit#slide=id.p4)). Deeper integration to bring check level and more richer quality metadata into Amundsen hasn't been scoped yet.

#### Curated navigation experience

_What_: Currently Amundsen's experience is very focussed on search. However, especially for new users, an experience where they are able to navigate through the data hierarchy is very important. This item proposes to revamp the navigational experience in Amundsen (currently, barebones - based on tags) to do justice to the user need to browse through data sets when they don't know what to even search for.

#### Notifications when a table evolves

_What_: Notify users in Amundsen (akin to Facebook notifications or similar) when a table evolves. Owners of data and consumers of data will likely need to be notified of different things. Preliminary designs available (see [presentation](https://www.youtube.com/watch?v=gVf7S98bnyg&t=90s)).

#### Improve search ranking

_What_: Overhaul search ranking to improve results.

#### Commonly joined tables / browsing the data model

_What_: As a data user, I would like to see commonly joined tables and how to join them.
One option would be to show commonly joined tables and showing example join queries. Another option would be to provide a navigational experience for data model, showing foreign keys and which tables they come from.

#### Push ingest API

_What_: Possible through [Kafka extractor](https://github.com/amundsen-io/amundsendatabuilder/blob/master/databuilder/extractor/kafka_source_extractor.py), though Kafka topic schema is not well defined. And it requires client side SDK to support message pushing.

#### Granular Access Control

_What_: we want to have a more granular control of the access. For example, only certain types of people would be able to see certain types of metadata/functionality

#### Versioning system

_What_: We want to create a versioning system for our indexed resources, to be able to index different versions of the same resource. This is especially required for machine learning purposes.

#### Index Teams

_What_: We want to add teams pages to enable users to see what are the important tables and dashboard a team uses

#### Integrate with services

_What_: For companies that use microservices, we want to how these services interact with data artifacts, in particular, which data artifact is produced by what service.

#### Index S3 buckets

_What_: Add these new resource types to our data map and create resource pages for them

#### Index Pub/Sub systems

_What_: We want to make our pub/sub systems discoverable

## How to Get Involved

Let us know in the [Slack channel](https://app.slack.com/client/TGFR0CZM3/CGFBVT23V) if you are interested in taking a stab at leading the development of one of these features.

You can also jump right in by tackling one of our issues labeled as ['help wanted'](https://github.com/amundsen-io/amundsen/labels/help%20wanted) or, if you are new to Amundsen, try one of our ['good first issue'](https://github.com/amundsen-io/amundsen/labels/good%20first%20issue) tickets.
