# LLM Agent Threat Catalog (Starter)

## Prompt and context attacks

- Prompt injection through untrusted content
- Indirect prompt injection via retrieved documents or web pages
- Instruction hierarchy confusion leading to policy bypass

## Tooling and action risks

- Over-privileged tool credentials
- Unsafe tool invocation from malformed model output
- SSRF/path traversal/command injection through tool parameters

## Data protection risks

- Secret leakage in prompts, logs, or traces
- Cross-tenant data exposure in memory/retrieval
- Sensitive output disclosure to unauthorized users

## Integrity and abuse risks

- Hallucinated actions recorded as factual outcomes
- Workflow manipulation causing unauthorized transactions
- Feedback-loop self-amplification and denial of service

## Governance and oversight risks

- Missing approvals for high-impact operations
- Incomplete audit trails and repudiation gaps
- Drift between documented controls and deployed behavior
