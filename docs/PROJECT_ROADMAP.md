# Project Roadmap

This document is the concise implementation roadmap for Togetherly CloudSec Platform. The full project description and version scope are maintained in the repository README.

| Version | Focus | Key technologies | Exit outcome |
|---|---|---|---|
| V1 | Local assessment and security baseline | Python, STRIDE, OWASP, Zero Trust, Bandit, pip-audit | Local assessment engine, validated findings, remediation evidence, baseline report |
| V2 | Identity and access management | Microsoft Entra ID, OAuth/OIDC, SSO, Azure RBAC, Managed Identities, Key Vault, App Service or ACI | Tested identity integration and controlled Azure hosting environment |
| V3 | Infrastructure automation | Terraform, Bicep, GitHub Actions, VNet, NSG, ASG, Azure CLI/PowerShell | Reproducible infrastructure, CI/CD, network security |
| V4 | Security operations | Microsoft Sentinel, Defender for Cloud, Azure Monitor, Log Analytics, KQL | Tested telemetry, detections, investigation workflows |
| V5 | Enterprise security architecture | Azure Policy, Azure Backup, Recovery Services Vault, MCRA, Zero Trust | Governance assessment, tested recovery, final architecture |

## Execution order

Complete and verify each version's exit evidence before moving to the next. Future-version resources must not be deployed early merely to populate the repository.

## Current phase

V1 — Local Assessment & Security Baseline.

Existing application security groundwork has been performed, but the Python assessment engine and complete V1 deliverables remain in progress.
