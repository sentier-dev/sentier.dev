# sentier.dev

Open infrastructure for quantitative sustainability assessment.

This repository is the planning and discussion home of the sentier.dev platform.
It holds no runnable code.

## What it is

- Product vision and requirements for the platform.
- Engineering decisions (ADRs) and the contributing guide.
- Architecture and sequence diagrams.
- Discussion templates for suggesting new data sources and models.

The platform is split into one repository per component.
`Engineering/ADRs/ADR_1_MultiRepo.md` explains why.

| Repository | Role |
|---|---|
| [sentier-vocab](https://github.com/sentier-dev/sentier-vocab) | Vocabulary terms and schemas |
| [sentier-inventory](https://github.com/sentier-dev/sentier-inventory) | Life cycle inventory datasets |
| [sentier-methods](https://github.com/sentier-dev/sentier-methods) | Impact assessment methods |
| [sentier-mappings](https://github.com/sentier-dev/sentier-mappings) | Cross-source mappings |
| [sentier-importers](https://github.com/sentier-dev/sentier-importers) | Imports external data into the repositories above |
| [sentier-brightway](https://github.com/sentier-dev/sentier-brightway) | Installs Sentier data into a Brightway project |

### Development philosophy

- Most content will come from volunteers, as in OpenStreetMap and Wikipedia.
- Our job is to make contributing easy and rewarding.
- The code is FOSS. Project and product management happen in the open too.
- Participation is governed by the code of conduct in `CODE_OF_CONDUCT.md`.

## Layout

```
sentier.dev/
├── Product/
│   ├── Glossary product vision statement.md
│   └── Glossary v1 product requirements.md
├── Engineering/
│   ├── CONTRIBUTING.md
│   └── ADRs/ADR_1_MultiRepo.md
├── Sequence diagrams/
│   ├── README.md
│   └── architecture.png
├── .github/DISCUSSION_TEMPLATE/
│   ├── data-suggestion.yml
│   └── model-suggestion.yml
├── CODE_OF_CONDUCT.md
└── LICENSE
```

The sequence diagrams in `Sequence diagrams/README.md` describe a design hypothesis, not the built system.

## Contributing

You want to contribute? That's awesome! We need your ideas, your energy, and your voice.

1. [Search the issues](https://github.com/sentier-dev/sentier.dev/issues?q=is%3Aissue) for a similar idea.
2. If you find one, check how it was resolved.
3. If not, open a new issue.
4. To suggest a data source or a model, use the discussion templates in `.github/DISCUSSION_TEMPLATE/`.
5. Follow the commit style in `Engineering/CONTRIBUTING.md`.

## Licensing

See `LICENSES`. Source code is MIT, other content is CC-BY.
