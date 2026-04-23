# agentic-threat-model

[![CI](https://github.com/Salkimmich/agentic-threat-model/actions/workflows/ci.yml/badge.svg)](https://github.com/Salkimmich/agentic-threat-model/actions/workflows/ci.yml)
[![License: Apache-2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[![Last Commit](https://img.shields.io/github/last-commit/Salkimmich/agentic-threat-model)](https://github.com/Salkimmich/agentic-threat-model/commits/main)

Practitioner-grade threat modeling resources for agentic AI systems.
Built for security engineers, AI red teamers, and architects who need a structured
starting point grounded in realistic attack behavior.

## Why this repository exists

Most threat modeling guidance for AI remains either too generic to apply in real
reviews or too product-specific to reuse. This repository focuses on practical,
reusable patterns for deployed agentic systems: tool-using agents, orchestration
layers, memory-enabled assistants, and multi-agent pipelines.

It is designed for teams that need to move from "AI is risky" to concrete,
defensible security decisions with documented trade-offs.

## What this is

A docs-first threat modeling reference covering:

- **Threat taxonomy**: 50 attack patterns across 10 categories
- **Control mappings**: Prevent, detect, and respond controls with verification signals
- **Framework crosswalks**: OWASP LLM Top 10, MITRE ATLAS, and NIST AI RMF
- **Risk scoring**: Agentic Risk Score (ARS) rubric for triage and prioritization
- **Templates**: Threat model worksheets and submission templates for repeatable reviews

## What makes this different

- Focused on **deployed agentic systems**, not generic LLM safety discussions.
- Uses concrete threat patterns with preconditions and affected assets.
- Includes a lightweight but practical prioritization model (ARS).
- Maps directly to OWASP LLM Top 10, MITRE ATLAS, and NIST AI RMF.
- Includes reusable templates and worked examples for real review sessions.

## Show, don't tell

- Threat catalog sample: [`docs/threat-catalog/llm-agent-threats.md`](docs/threat-catalog/llm-agent-threats.md)
- Scored example: [`docs/examples/customer-support-agent-threat-model.md`](docs/examples/customer-support-agent-threat-model.md)
- Multi-agent example: [`docs/examples/multi-agent-tool-escalation-model.md`](docs/examples/multi-agent-tool-escalation-model.md)
- Submission format: [`docs/templates/threat-submission.md`](docs/templates/threat-submission.md)

## Quality and review standards

- Content changes are reviewed through pull requests with documented rationale.
- Markdown quality checks run in CI on pull requests and pushes to `main`.
- Repository links are validated in CI to catch stale references.
- New threat entries are expected to include realistic attack preconditions and
  evidence when possible.

## Assumptions and limitations

- Assumptions for this framework: [`ASSUMPTIONS.md`](ASSUMPTIONS.md)
- Known limitations and non-goals: [`LIMITATIONS.md`](LIMITATIONS.md)

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

## How to use this in practice

### 30-minute quick pass

1. Define system scope and trust boundaries.
2. Pick the 5 to 10 most likely threat patterns from the catalog.
3. Score each with ARS.
4. Assign one prevent and one detect control for the highest scores.
5. Record owners, due dates, and residual risks.

### Full review workflow

1. Run the guide end-to-end with engineering, security, and operations.
2. Build a complete threat table with assets, preconditions, and controls.
3. Prioritize remediation by ARS tier and business criticality.
4. Revisit the model when architecture, permissions, or tooling changes.

## Team adoption (30/60/90 days)

Adoption playbook: [`ROADMAP.md`](ROADMAP.md)

## Scope

This repository focuses on threats to **deployed agentic systems**:
runtime attacks, orchestration weaknesses, tool abuse, data exfiltration,
and supply chain compromise.

## Out of scope

- Model pretraining security internals and lab-only model research workflows
- Domain-specific legal or regulatory interpretations
- Incident response runbooks for a specific vendor platform

## Maintenance

Taxonomy updates are tracked in [`CHANGELOG.md`](CHANGELOG.md).
Contributions are reviewed through pull requests and threat submissions.

## Maintainer intent

This repository is maintained as a practitioner portfolio and community resource
for production-grade agentic AI threat modeling. The primary goal is to provide
material that security teams can apply directly in architecture reviews.

## Contributing

See [`CONTRIBUTING.md`](CONTRIBUTING.md). New catalog entries should use
[`docs/templates/threat-submission.md`](docs/templates/threat-submission.md).

## License

Apache-2.0. See [`LICENSE`](LICENSE).
