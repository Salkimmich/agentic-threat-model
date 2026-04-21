# Agentic Threat Modeling Guide

## 1) Define scope

- Describe the agent's objective and operating environment
- Enumerate components: model, memory, tools, orchestration, human oversight
- Define security objectives (confidentiality, integrity, availability, safety)

## 2) Identify assets and actors

- Assets: prompts, credentials, tool outputs, logs, model config
- Actors: end users, operators, maintainers, external systems, adversaries

## 3) Map trust boundaries

Capture where data or control crosses trust boundaries:

- User input to agent runtime
- Agent runtime to external tools/APIs
- Agent to persistent memory/state stores
- Human approval and override channels

## 4) Enumerate threats

Use STRIDE-inspired categories adapted for agentic systems:

- Spoofing (identity/session impersonation)
- Tampering (prompt/tool response manipulation)
- Repudiation (insufficient auditability)
- Information disclosure (secret leakage)
- Denial of service (resource exhaustion loops)
- Elevation of privilege (tool abuse, over-scoped permissions)

See [`../threat-catalog/llm-agent-threats.md`](../threat-catalog/llm-agent-threats.md).

## 5) Select mitigations

Prioritize controls by impact and effort:

- Principle of least privilege for tools and credentials
- Input/output validation and policy checks
- Human-in-the-loop approval for high-risk actions
- Isolation/sandboxing for external tool execution
- Monitoring, alerting, and tamper-evident logs

## 6) Record residual risk

Document accepted risk, ownership, review cadence, and rollback/escalation paths.

## 7) Review cadence

Re-run threat modeling when:

- New tools or memory layers are introduced
- Permission scopes change
- Major prompt/orchestration logic changes
- Security incidents occur
