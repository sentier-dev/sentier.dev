# Glossary Product Vision Statement

## Introduction

Data and inventory datasets refer to concepts like numbers, units, places, products, and processes. In all the main data exchange formats, these concepts are given as strings, like "kg", "RER", or "steel". Even OLCA schema, which is formally a JSON-LD schema, uses strings for these concepts (see [the example](https://github.com/GreenDelta/olca-schema/blob/master/examples/process.json#L24)). Before Hestia introduced online Glossaries, such terms were identified as string and stored in XML or Excel. These taxonomies were poorly distributed, versioned, and licensed; they were also used inconsistently. The practical effect was chaos, with enormous amounts of time lost by everyone manually matching strings with minor differences (such as "Toluene, 2-chloro-" versus "Toluene, 2-chloro") and huge costs to translating across LCA software systems.

We have similar problems understanding what current terms mean. Most terminology in LCA was developed from scratch, using labels which reflected the individual preferences of dataset developers. The end result of this process over decades is a set of names which are not self-explanatory, not rooted in the terms or specifications used in industry or standards, and normally requiring additional research to understand what the given labels actually mean.

## Long-term vision

The Sentier community consensus glossary is a single source of truth for the data and modelling terms used in all our systems, databases, and infrastructure, and is widely used across the industrial ecology and sustainability assessment worlds. It provides clear definitions for terms based on international standards, is multilingual, and offers services to ease conversion of data into and out of the glossary, and for using the glossary terms (such as automatic unit conversions).

## Stakeholder Feedback and Alignment

In our understanding, there is little interest across the community in maintaining separate lists of terms; in other words, the current situation is a product of inertia instead of active maintenance. There seems to be a high willingness to adopt changes if we can help make such changes easy and ensure that they reflect a true, single community consensus.

## Key Pillars of the Vision

* Each term has an [IRI](https://en.wikipedia.org/wiki/Internationalized_Resource_Identifier), such as "https://g.sentier.dev/models/Prelim/1.6/Kero%20Merox%20Unit". The IRI is the **only** way to refer to that term.
* Each IRI is a webpage which presents a human-friendly representation of all the data behind the term, including its preferred and alternative labels in multiple languages, description, position in a concept hierarchy, additional links for clarification, and correspondence with other terms in other concept hierarchies.
* Each IRI is also an API endpoint which allows for the same information as in the webpage to be retrieved for use by software.
* When possible, terms are defined hierarchically, with reference to parent and child concepts
* The extremely strong presumption is that terms come from existing standards whenever possible. Ideally these standards come from well-known standardization bodies.
* The glossary is *append-only* - data can be added but never removed. Both the webpage and API can access the glossary state at any historical time.
* The glossary is developed in an open and community-oriented process. Anyone can suggest changes, and discussion and resolution of such changes is done in the open. There are user guides and tutorials to encourage newcomers to help in glossary maintenance.
* Modifications to the glossary go through both an automated and manual review process. Possible changes are not reflected in the main glossary until review is completed, but these "branches" of the glossary can be used instead of the "main" branch.

## Differentiators

* Uses of IRIs means that no more string compatiblity checks and guarantees of automatic harmonization
* Provision of terms in multiple languages makes the glossary accessible to the broader world
* Open and community-friendly development process increases willingness of community to participate and maintain glossary
* Open and clearly defined license encourage institutions to use our data
* Clear versioning and links across versions make migrations much easier and more correct
* Hierarchical concept schemes allow narrow and broad matches, improving chances for automatic matching and allowing for search refinement

## Success Metrics

* Website and API usage statistics
* Number of support questions in community forum (want golden medium, not too few and not too many)
* Number of outside contributors
* Number of editors
* Number of LCA software systems which use our glossary as the default

## Conclusion

If successful, the glossary could revolutionize data exchange in life cycle assessment and industrial ecology as a whole. It would allow for much more automatic matching, allow practitioners to specify inputs correctly (instead of the lowest common denominator of a specific background database), and allow for the automatic creation of supply chains by models which can be built and operate automatically.
