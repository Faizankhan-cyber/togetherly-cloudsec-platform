# Project Evidence

This folder stores sanitised evidence that supports implementation and review of each project version.

## Folder layout

- `architecture/` — architecture diagrams, data-flow views, and design decisions.
- `assessments/` — assessment summaries, threat models, and findings registers.
- `tests/` — test reports and validation output.
- `remediation/` — remediation notes and before/after verification.

## Evidence rules

1. Never commit passwords, API keys, access tokens, private keys, service-role credentials, or Terraform state.
2. Never commit real employee/customer information, personal data, private logs, or unredacted screenshots.
3. Use synthetic examples and redact identifiers, hostnames, email addresses, and resource IDs where appropriate.
4. Include the date, project version, environment type (local/staging/lab), test/tool version, and result.
5. Link evidence to the relevant task in the V1 progress tracker.
6. Do not describe a control as fixed or verified unless the evidence supports that claim.

## Suggested evidence record

```text
Title:
Project version:
Date:
Environment:
Objective:
Method:
Result:
Limitations:
Related finding/task:
Redactions applied:
```
