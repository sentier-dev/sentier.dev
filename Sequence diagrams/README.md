# Sequence diagrams

The diagrams were built with the following hypothesis as basis:

+ Orchestration service will launch containerization (docker/podman/runc) objects
+ models are serialized under a filesystem with standard structure:
```

models.sentier.dev
└── a_model_URI
    └── python
        ├── extract.py
        ├── load.py
        ├── prepare.py
        └── transform.py

```
+  The orchestrator has the responsibility of keeping track of the "graph" of models being called (to be returned after call)
+  The orchestrator has the responsibility of "calling" the other models (from the results above)
+  calling a model returns:
	- other necessary models
	- emissions

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
    participant Frontend
    participant Glossary
    participant Orchestrator
    participant Runner
    participant Log
    Frontend-->>Orchestrator: Calculate(impact category, product)
    Orchestrator-->>+Glossary: Who produces product?
    Glossary-->>-Orchestrator: Model reference
    Orchestrator-->>+Runner: Apply(demand)
    Runner-->>-Orchestrator: Return result object
    Orchestrator-->>Log: Write emissions and context from model
    Note right of Orchestrator: Decompose result object
    Orchestrator-->>+Glossary: Who produces dependent product 1? 
    Glossary-->>-Orchestrator: Model reference
    Orchestrator-->>+Runner: Apply(demand)
    Runner-->>-Orchestrator: Return result object
    Note right of Orchestrator: Iterate throughout supply chain
    Log-->>Orchestrator: Read graph structure
    Orchestrator-->>Frontend: Result report
```

Graph traversal:

```mermaid
sequenceDiagram
	participant Queue
	participant Orchestrator
	participant Runner
	Runner-->>Orchestrator: Return result object
    Note right of Orchestrator: Decompose result object
    Note right of Orchestrator: For demand in result
    Orchestrator->>Queue: Push demands
    Runner-->>Orchestrator: Ready signal
    Queue-->>Orchestrator: Pop most important demand
    Orchestrator-->>Runner: Apply(demand)
    Runner-->>Orchestrator: Return result object
    Note right of Orchestrator: Iterate
```
