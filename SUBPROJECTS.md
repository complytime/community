# ComplyTime Subprojects

This document outlines the subprojects under the ComplyTime umbrella, their status, and contribution guidelines. Each subproject has its own maintainers, roadmap, and contribution guidelines while adhering to the overall ComplyTime [governance](./GOVERNANCE.md) and [code of conduct](./CODE_OF_CONDUCT.md).

## Subproject Maturity Levels

| Status | Description |
|--------|-------------|
| **🟢 Active** | Production-ready, actively maintained with regular releases |
| **🟡 Incubating** | Under active development, working toward stability |
| **🔵 Supporting** | Foundational/utility project, stable but lower release cadence |
| **⚪ Archived Or Empty** | Empty or no longer actively maintained, kept for historical reference |

## Current Subprojects

### complyctl

**Description**: A command-line tool for streamlining end-to-end compliance workflows on local systems.

**Status**: 🟢 Active
**Repository**: [complytime/complyctl](https://github.com/complytime/complyctl)
**Language**: Go | **License**: Apache-2.0

---

### complyscribe

**Description**: A workflow automation tool for compliance content authoring.

**Status**: 🟡 Incubating
**Repository**: [complytime/complyscribe](https://github.com/complytime/complyscribe)
**Language**: Python | **License**: Apache-2.0

---

### complytime-collector-components (ComplyBeacon)

**Description**: A policy-driven observability toolkit for compliance evidence collection, extending the OpenTelemetry standard.

**Status**: 🟡 Incubating
**Repository**: [complytime/complytime-collector-components](https://github.com/complytime/complytime-collector-components)
**Language**: Go | **License**: Apache-2.0

---

### complytime-collector-distro

**Description**: Pre-built OpenTelemetry Collector distribution for ComplyBeacon releases.

**Status**: ⚪ Empty
**Repository**: [complytime/complytime-collector-distro](https://github.com/complytime/complytime-collector-distro)
**License**: Apache-2.0

---

### org-infra

**Description**: Reusable workflows, shared configurations, and templates for the ComplyTime organization.

**Status**: 🟢 Active
**Repository**: [complytime/org-infra](https://github.com/complytime/org-infra)
**Language**: Python | **License**: Apache-2.0

---

### website

**Description**: The ComplyTime project website.

**Status**: ⚪ Empty
**Repository**: [complytime/website](https://github.com/complytime/website)

---

### .github

**Description**: Organization management via [Peribolos](https://docs.prow.k8s.io/docs/components/cli-tools/peribolos/).

**Status**: 🔵 Supporting
**Repository**: [complytime/.github](https://github.com/complytime/.github)

---

### community

**Description**: Community documentation including contributing guidelines, governance, and code of conduct.

**Status**: 🔵 Supporting
**Repository**: [complytime/community](https://github.com/complytime/community)
**License**: Apache-2.0

---

### gemara-content-service

**Description**: A content API service for [Gemara](https://github.com/ossf/gemara) — the GRC Engineering Model for Automated Risk Assessment. Naming not yet finalized.

**Status**: ⚪ Empty
**Repository**: [complytime/gemara-content-service](https://github.com/complytime/gemara-content-service)
**License**: Apache-2.0

---

### complytime-policies

**Description**: Engineering policies expressed in [Gemara](https://github.com/ossf/gemara) for the ComplyTime project.

**Status**: 🟡 Incubating
**Repository**: [complytime/complytime-policies](https://github.com/complytime/complytime-policies)
**License**: Apache-2.0

---

### compliance-to-policy-go

**Description**: Go framework for Compliance-to-Policy (C2P), bridging compliance requirements to policy enforcement.

**Status**: 🔵 Supporting
**Repository**: [complytime/compliance-to-policy-go](https://github.com/complytime/compliance-to-policy-go)
**Language**: Go | **License**: Apache-2.0
**Type**: Fork of [oscal-compass/compliance-to-policy-go](https://github.com/oscal-compass/compliance-to-policy-go)

---

### compliance-to-policy-plugins

**Description**: C2P plugins that integrate compliance-to-policy with ComplyTime tooling.

**Status**: 🟡 Incubating
**Repository**: [complytime/compliance-to-policy-plugins](https://github.com/complytime/compliance-to-policy-plugins)
**Language**: Go | **License**: Apache-2.0

---

### oscal-sdk-go

**Description**: Go SDK for working with OSCAL (Open Security Controls Assessment Language) documents.

**Status**: 🔵 Supporting
**Repository**: [complytime/oscal-sdk-go](https://github.com/complytime/oscal-sdk-go)
**Language**: Go | **License**: Apache-2.0
**Type**: Fork of [oscal-compass/oscal-sdk-go](https://github.com/oscal-compass/oscal-sdk-go)

---

### gemara-mcp-server

**Description**: An MCP server for automating the authoring of GRC Risk Assessment documentation in [Gemara](https://github.com/ossf/gemara).

**Status**: 🟡 Incubating
**Repository**: [complytime/gemara-mcp-server](https://github.com/complytime/gemara-mcp-server)
**Language**: Go | **License**: Apache-2.0

---

## Process for Adding New Subprojects

1. **Open a Proposal Issue** in the [community repository](https://github.com/complytime/community/issues) with:
   - Project name and description
   - Problem statement and goals
   - Proposed maintainers (minimum 2)
   - Technical architecture overview
   - Alignment with ComplyTime's mission

2. **Community Review**: The proposal will be open for community discussion for at least 2 weeks.

3. **TOC Approval**: The [Technical Oversight Committee](./GOVERNANCE.md) will vote on the proposal.

## Subproject Requirements

All subprojects must:

- Follow the ComplyTime [Code of Conduct](./CODE_OF_CONDUCT.md)
- Adhere to the [Contributing Guidelines](./CONTRIBUTING.md)
- Have at least two maintainers
- Maintain clear documentation
- Follow ComplyTime's licensing guidelines (Apache-2.0 preferred)

## Process for Archiving Subprojects

Subprojects may be archived when:

- No active maintainers remain after reasonable recruitment efforts
- The project no longer aligns with ComplyTime's direction
- The project has been superseded by another solution
- A supermajority vote of the TOC approves archival

Archived projects remain available for reference but no longer receive updates or support.
