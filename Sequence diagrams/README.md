# Sequnce diagrams

Selecting a product from natural text query

```mermaid

sequenceDiagram
    User->>Frontend: Please calculate the carbon footprint of a bike
    Frontend-->>SearchEngine: Glossary terms for "bike"
    SearchEngine-->>Frontend: List(terms)
    Frontend-->>User: Please select the term you mean
```