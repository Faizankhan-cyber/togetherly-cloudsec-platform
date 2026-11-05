# Security Policy

## Scope

This repository contains an educational cloud security engineering project. Security testing must be limited to:
- Code and infrastructure owned by the project.
- Togetherly environments for which explicit authorisation has been granted.
- Local, staging, or disposable lab resources.

Do not test unrelated systems or production services without written permission.

## Supported versions

| Version | Security support |
|---|---|
| Current development version on `main` | Active |
| Earlier project snapshots | Best effort; fixes are made on the current development line |

## Reporting a vulnerability

Please do not publish credentials, tokens, personal information, private evidence, or exploitable details in a public issue.

1. Use GitHub's **Report a vulnerability** option in the repository Security tab if private vulnerability reporting is available.
2. If that option is unavailable, contact the repository owner privately through GitHub.
3. Include the affected file or component, impact, reproduction steps, and any safe proof of concept.
4. Allow time for investigation and remediation before public disclosure.

Please do not include real customer or employee data in a report. Redact logs, screenshots, identifiers, and secrets.

## Response process

The maintainer will acknowledge reports when practical, assess severity and scope, reproduce the issue in a safe environment, and document the fix or mitigation. There is no guaranteed response-time SLA for this personal educational project.

## Safe testing rules

- Obtain permission before testing any system.
- Prefer local, staging, or disposable lab environments.
- Do not access, modify, or disclose another person's data.
- Do not commit secrets, private keys, service-role credentials, or sensitive Terraform state.
- Remove temporary cloud resources after testing and verify their deletion.

## Project status

Security controls and findings are documented as they are verified. A tool or planned control in the roadmap does not mean it has been deployed or validated.
