# Worked Example: Customer Support Agent

This worked example shows how to apply the guide, catalog, and ARS scoring in
an employer-realistic scenario.

## System context

An enterprise customer support agent can:

- Read support tickets from an internal system
- Query account metadata from a CRM API
- Draft responses for human review
- Escalate high-risk cases to a human operator

The system uses:

- Hosted LLM endpoint
- Orchestration service
- Ticketing API tool
- CRM API tool
- Long-term memory store for prior ticket summaries

## Security goals

- Protect customer data confidentiality
- Preserve ticket decision integrity
- Prevent unauthorized actions in connected tools
- Maintain service availability during abuse attempts

## Trust boundaries

1. User input to agent runtime
2. Agent runtime to tool APIs
3. Agent runtime to memory store
4. Agent output to human approver

## Threat shortlist and ARS scoring

| Threat ID | Scenario | R | A | E | I | D | ARS | Tier |
|-----------|----------|---|---|---|---|---|-----|------|
| ATM-PI-02 | Web lookup result contains hidden instructions that alter tool behavior | 2 | 2 | 2 | 3 | 2 | 11 | High |
| ATM-TF-01 | Agent invokes CRM write endpoint outside approved support scope | 3 | 2 | 2 | 3 | 2 | 12 | High |
| ATM-DE-02 | Sensitive ticket notes are included in outbound API payloads | 2 | 2 | 2 | 3 | 3 | 12 | High |
| ATM-DS-02 | Prompt sequence causes repeated tool retries and quota exhaustion | 2 | 3 | 2 | 2 | 2 | 11 | High |
| ATM-MC-01 | Poisoned knowledge article drives incorrect account actions | 2 | 2 | 2 | 2 | 2 | 10 | Medium |

## Prioritized controls

### ATM-PI-02 (High)

- Prevent: isolate untrusted tool output from instruction channel
- Detect: alert on instruction-like tokens in retrieval/tool content
- Respond: terminate run and preserve execution trace for review

### ATM-TF-01 (High)

- Prevent: enforce per-tool, per-operation authorization policy
- Detect: log and alert on denied tool calls and scope mismatch attempts
- Respond: disable agent write actions until policy review completes

### ATM-DE-02 (High)

- Prevent: outbound payload policy checks for sensitive data classes
- Detect: monitor egress for unusual payload size and sensitive patterns
- Respond: revoke API token, quarantine session, notify incident response

## Residual risk decisions

- Accept medium risk for ATM-MC-01 for one quarter due to migration timeline.
- Owner: Product Security Lead.
- Next review date: 90 days from publication or earlier if memory pipeline changes.

## Validation checklist

- [x] Threats mapped to system trust boundaries
- [x] ARS scoring rationale documented
- [x] At least one prevent and one detect control per high-tier threat
- [x] Residual risk owner and review date recorded

## Notes

Use this as a reference format, not as a fixed template. Adjust tool set,
threat selection, and controls to match your environment and risk appetite.
