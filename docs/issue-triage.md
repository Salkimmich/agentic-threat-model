# Issue Triage Guide

Use this guide to keep issue handling consistent and transparent.

## Priority labels

- `priority:P0` - Immediate attention required
- `priority:P1` - High priority, next planned cycle
- `priority:P2` - Medium priority, backlog candidate
- `priority:P3` - Low priority, opportunistic improvements

## Severity labels

- `severity:critical` - Could cause unsafe guidance or serious operational risk
- `severity:high` - Material quality/security impact with likely downstream effects
- `severity:medium` - Meaningful quality gap or inconsistency
- `severity:low` - Minor quality issue, typo, or editorial cleanup

## Type labels

- `type:bug` - Defect in docs, templates, or process
- `type:enhancement` - Improvement to existing content/process
- `type:new-threat` - Proposal for new threat pattern or taxonomy entry
- `type:governance` - Policy, process, or maintainer model change

## Triage workflow

1. Confirm issue scope and expected behavior.
2. Apply one type label, one severity label, and one priority label.
3. Link related references (issue, PR, advisory, or source).
4. Decide disposition: fix now, schedule, request clarification, or close.
5. Record rationale when closing without implementation.
