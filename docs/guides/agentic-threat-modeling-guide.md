# Agentic Threat Modeling Guide

This guide is intentionally practical. Use it in a working session with engineering, security, and whoever owns operations.

## 1) Define scope

- State what the agent is allowed to do and where it runs.
- List components: model, memory, tools, orchestration, human review path.
- Agree on security goals (confidentiality, integrity, availability, safety).

## 2) Identify assets and actors

- Assets: prompts, credentials, tool outputs, logs, model configuration.
- Actors: users, operators, maintainers, external systems, and likely adversaries.

## 3) Map trust boundaries

Document every place where data or control crosses a trust boundary:

- User input -> agent runtime
- Agent runtime -> external tools/APIs
- Agent -> persistent memory/state store
- Human approval and override channels

## 4) Enumerate threats

Use the catalog categories in [`../threat-catalog/llm-agent-threats.md`](../threat-catalog/llm-agent-threats.md):

- Prompt injection
- Tool and function abuse
- Memory and context manipulation
- Agent identity and trust
- Orchestration and control flow
- Data exfiltration
- Supply chain
- Denial of service
- Output manipulation and integrity
- Privilege escalation and scope creep

## 5) Select mitigations

Start with high-impact controls that are cheap to implement:

- Principle of least privilege for tools and credentials
- Input/output validation and policy checks
- Human-in-the-loop approval for high-risk actions
- Isolation/sandboxing for external tool execution
- Monitoring, alerting, and tamper-evident logs

For detailed controls, use the control mapping section in the threat catalog and ensure each threat has at least one prevent and one detect control.

## 6) Risk Assessment: Agentic Risk Score (ARS)

ARS is a lightweight scoring model for prioritization in agentic systems.
It complements, rather than replaces, broader enterprise risk methods.

Score each threat on five factors from 1 to 3:

| Factor | 1 (Low) | 2 (Medium) | 3 (High) |
|--------|---------|------------|----------|
| Reach (R) | Single component impact | Crosses one trust boundary | Crosses multiple boundaries / external systems |
| Autonomy (A) | Human approves each action | Exception-based human review | Fully autonomous execution |
| Exploitability (E) | Specialist skill needed | Moderate skill with tooling | Widely accessible techniques |
| Impact (I) | Limited and reversible | Significant operational impact | Severe or irreversible impact |
| Detectability (D) | Easily detected by standard controls | Detectable with tuned monitoring | Hard to detect without specialized analysis |

`ARS = R + A + E + I + D`

| Score | Tier | Suggested action |
|-------|------|------------------|
| 5 to 7 | Low | Track in backlog; review at next cycle |
| 8 to 10 | Medium | Assign owner; remediate within 90 days |
| 11 to 13 | High | Escalate; remediate within 30 days |
| 14 to 15 | Critical | Block or isolate affected component until fixed |

Reference: [`../scoring/agentic-risk-score.md`](../scoring/agentic-risk-score.md)

## 7) Record residual risk

Write down what risk is accepted, who owns it, and when it will be reviewed again.

## 8) Review cadence

Revisit the model when:

- New tools or memory layers are added
- Permission scopes change
- Prompt or orchestration logic changes materially
- You have a security incident or near miss
