# On the infamous monorepo vs multi-repo

## Context

We currently have a small development team spread through multiple projects and system components.
While we focus on building our whole product vertical we expect a lot of alignment is needed between different layers.
One of the key challenges is our APIs specifications and data schemas, which are prone to quick and breaking changes.
An important decision when it comes to codebase management and architecture is how to organize the different system components and shared libraries;
this document details our decision to follow a multi-repository approach.
This approach aligns with our long-term goals of building a scalable and maintainable product.

## Decision

We will adopt a multi-repository architecture, where each repository will house a distinct component, service, or bounded context within our software system.
This includes, among others, separate repositories for:

* **Custom data management flow:**  For focused development and evolution.
* **Contract specifications:**  For maintaining clear interface definitions and promoting contract-based design and testing.
* **Model and interface definition**: For declaring different computational models and communication interfaces

## Reasons

* **Maintainability:**  Smaller repositories will be easier to understand and manage as our codebase expands.
* **Flexibility:** This approach allows us to adopt the most appropriate technology for each component without being constrained by a quasi-monolithic structure.
* **Future-proofing:**  We anticipate growth and want to establish a scalable architecture that can accommodate it.
* **Onboarding:**  Focused documentation within each repository will simplify the onboarding process for new or temporary team members working on specific projects. 
* **Local Testing:**  Isolation of components in separate repositories will enable faster and more focused local testing, improving developer productivity.
* **Git Efficiency:** Smaller repositories will lead to low-complexity Git operations and a less cluttered commit history.
* **Simplified Merging:**  We'll avoid the complexity of merging large, unrelated changes that often occur in a monorepo.
* **Contract-Driven Development:** A dedicated repository for contract specifications will facilitate clear communication of interfaces between components, enabling better collaboration and independent development cycles.
* **Domain ownership**: As we want to have external contributors directly embedded across our products, having a multi-repo means they retain ownership of the specific repository processes.
* **Adhering to engineering best-practices**: Having multiple repositories makes it easier to systematically manage engineering best practices such as dependency pinning, testing and documentation.

## Consequences

* **Increased repositories:**  We will need to manage multiple repositories, potentially increasing operational overhead and dependency management.
* **Coordination:** We'll need to be mindful of communication and coordination between repositories, especially as our team grows.

## Mitigation Strategies

* **Automation:** We will invest in robust CI/CD pipelines and tooling to streamline management across repositories.
* **Clear Ownership:** Each repository will have a clearly defined owner, responsible for its maintenance and evolution.
* **Contract Testing:**  We'll implement automated contract tests to ensure that components adhere to their specified interfaces.
* **Versioning:** We'll establish clear versioning rules, following semantic versioning, for contract specifications to manage compatibility and change management.

## Alternatives Considered

* **Monorepo:**  While simpler initially, it could lead to major issues in scalability and flexibility, as well as to version control inefficiencies, merging challenges, and onboarding issues in the future.

## Decision Outcome

While a monorepo might seem appealing initially, we recognize the potential challenges it could pose as our codebase and team grow:

1. _From a design perspective_, having a multi-repository approach lends itself well to a service-oriented architecture and decreases onboarding time for targeted one-off projects.
2. _From a developer experience_, it reduces testing as well as local set-up time and reduces complexity in adhering to engineering best-practices.
3. _From a larger community perspective_, having dedicated repositories decreases documentation overload and allows for a quick exchange turnover. Sentier's foreseen organizational structure and institutional-oriented funding strategies also play a critical role here.

We believe that the benefits of multiple repositories, including improved maintainability, flexibility, onboarding, local testing, version control efficiency, simplified merging, and the ability to implement contract-driven development, outweigh the potential drawbacks.
