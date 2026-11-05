# Togetherly CloudSec Platform

**A practical, five-stage cloud security engineering project built around the Togetherly Workforce application.**

Togetherly CloudSec Platform is a hands-on security engineering initiative to assess, harden, integrate, automate, monitor, and progressively evolve a real application toward an enterprise-style cloud security architecture.

The project combines application security, Python security automation, Microsoft Entra ID, Azure infrastructure, Infrastructure as Code (IaC), DevSecOps, security operations, governance, and resilience. It is designed to demonstrate practical engineering decisions and verifiable outcomes, not just a collection of cloud screenshots.

> **Project approach:** Assess it. Secure it. Integrate identity. Automate infrastructure. Detect threats. Prove resilience.

---

## Why this project exists

Modern applications depend on more than a secure login page. Their security depends on application design, identity, permissions, data access, secrets, infrastructure, deployment pipelines, monitoring, and recovery.

This project uses Togetherly Workforce as a practical case study. Each version adds a new layer of capability while preserving the lessons and evidence from earlier versions.

The intended portfolio outcome is a documented, testable body of work that demonstrates how a cloud security engineer approaches an application across its lifecycle.

## Project objectives

- Assess application architecture and identify security risks using recognised security methods.
- Build a Python-based local security assessment and reporting engine.
- Apply STRIDE threat modelling, OWASP guidance, and Zero Trust principles.
- Introduce Microsoft Entra ID and Azure identity controls.
- Deploy and manage cloud infrastructure using Terraform and Azure Bicep.
- Build CI/CD workflows with security and infrastructure validation.
- Collect and investigate cloud telemetry using Microsoft Sentinel and Azure monitoring services.
- Apply governance, backup, disaster recovery, and enterprise architecture practices.
- Publish evidence, test results, diagrams, and technical decisions throughout the project.

## Application under assessment

**Togetherly Workforce** is an existing workforce management application with roles such as Admin, Manager, HR, and Employee.

| Layer | Current technology |
|---|---|
| Frontend | React, TypeScript, Vite, Tailwind CSS |
| Authentication | Supabase Auth |
| Database | Supabase PostgreSQL with Row Level Security (RLS) |
| File storage | Supabase Storage |
| Server-side operations | Supabase Edge Functions |
| Current hosting | Vercel |
| Source control and CI | GitHub and GitHub Actions |

The existing application is the starting point, not a reason to migrate everything immediately. Azure hosting is introduced later as a controlled learning and integration environment. Any production migration must be justified by security, operational, and cost considerations.

## Five-version roadmap

### V1 — Local Assessment & Security Baseline

**Focus:** Security fundamentals, local assessment tooling, and threat modelling.

- Build a Python security assessment and reporting engine.
- Map application architecture, data flows, assets, and trust boundaries.
- Apply STRIDE threat modelling.
- Assess relevant OWASP Top 10 risks.
- Evaluate Zero Trust principles: Verify Explicitly, Least Privilege, and Assume Breach.
- Use Bandit for Python static analysis.
- Use pip-audit for Python dependency vulnerability checks.
- Add appropriate JavaScript/TypeScript dependency and source checks.
- Validate and prioritise security findings, remediate selected issues, and retest.
- Produce evidence-based reports and a documented security baseline.

**Exit evidence:** Working local assessment tooling, architecture and threat-model diagrams, validated findings, remediation tests, and a V1 security baseline report.

### V2 — Identity & Access Management (Cloud Onboarding)

**Focus:** Enterprise identity and controlled Azure onboarding.

- Microsoft Entra ID tenant, users, groups, and enterprise applications.
- App registrations and OAuth 2.0 / OpenID Connect integration.
- Single Sign-On (SSO) exploration and implementation.
- Identity mapping and application role mapping.
- Azure Role-Based Access Control (RBAC) and least privilege.
- System-assigned and user-assigned Managed Identities.
- Azure Key Vault for secrets, keys, and certificates.
- Temporary Togetherly hosting on Azure App Service or Azure Container Instances to test integration.

**Important design requirement:** Entra ID authentication does not replace application authorisation. Togetherly's application permissions and Supabase RLS must continue to enforce access to application data. The integration approach must be validated against the existing Supabase authentication architecture before implementation.

**Exit evidence:** Identity architecture, app registration configuration, tested authentication flow, role/permission mapping, Managed Identity and Key Vault demonstrations, and a controlled Azure hosting test.

### V3 — Infrastructure Automation (IaC & Networking)

**Focus:** Repeatable infrastructure, CI/CD, and network security.

- Terraform as the primary Infrastructure as Code tool.
- Azure Bicep as a complementary native Azure IaC tool.
- Reusable modules, variables, outputs, and secure state handling.
- GitHub Actions for validation, security checks, and controlled deployment workflows.
- Azure Virtual Networks (VNets), subnets, Network Security Groups (NSGs), and Application Security Groups (ASGs).
- Azure CLI and Azure PowerShell for administration.
- Cost-aware deployment and teardown procedures.

**Exit evidence:** Version-controlled Terraform modules, at least one Bicep module, CI/CD workflows, network diagrams, validated deployments, and teardown documentation.

### V4 — Security Operations (Telemetry & Threat Detection)

**Focus:** Cloud visibility, detection engineering, and incident response.

- Microsoft Sentinel for SIEM capabilities.
- Microsoft Defender for Cloud for cloud security posture and applicable workload protection.
- Azure Monitor and Log Analytics.
- Diagnostic settings and controlled log ingestion.
- Kusto Query Language (KQL) for investigation and detection queries.
- Analytics rules, alerting, incident investigation, and response playbooks.
- Safe simulations of suspicious activity to validate detections.

**Cost control:** Sentinel and Log Analytics costs can depend on ingestion, retention, and configuration. Use limited test data, review pricing before deployment, capture evidence, and remove temporary resources when testing is complete.

**Exit evidence:** Tested log collection, KQL query library, working detection examples, incident investigation notes, and a security operations report.

### V5 — Enterprise Security Architecture (Resilience & Governance)

**Focus:** Governance, recoverability, and final architecture validation.

- Azure Policy for governance and configuration enforcement.
- Azure Backup and Recovery Services Vault.
- Controlled backup and restore tests.
- Disaster recovery planning.
- Recovery Time Objective (RTO) and Recovery Point Objective (RPO) measurements based on actual tests.
- Microsoft Cybersecurity Reference Architecture (MCRA).
- Enterprise Zero Trust architecture assessment.
- Final application, identity, network, monitoring, governance, and recovery diagrams.

**Exit evidence:** Policy and compliance assessment, verified recovery evidence, documented RTO/RPO results, disaster recovery plan, and final enterprise security architecture.

---

## High-level architecture evolution

The architecture evolves across the versions:

1. **Starting point:** Togetherly frontend on Vercel, with Supabase Auth, PostgreSQL/RLS, Storage, and Edge Functions.
2. **Identity layer:** Microsoft Entra ID integration and Azure resource identity, while retaining application-level authorisation and database controls.
3. **Infrastructure layer:** Azure networking and repeatable Terraform/Bicep deployments, supported by GitHub Actions.
4. **Operations layer:** Azure Monitor, Log Analytics, Sentinel, and applicable Defender for Cloud capabilities.
5. **Enterprise layer:** Azure Policy, backup, recovery, governance, and documented Zero Trust architecture.

The final architecture will be documented with diagrams as each layer is implemented. This is a target architecture, not a claim that every component is currently deployed.

## Repository structure

The repository will keep all five versions in one project history:

```text
togetherly-cloudsec-platform/
├── README.md
├── V1-local-assessment-security-baseline/
│   ├── engine/
│   ├── assessments/
│   ├── tests/
│   ├── reports/
│   └── docs/
├── V2-identity-access-management/
│   ├── entra-id/
│   ├── rbac/
│   ├── managed-identities/
│   ├── key-vault/
│   └── hosting/
├── V3-infrastructure-automation/
│   ├── terraform/
│   ├── bicep/
│   ├── networking/
│   └── github-actions/
├── V4-security-operations/
│   ├── sentinel/
│   ├── defender/
│   ├── log-analytics/
│   ├── kql/
│   └── detections/
├── V5-enterprise-security-architecture/
│   ├── governance/
│   ├── backup-recovery/
│   ├── zero-trust/
│   └── architecture-diagrams/
└── docs/
    ├── project-roadmap/
    ├── architecture/
    ├── decisions/
    └── evidence/
```

The structure will be created progressively. Directories and components will be added when there is real content to put in them.

## Current project status

**Current phase: V1 — Local Assessment & Security Baseline.**

Preliminary security groundwork has already been performed on the existing Togetherly application, including reviews of GitHub security settings, Supabase RLS and authentication, storage configuration, Edge Functions, and Vercel deployment settings. Selected Supabase security improvements have been applied and documented separately.

The main V1 engineering deliverables are still in progress. In particular, the custom Python assessment engine, complete STRIDE model, structured OWASP assessment, local Zero Trust assessment, and final V1 baseline report have not yet been completed.

No Entra ID integration, Azure hosting migration, Terraform infrastructure, Sentinel deployment, or V2–V5 implementation is claimed as complete.

Progress will be updated only when work is implemented and verified.

## Development principles

- Inspect before changing; understand the existing system before modifying it.
- Work in small, reviewable steps.
- Keep the five-version roadmap intact; discuss scope changes before making them.
- Use feature branches and pull requests for meaningful changes.
- Test security controls and fixes; do not treat scanner output as proof by itself.
- Separate confirmed findings from suspected issues and false positives.
- Never test against systems or data without authorisation.
- Never commit API keys, passwords, tokens, certificates, service-role keys, or sensitive Terraform state.
- Prefer local or staging environments for experiments.
- Do not make destructive production changes without explicit approval and a verified recovery plan.
- Capture evidence at each milestone and document how results were verified.

## Azure budget and resource safety

The project uses an Azure for Students subscription with **$100 in credits**.

Cost controls are mandatory:

- Estimate service costs before deployment.
- Prefer free or low-cost options where suitable.
- Deploy only the resources needed for the current task.
- Use Terraform to make temporary environments reproducible and removable.
- Check Cost Management after deployments.
- Understand that stopping a resource does not necessarily stop every charge.
- Pay special attention to App Service, compute, Sentinel, Log Analytics ingestion/retention, Defender plans, and backup storage.
- Destroy temporary resources after collecting required evidence.
- Never deploy all project versions' infrastructure at once.

Pricing, licensing, and student eligibility must be checked at the time of implementation.

## Getting started — V1

V1 is designed to run locally and does not require Azure resources.

Prerequisites:
- Python 3
- Git
- Visual Studio Code
- Access to the authorised Togetherly source repository

Create and activate a virtual environment on Windows PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
```

The V1 tooling will be added incrementally. Bandit and pip-audit will be configured as part of the assessment workflow, with suitable JavaScript/TypeScript checks added for the frontend.

## Portfolio and professional value

This project is intended to demonstrate practical ability across:

- Application security and secure design.
- Python security tooling and automation.
- Threat modelling and vulnerability assessment.
- Microsoft Entra ID and cloud identity.
- Azure administration and access control.
- Terraform, Bicep, networking, and CI/CD.
- SIEM concepts, KQL, and detection engineering.
- Cloud governance, backup, and disaster recovery.
- Technical documentation, evidence, and engineering judgement.

The quality of the project will be demonstrated through reproducible implementations, test results, architecture decisions, and honest documentation—not by the number of technologies listed.

## Project links

- **Application under assessment:** https://togetherly-tinyfish.vercel.app
- **Application source repository:** https://github.com/Faizankhan-cyber/togetherly-workforce

## Disclaimer

This is an independent educational and portfolio project. All testing must be authorised and limited to systems and environments for which permission has been granted. Findings should be responsibly handled, and secrets or personal data must not be published.

---

**Project principle:** Build it. Secure it. Automate it. Monitor it. Prove that it works.
