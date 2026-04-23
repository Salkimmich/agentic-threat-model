# Agentic Risk Score (ARS)

The Agentic Risk Score (ARS) is a lightweight threat-prioritization model for
agentic AI systems.

## Why ARS

Traditional software scoring models often miss two key properties of agentic systems:

- **Autonomy**: agents may execute actions without per-action approval
- **Reach**: agents can traverse trust boundaries through tools and integrations

## Factors

Score each factor from 1 (low) to 3 (high):

| Factor | Question | 1 | 2 | 3 |
|--------|----------|---|---|---|
| Reach (R) | How far can this attack propagate? | Single component | Crosses one boundary | Crosses multiple boundaries/external systems |
| Autonomy (A) | How independently can the agent act? | Human approves each action | Human reviews by exception | Fully autonomous |
| Exploitability (E) | How hard is it to exploit? | Specialized skill required | Moderate skill/tooling | Low skill/public techniques |
| Impact (I) | What is worst-case impact? | Limited, recoverable | Significant business impact | Severe/irreversible impact |
| Detectability (D) | How hard is detection? | Standard controls catch it | Requires tuned monitoring | Requires specialized forensics |

## Formula

`ARS = R + A + E + I + D`

## Tiers

| ARS | Tier | Recommended action |
|-----|------|--------------------|
| 5 to 7 | Low | Document and review next cycle |
| 8 to 10 | Medium | Assign owner and remediate within 90 days |
| 11 to 13 | High | Escalate and remediate within 30 days |
| 14 to 15 | Critical | Block deployment or isolate component pending immediate remediation |

## Example scored threats

| Threat ID | R | A | E | I | D | ARS | Tier |
|-----------|---|---|---|---|---|-----|------|
| ATM-PI-02 | 2 | 3 | 2 | 3 | 3 | 13 | High |
| ATM-TF-04 | 3 | 2 | 2 | 3 | 2 | 12 | High |
| ATM-SC-04 | 3 | 3 | 1 | 3 | 2 | 12 | High |
| ATM-DE-02 | 2 | 2 | 2 | 2 | 3 | 11 | High |
| ATM-MC-02 | 1 | 2 | 3 | 2 | 2 | 10 | Medium |
