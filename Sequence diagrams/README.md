# Sequnce diagrams

Selecting a product from natural text query:

```mermaid
sequenceDiagram
    User->>Frontend: Calculate the carbon footprint of a bike
    Frontend-->>SearchEngine: Glossary terms for "bike"
    SearchEngine-->>Frontend: List(terms)
    Frontend-->>User: Select the correct term
```

Running a calculation from the perspective of the orchestrator:

```mermaid
sequenceDiagram
    Frontend-->>Orchestrator: Calculate(impact category, product)
    Orchestrator-->>Glossary: Who produces product?
    Glossary-->>Orchestrator: Model reference
    Orchestrator-->>Runner: Start(model)
    Runner-->>Orchestrator: Ready
    Orchestrator-->>Runner: Apply(demand)
    Runner-->>Orchestrator: Return result object
```
