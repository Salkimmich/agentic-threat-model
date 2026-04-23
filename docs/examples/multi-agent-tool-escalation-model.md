# Worked Example: Multi-Agent Tool Escalation

This example focuses on permission boundaries and escalation risks in a
multi-agent architecture.

## System context

A workflow orchestration platform uses:

- Planner agent: decomposes user goals into steps
- Research agent: gathers external and internal context
- Execution agent: performs tool actions in internal systems
- Approval agent: routes high-risk actions to a human reviewer

Tools include:

- Internal ticketing API
- CRM update API
- Billing adjustment API
- Knowledge base retriever

## Security goals

- Prevent unauthorized billing and account modification actions
- Preserve decision integrity across agent handoffs
- Ensure high-risk actions require explicit approval
- Detect and contain suspicious cross-agent behavior

## Key trust boundaries

1. User input to planner agent
2. Inter-agent message channel between planner/research/execution
3. Execution agent to privileged tool APIs
4. Approval agent to human decision channel

## Threat shortlist and ARS scoring

| Threat ID | Scenario | R | A | E | I | D | ARS | Tier |
|-----------|----------|---|---|---|---|---|-----|------|
| ATM-IT-03 | Research agent forges privileged caller lineage in handoff | 3 | 2 | 2 | 3 | 2 | 12 | High |
| ATM-TF-05 | Safe-seeming tool calls chain into unauthorized billing changes | 3 | 3 | 2 | 3 | 2 | 13 | High |
| ATM-PE-01 | Execution agent gradually expands scopes beyond approved envelope | 3 | 3 | 2 | 3 | 2 | 13 | High |
| ATM-OC-05 | Planner inserts hidden high-risk step between approved actions | 2 | 3 | 2 | 3 | 2 | 12 | High |
| ATM-DE-01 | Cross-agent context leak exposes sensitive customer metadata | 2 | 2 | 2 | 3 | 2 | 11 | High |

## Priority controls by threat

### ATM-IT-03 (Trust chain spoofing)

- Prevent: sign inter-agent messages with verifiable identity claims
- Detect: alert on attestation failures and caller lineage mismatches
- Respond: quarantine untrusted agent instance and revoke credentials

### ATM-TF-05 (Tool chaining escalation)

- Prevent: evaluate composed plans against a policy engine before execution
- Detect: monitor multi-step tool chains for privilege boundary crossings
- Respond: stop workflow and require manual replay from safe checkpoint

### ATM-PE-01 (Scope expansion)

- Prevent: enforce immutable scope envelope per workflow run
- Detect: flag scope change requests that exceed policy baseline
- Respond: deny expansion and trigger security review ticket

## Residual risk handling

- Residual risk accepted for moderate false-positive rates in chain anomaly
  detection for the first release quarter.
- Owner: Security Engineering Manager.
- Review trigger: any change to tool permissions, token scopes, or orchestrator policy.

## Validation checklist

- [x] Inter-agent trust boundaries identified and documented
- [x] High-tier threats have prevent/detect/respond controls
- [x] Scope and identity controls mapped to specific threats
- [x] Residual risk owner and re-evaluation trigger recorded
