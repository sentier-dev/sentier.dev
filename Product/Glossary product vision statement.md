# Glossary Product Vision Statement

## Introduction

The Sentier community consensus glossary is a single source of truth for the data and modelling terms used in all our systems, databases, and infrastructure. Before Hestia introduced online Glossaries, such terms were identified as string and stored in XML or Excel. These taxonomies were poorly distributed, versioned, and licensed; they were also used inconsistently. The practical effect was chaos, with enormous amounts of time lost by everyone manually matching strings with minor differences (such as "Toluene, 2-chloro-" versus "Toluene, 2-chloro") and huge costs to translating across LCA software systems.

We have similar problems understanding what current terms mean. Most terminology in LCA was developed from scratch, using labels which reflected the individual preferences of dataset developers. The end result of this process over decades is a set of names which are not self-explanatory, not rooted in the terms or specifications used in industry or standards, and normally requiring additional research to understand what the given labels actually mean.

## Stakeholder Feedback

In our understanding, there is little interest across the community in maintaining separate lists of terms; in other words, the current situation is a product of inertia instead of active maintenance. There seems to be a high willingness to adopt changes if we can help make such changes easy and ensure that they reflect a true, single community consensus.

*What feedback have you received from stakeholders? Are there any conflicting opinions or priorities among stakeholders that need to be addressed?*

## Key Pillars of the Vision

* Each term has an [IRI](https://en.wikipedia.org/wiki/Internationalized_Resource_Identifier), such as "https://g.sentier.dev/models/Prelim/1.6/Kero%20Merox%20Unit". The IRI is the **only** way to refer to that term.
* Each IRI is a webpage which presents a human-friendly representation of all the data behind the term, including its preferred and alternative labels in multiple languages, description, position in a concept hierarchy, additional links for clarification, and correspondence with other terms in other concept hierarchies.
* Each IRI is also an API endpoint which allows for the same information as in the webpage to be retrieved for use by software.
* The extremely strong presumption is that terms come from existing standards whenever possible. Ideally these standards come from well-known standardization bodies.
* The glossary is *append-only* - data can be added but never removed. Both the webpage and API can access the glossary state at any historical time.
* The glossary is developed in an open and community-oriented process. Anyone can suggest changes, and discussion and resolution of such changes is done in the open. There are user guides and tutorials to encourage newcomers to help in glossary maintenance.
* Modifications to the glossary go through both an automated and manual review process. Possible changes are not reflected in the main glossary until review is completed, but these "branches" of the glossary can be used instead of the "main" branch.

## Rationale

*Explanation of the factors, market trends, user needs, and other considerations that informed the long-term vision.*

## Stakeholder Alignment

*Details on how the vision aligns with stakeholder expectations and the broader strategy.*

## Differentiators

*What sets your product apart from competitors or alternative solutions in the market?*

## Success Metrics

*How will you measure the success post-release (KPIs)?*

## Conclusion

*A summary of the vision's importance and the commitment to realising it.*
