# V1 Progress Tracker · Security Foundation

**Status:** In progress  
**Rule:** Mark a task complete only when implementation, review, and required evidence exist in the repository.

## 1. Baseline and scope

- [x] Review GitHub security settings and repository controls
- [x] Review Supabase Auth, RLS, storage, Edge Functions, and deployment configuration
- [x] Record selected baseline improvements and live verification
- [ ] Document application assets, data flows, trust boundaries, and security assumptions
- [ ] Confirm authorised assessment scope and test environment

## 2. Assessment engine

- [ ] Define Python project structure and supported runtime
- [ ] Add configuration and safe target selection
- [ ] Implement read-only checks first
- [ ] Add structured finding model (ID, title, severity, evidence, impact, remediation, references)
- [ ] Add JSON output and a human-readable report
- [ ] Add unit tests and safe test fixtures

## 3. Threat modelling and review

- [ ] Complete STRIDE threat model
- [ ] Map relevant OWASP risks to application components
- [ ] Review authentication and session handling
- [ ] Review authorisation and database RLS assumptions
- [ ] Review storage and file upload boundaries
- [ ] Review Edge Functions and privileged operations
- [ ] Record risk rating, evidence, and recommended remediation

## 4. Remediation and validation

- [ ] Prioritise findings by severity and practical impact
- [ ] Create a remediation record for each accepted finding
- [ ] Implement approved fixes in a controlled branch/environment
- [ ] Add regression tests for each relevant fix
- [ ] Record before/after evidence without exposing sensitive data

## 5. V1 release gate

- [ ] Assessment engine runs from documented instructions
- [ ] Tests pass and test output is retained
- [ ] Threat model and application diagram reviewed
- [ ] Findings register and remediation status published
- [ ] Security baseline report completed
- [ ] Documentation reviewed for accuracy and sensitive data

## Evidence links

Store sanitised artefacts under [evidence/](../evidence/README.md). Link each completed task to its evidence or report before checking it off.

## Change log

| Date | Update |
|---|---|
| 2026-11-05 | Created the V1 task tracker and acceptance gates |
