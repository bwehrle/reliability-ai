# Reliability AI

This software does reliability reviews of a system and based on the target reliability and actuals, recommends changes.

It is currently a side-project to explore building AI agents and AI-augmented application

## Goals

The goal of the system is to evaluate, given information, how well each service, and the overall system, is likely to meet its reliability target. 

* Define a domain model for reliability metrics
* Find services, dependencies of the system from documentation and code
* Find the availability SLA of the dependents, including underlying infrastructure
* Consume data about service incidents

Once this information is consumed, the system will make a list of top recommendations of what changes should be make to increase the reliability:
* Pre-production validation (unit, integration or other tests)
* Infrastructure improvements

## Background information: Reliability Metrics
There are several reliability metrics which describe how well the service can be expected to perform under a certain load condition.  Each metric has a `Service Level Objective`, which is the target that should be met for the metric.

* Availability (during normal operating conditions)
* Recovery time objective (RTO: time needed to recover from a region disaster)
* Recovery point objective (RPO: minutes of data that can be lost, )


## Scenarios

* Use traces to discover service map
  * Traces or other data will show that the documentation is not up-to-date nor correct
  * If available, these sources should be used;
  * Human intervention might be needed if instrumentation missing or tracing data is not available
* Human review of any cases that are not clear
  * Detect cases where data is clearly missing
  * Involve a human for review


## Status: WIP
* Create depeDependency graph from documentation
  * Basic domain model for system
  * Markdown processing of system documentation
  * RAG using vector store
* Consuming data about SLA
  * Read stated SLA for service 


### Roadmap
* Configuration
* Observability data consumption (availability, traces, ...)
* Multiple reliability metrics
* Sourcing data from CMS (Notion, Confluence, etc)
* Quality-control of data sourcing (different )
* Human review
* Setting reliabiltiy targets for different goals (availability, recovery, data loss, etc)
* Infrastructure as code consumption
* Topology feedback
* Structure into application (currently notebook)
* Periodic processing of new documents
* Architectural proposal
