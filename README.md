# Agentic Threat Model

Open-source documentation and templates for modeling threats in AI/LLM agent systems.

## Why this repository exists

Agentic systems introduce risks beyond traditional web/software threats, including prompt injection, tool misuse, data leakage, and unsafe autonomy. This repository provides a practical, repeatable way to model those risks and track mitigations.

## Scope

- Documentation-first project (no runtime code required)
- Initial guide focused on agentic/LLM threats
- Reusable templates for system context, trust boundaries, threats, and residual risk

## Quick start

1. Read [`docs/guides/agentic-threat-modeling-guide.md`](docs/guides/agentic-threat-modeling-guide.md).
2. Copy the files in [`docs/templates/`](docs/templates/) into your project workspace.
3. Populate threats using [`docs/threat-catalog/llm-agent-threats.md`](docs/threat-catalog/llm-agent-threats.md).
4. Open a pull request with improvements.

## Repository layout

- [`docs/README.md`](docs/README.md) - documentation index
- [`docs/guides/`](docs/guides/) - step-by-step methods
- [`docs/templates/`](docs/templates/) - worksheet templates
- [`docs/threat-catalog/`](docs/threat-catalog/) - starter threat lists

## Contributing and security

- Contribution guide: [`CONTRIBUTING.md`](CONTRIBUTING.md)
- Security reporting: [`SECURITY.md`](SECURITY.md)
- Code of conduct: [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md)

## License

Licensed under Apache-2.0. See [`LICENSE`](LICENSE).
