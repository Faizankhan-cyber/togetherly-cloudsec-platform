# Togetherly CloudSec Platform

**A hands-on cloud security engineering project built around the Togetherly Workforce application.**

Togetherly CloudSec Platform is a long-term portfolio project to assess and secure an existing application, strengthen identity and access controls, automate Azure infrastructure, build threat detection, and design an enterprise-ready cloud security architecture.

The goal is to show employers practical engineering ability through working tools, secure configurations, infrastructure code, tests, diagrams, and clear technical reports.

> **Assess → Secure → Integrate → Automate → Detect → Improve**

## The application

The project uses Togetherly Workforce as its real-world case study.

| Layer | Current technology |
|---|---|
| Frontend | React, TypeScript, Vite |
| Authentication | Supabase Auth |
| Database and access control | Supabase PostgreSQL and Row Level Security |
| File storage and backend operations | Supabase Storage and Edge Functions |
| Hosting and CI/CD | Vercel, GitHub, GitHub Actions |

Azure will be introduced in controlled stages. The existing application will not be migrated without a clear technical reason.

## Five project versions

| Version | Main focus | Planned outcome |
|---|---|---|
| **V1: Security Foundation** | Python security assessment, application review, STRIDE, OWASP, Zero Trust | Local assessment tool, security findings, fixes, tests and baseline report |
| **V2: Identity & Cloud Security** | Microsoft Entra ID, OAuth/OIDC, SSO, Azure RBAC, Managed Identity, Key Vault | Tested identity design and controlled Azure hosting/integration |
| **V3: Infrastructure & DevSecOps** | Terraform, Bicep, Azure networking, GitHub Actions | Repeatable infrastructure, secure CI/CD and network controls |
| **V4: Security Operations** | Azure Monitor, Log Analytics, Microsoft Sentinel, KQL, Defender for Cloud | Log collection, detections, alerts and incident investigation exercises |
| **V5: Enterprise Architecture** | Azure Policy, governance, backup, disaster recovery, Zero Trust | Tested recovery plan, governance assessment and final architecture |

## Certification alignment

Certifications are learning milestones that support the project. They are not substitutes for building and testing the actual systems. The project will progress alongside the study roadmap.

| Certification milestone | Project connection |
|---|---|
| **DataCamp Python Fundamentals + Intermediate Python** | Prepare for the Python assessment engine in V1 |
| **AZ-900: Azure Fundamentals** | Azure concepts and services used from V2 onward |
| **GH-900: GitHub Foundations** | GitHub workflows, repository practices and collaboration across all versions |
| **AZ-104: Azure Administrator Associate** | Azure identity, resources, networking and operations in V2–V4 |
| **SC-500: Cloud and AI Security Engineer Associate** | Security controls and cloud protection across V2 and V4 |
| **HashiCorp Terraform Associate (004)** | Infrastructure as Code implementation in V3 |
| **AWS Cloud Practitioner (CLF-C02) + AWS Solutions Architect Associate (SAA-C03)** | Multi-cloud comparison and architecture knowledge, mainly V3 and V5 |
| **AZ-305: Azure Solutions Architect Expert** | Enterprise architecture decisions and final design in V5 |
| **AWS Certified Security – Specialty** | Advanced cloud security concepts supporting V4 and V5 |

### Planned order

- **Before / during V1:** Complete DataCamp Python Fundamentals and Intermediate Python; build working knowledge of Bash and PowerShell. Begin V1 locally.
- **By February 2027 target:** AZ-900, GH-900, AZ-104 and SC-500, following the planned study sequence. These support V2 and prepare for V3/V4.
- **BCA fourth semester:** JavaScript, AWS CLF-C02, AWS SAA-C03 and Terraform Associate (004). Apply the relevant learning to V3.
- **Final year:** AZ-305 and AWS Certified Security – Specialty. Use this advanced knowledge to complete and validate V4/V5.

Certification dates are targets, not claims of completion. Actual project work will be recorded separately from exam progress.

## How we will build it

- Inspect before changing anything.
- Work in small, testable steps using Git branches and pull requests.
- Use local or staging environments for experiments.
- Keep production data and services safe.
- Document findings, fixes, test results and design decisions.
- Never publish passwords, API keys, tokens, private keys or sensitive data.
- Estimate Azure costs before deployment and remove temporary resources after testing.

The project starts locally. Azure services such as Sentinel, Defender and Log Analytics will only be deployed when needed and after reviewing cost and licensing.

## Current status

**Current version: V1 — Security Foundation.**

Initial security groundwork has been completed on the Togetherly application, including reviews of GitHub security settings, Supabase authentication and RLS, storage, Edge Functions and deployment configuration. Selected improvements have been applied and documented.

The V1 Python assessment engine, full threat model, structured assessment and final baseline report are still to be built. V2–V5 are planned, not completed.

## Repository structure

```text
├── V1-security-foundation/
├── V2-identity-cloud-security/
├── V3-infrastructure-devsecops/
├── V4-security-operations/
├── V5-enterprise-architecture/
└── docs/
```

Folders and implementation files will be added as each stage begins.

## Links

- **Togetherly Workforce:** https://togetherly-tinyfish.vercel.app
- **Application source:** https://github.com/Faizankhan-cyber/togetherly-workforce

---

This is an independent educational and portfolio project. All security testing must be authorised and limited to systems and environments for which permission has been granted.
