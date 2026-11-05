<!-- PROJECT LOGO -->
<p align="center">
  <img src="assets/cloudsec-logo.svg" alt="Togetherly CloudSec Platform" width="760">
</p>

<h1 align="center">Togetherly CloudSec Platform</h1>
<p align="center"><strong>A hands-on cloud security engineering project built around the Togetherly Workforce application.</strong></p>

<p align="center">
  <a href="https://github.com/Faizankhan-cyber/togetherly-cloudsec-platform"><img src="https://img.shields.io/github/last-commit/Faizankhan-cyber/togetherly-cloudsec-platform?style=for-the-badge&color=3976d8" alt="Last commit"></a>
  <a href="https://github.com/Faizankhan-cyber/togetherly-cloudsec-platform/issues"><img src="https://img.shields.io/github/issues/Faizankhan-cyber/togetherly-cloudsec-platform?style=for-the-badge&color=2596be" alt="Issues"></a>
  <a href="LICENSE"><img src="https://img.shields.io/github/license/Faizankhan-cyber/togetherly-cloudsec-platform?style=for-the-badge&color=2e9d72" alt="License"></a>
  <img src="https://img.shields.io/badge/Status-V1%20in%20progress-8b5cf6?style=for-the-badge" alt="Project status">
</p>

<p align="center">
  <a href="#project-overview">Overview</a> ·
  <a href="#architecture">Architecture</a> ·
  <a href="#project-roadmap">Roadmap</a> ·
  <a href="#certification-roadmap">Certifications</a> ·
  <a href="docs/V1_PROGRESS.md">V1 progress</a>
</p>

---

## Project overview

Togetherly CloudSec Platform is a long-term portfolio project focused on assessing and securing the existing **Togetherly Workforce** application, then gradually extending it with cloud identity, infrastructure automation, threat detection, and enterprise security controls.

The goal is to demonstrate practical engineering through working tools, secure configurations, infrastructure code, tests, architecture diagrams, and clear technical reports.

**Assess → Secure → Integrate → Automate → Detect → Improve**

### Why this project?

- Uses a real application as the security case study.
- Connects application security with cloud security and operations.
- Builds practical evidence through code, tests, reports, and documented decisions.
- Follows a staged path instead of moving everything to the cloud at once.
- Connects each project stage to the skills being developed through certifications.

## Architecture

The diagram separates the **existing application** from the **planned security engineering layers**. Azure services and the Python assessment engine are planned additions, not claims about the current production deployment.

```mermaid
flowchart TB
    subgraph APP["Existing Togetherly Workforce"]
      U["Users and workforce roles"]
      FE["React · TypeScript · Vite"]
      AUTH["Supabase Auth"]
      DB[("Supabase PostgreSQL · RLS")]
      ST["Supabase Storage"]
      EF["Supabase Edge Functions"]
      HOST["Vercel hosting"]
      U --> FE
      FE --> AUTH
      FE --> DB
      FE --> ST
      FE --> EF
      FE --> HOST
    end

    subgraph V1["V1 · Security Foundation"]
      PY["Python security assessment engine"]
      TH["STRIDE threat model · OWASP review"]
      FIND["Findings · remediation · tests · report"]
      PY --> TH --> FIND
    end

    subgraph CLOUD["Planned cloud security layers · V2–V5"]
      ENTRA["Microsoft Entra ID · OAuth/OIDC"]
      AZ["Azure RBAC · Key Vault · networking"]
      IAC["Terraform · Bicep · GitHub Actions"]
      SOC["Azure Monitor · Log Analytics · Sentinel · KQL"]
      GOV["Policy · governance · backup · recovery"]
      ENTRA --> AZ --> IAC --> SOC --> GOV
    end

    GH["GitHub repository · issues · pull requests · CI"]
    GH -. source and change control .-> V1
    GH -. automation workflows .-> IAC
    APP -. authorised assessment scope .-> PY
    FIND --> GH
```

See the [architecture source and design notes](docs/architecture/system-context.md) for scope, trust boundaries, and planned integrations.

## Project roadmap

| Version | Focus | Planned engineering outcome |
|:--:|---|---|
| **V1** | **Security Foundation** | Python assessment tool, application review, STRIDE threat model, OWASP checks, findings, fixes, and baseline report |
| **V2** | **Identity & Cloud Security** | Microsoft Entra ID, OAuth/OIDC, SSO, Azure RBAC, Managed Identity, and Key Vault |
| **V3** | **Infrastructure & DevSecOps** | Terraform, Bicep, Azure networking, GitHub Actions, and secure CI/CD |
| **V4** | **Security Operations** | Azure Monitor, Log Analytics, Microsoft Sentinel, KQL, Defender for Cloud, and incident investigation |
| **V5** | **Enterprise Architecture** | Azure Policy, governance, backup and recovery, disaster recovery, and Zero Trust architecture |

### Version details

<details>
<summary><strong>V1 · Security Foundation</strong></summary>

Build a local Python security assessment engine, map the application architecture, perform STRIDE threat modelling, review relevant OWASP risks, validate findings, and document remediation.
</details>
<details>
<summary><strong>V2 · Identity & Cloud Security</strong></summary>

Design and test Microsoft Entra ID integration, OAuth/OIDC, application role mapping, Azure RBAC, Managed Identities, and Key Vault. Application-level authorisation and database Row Level Security must remain in place.
</details>
<details>
<summary><strong>V3 · Infrastructure & DevSecOps</strong></summary>

Create repeatable infrastructure using Terraform and Bicep, build Azure networking controls, and add GitHub Actions validation and controlled deployment workflows.
</details>
<details>
<summary><strong>V4 · Security Operations</strong></summary>

Build log collection and KQL investigations, then add Sentinel detections, alerting, and incident response exercises. Review service costs before enabling paid ingestion or security plans.
</details>
<details>
<summary><strong>V5 · Enterprise Architecture</strong></summary>

Complete governance, Azure Policy, backup and restore testing, disaster recovery planning, Zero Trust assessment, and final architecture documentation.
</details>

The detailed stage gates and certification mapping are in [PROJECT_ROADMAP.md](docs/PROJECT_ROADMAP.md).

## V1 progress

<sub>Live checklist: update this as implementation and evidence are completed.</sub>

- [x] Initial review of GitHub security settings, Supabase Auth/RLS, storage, Edge Functions, and deployment configuration
- [x] Document selected baseline improvements and live verification
- [ ] Map the full application architecture and trust boundaries
- [ ] Build the Python security assessment engine
- [ ] Complete the STRIDE threat model and relevant OWASP review
- [ ] Produce structured findings with severity, evidence, and remediation
- [ ] Validate fixes with repeatable tests
- [ ] Publish the V1 security baseline report

See [V1_PROGRESS.md](docs/V1_PROGRESS.md) for task-level acceptance criteria. V2–V5 remain planned.

## Certification roadmap

Certifications support the learning behind each version. They do **not** count as project completion by themselves.

| Target period | Certification / learning | Project connection |
|---|---|---|
| Preparation | DataCamp Python Fundamentals + Intermediate Python | V1 assessment engine |
| Preparation | Bash and PowerShell skills | V1 automation and V2/V3 administration |
| By February 2027 target | **AZ-900** · Azure Fundamentals | Azure foundations for V2–V5 |
| By February 2027 target | **GH-900** · GitHub Foundations | Repository workflows and collaboration |
| By February 2027 target | **AZ-104** · Azure Administrator Associate | V2 identity, V3 networking, V4 operations |
| By February 2027 target | **SC-500** · Cloud and AI Security Engineer Associate | V2 cloud security and V4 operations |
| BCA fourth semester | JavaScript | Application and web security knowledge |
| BCA fourth semester | **AWS CLF-C02** · Cloud Practitioner | Multi-cloud foundations |
| BCA fourth semester | **AWS SAA-C03** · Solutions Architect Associate | Architecture decisions in V3/V5 |
| BCA fourth semester | **Terraform Associate (004)** | V3 Infrastructure as Code |
| Final year | **AZ-305** · Azure Solutions Architect Expert | V5 enterprise architecture |
| Final year | **AWS Certified Security – Specialty** | Advanced cloud security for V4/V5 |

**Planning note:** These are target milestones, not claims that the exams have already been passed. Dates may change with exam availability and college schedules.

## Technology stack

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Microsoft_Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white" alt="Microsoft Azure">
  <img src="https://img.shields.io/badge/Microsoft_Entra_ID-5E5E5E?style=flat-square&logo=microsoft&logoColor=white" alt="Microsoft Entra ID">
  <img src="https://img.shields.io/badge/Terraform-844FBA?style=flat-square&logo=terraform&logoColor=white" alt="Terraform">
  <img src="https://img.shields.io/badge/Bicep-0078D4?style=flat-square&logo=microsoftazure&logoColor=white" alt="Bicep">
  <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" alt="GitHub Actions">
  <img src="https://img.shields.io/badge/Microsoft_Sentinel-5E5E5E?style=flat-square&logo=microsoft&logoColor=white" alt="Microsoft Sentinel">
</p>

The existing Togetherly Workforce application currently uses:

| Layer | Technology |
|---|---|
| Frontend | React, TypeScript, Vite |
| Authentication | Supabase Auth |
| Database and access control | Supabase PostgreSQL and Row Level Security |
| Storage and backend operations | Supabase Storage and Edge Functions |
| Hosting and CI/CD | Vercel, GitHub, GitHub Actions |

Azure services will be introduced in controlled stages. The existing application will not be migrated without a clear technical reason and a reviewed implementation plan.

## Evidence and documentation

Project evidence is organised by type under [evidence/](evidence/README.md):

- Architecture diagrams and design decisions
- Security assessment reports and findings
- Test results and validation output
- Remediation records and verification

Only sanitised, non-sensitive evidence belongs in this repository. Never commit real user data, credentials, tokens, private keys, or unredacted production logs.

## Engineering principles

- Inspect before changing anything.
- Work in small, testable steps and use Git branches and pull requests.
- Prefer local or staging environments for experiments.
- Protect production data and services.
- Record findings, fixes, test results, and design decisions.
- Never commit passwords, API keys, tokens, private keys, or sensitive data.
- Estimate Azure costs before deployment and remove temporary resources after testing.

## Project links

- **Case-study application:** [Togetherly Workforce](https://togetherly-tinyfish.vercel.app/)
- **Application source:** [togetherly-workforce](https://github.com/Faizankhan-cyber/togetherly-workforce)
- **Detailed project and certification roadmap:** [PROJECT_ROADMAP.md](docs/PROJECT_ROADMAP.md)
- **Security policy:** [SECURITY.md](SECURITY.md)
- **V1 progress tracker:** [V1_PROGRESS.md](docs/V1_PROGRESS.md)
- **Architecture design:** [system-context.md](docs/architecture/system-context.md)

---

<p align="center">
  <strong>Built as a practical cloud security engineering portfolio project.</strong><br>
  <sub>Learning, building, testing, documenting, and improving one version at a time.</sub>
</p>

> This is an independent educational and portfolio project. Security testing must be authorised and limited to systems and environments for which permission has been granted.
