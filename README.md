# agentic-threat-model

Practitioner-grade threat modeling resources for agentic AI systems.
Built for security engineers, AI red teamers, and architects who need a structured
starting point grounded in realistic attack behavior.

## What this is

A docs-first threat modeling reference covering:

- **Threat taxonomy**: 50 attack patterns across 10 categories
- **Control mappings**: Prevent, detect, and respond controls with verification signals
- **Framework crosswalks**: OWASP LLM Top 10, MITRE ATLAS, and NIST AI RMF
- **Risk scoring**: Agentic Risk Score (ARS) rubric for triage and prioritization
- **Templates**: Threat model worksheets and submission templates for repeatable reviews

## Who this is for

- Security architects designing or reviewing agentic AI deployments
- Product security teams adding AI-specific threats to existing libraries
- Red teams building test plans for tool-using and multi-agent systems
- Compliance and GRC teams mapping AI threats to governance frameworks

## Quick start

1. Read the guide: [`docs/guides/agentic-threat-modeling-guide.md`](docs/guides/agentic-threat-modeling-guide.md)
2. Review the catalog: [`docs/threat-catalog/llm-agent-threats.md`](docs/threat-catalog/llm-agent-threats.md)
3. Score threats with ARS: [`docs/scoring/agentic-risk-score.md`](docs/scoring/agentic-risk-score.md)
4. Record decisions using templates in [`docs/templates/`](docs/templates/)

## Scope

This repository focuses on threats to **deployed agentic systems**:
runtime attacks, orchestration weaknesses, tool abuse, data exfiltration,
and supply chain compromise.

## Maintenance

Taxonomy updates are tracked in [`CHANGELOG.md`](CHANGELOG.md).
Contributions are reviewed through pull requests and threat submissions.

## Contributing

See [`CONTRIBUTING.md`](CONTRIBUTING.md). New catalog entries should use
[`docs/templates/threat-submission.md`](docs/templates/threat-submission.md).

## License

Apache-2.0. See [`LICENSE`](LICENSE).
