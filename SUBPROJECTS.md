# ComplyTime Subprojects

This document provides an overview of the subprojects under the ComplyTime umbrella. Each subproject has its own maintainers, roadmap, and contribution guidelines while adhering to the overall ComplyTime [governance](./GOVERNANCE.md) and [code of conduct](./CODE_OF_CONDUCT.md).

## Project Lifecycle

Subprojects follow a defined lifecycle to ensure quality and community alignment:

| Status | Description |
|--------|-------------|
| **🟢 Active** | Production-ready, actively maintained with regular releases |
| **🟡 Incubating** | Under active development, working toward stability |
| **🔵 Supporting** | Foundational/utility project, stable but lower release cadence |
| **⚪ Archived** | No longer actively maintained, kept for historical reference |

---

## Core Projects

These are the primary user-facing tools that form the backbone of the ComplyTime ecosystem.

### `complytime`

> **A command-line tool for streamlining end-to-end compliance workflows on local systems.**

| | |
|---|---|
| **Repository** | [github.com/complytime/complytime](https://github.com/complytime/complytime) |
| **Status** | 🟢 Active |
| **Language** | Go |
| **License** | Apache-2.0 |

The `complytime` CLI is the primary interface for users to interact with the ComplyTime platform. It orchestrates compliance validation, policy assessment, and reporting workflows.

**Key Features:**
- Compliance validation against OSCAL-based policies
- Integration with policy engines and evidence collectors
- Local and CI/CD workflow support

**Related Repositories:**

| Repository | Purpose |
|------------|---------|
| [compliance-to-policy-plugins](https://github.com/complytime/compliance-to-policy-plugins) | Plugin extensions for `complytime` |
| [complytime-policies](https://github.com/complytime/complytime-policies) | Engineering policies expressed in Gemara |

---

### `complyctl`

> **A command-line tool for streamlining end-to-end compliance workflows on local systems.**

| | |
|---|---|
| **Repository** | [github.com/complytime/complyctl](https://github.com/complytime/complyctl) |
| **Status** | 🟢 Active |
| **Language** | Go |
| **License** | Apache-2.0 |

A complementary CLI tool that provides additional compliance workflow capabilities.

---

### `complytime-collector-components`

> **A policy-driven observability toolkit for compliance evidence collection.**

| | |
|---|---|
| **Repository** | [github.com/complytime/complytime-collector-components](https://github.com/complytime/complytime-collector-components) |
| **Status** | 🟢 Active |
| **Language** | Go |
| **License** | Apache-2.0 |

Provides policy-driven observability capabilities, enabling continuous evidence collection and compliance posture monitoring.

**Key Features:**
- Real-time file and system observability
- Evidence collection for compliance audits
- Status reporting and alerting

**Related Repositories:**

| Repository | Purpose |
|------------|---------|
| [complytime-collector-distro](https://github.com/complytime/complytime-collector-distro) | Distribution packages for collector releases |

---

### `complyscribe`

> **A workflow automation tool for compliance content authoring.**

| | |
|---|---|
| **Repository** | [github.com/complytime/complyscribe](https://github.com/complytime/complyscribe) |
| **Status** | 🟢 Active |
| **Language** | Go |
| **License** | Apache-2.0 |

Complyscribe streamlines the creation and maintenance of compliance documentation, enabling workflow automation for compliance content authoring.

**Key Features:**
- Compliance content authoring workflows
- Document generation and management
- Integration with GRC standards

---

### `gemara-mcp-server`

> **An MCP server for automating the authoring of GRC Risk Assessment documentation.**

| | |
|---|---|
| **Repository** | [github.com/complytime/gemara-mcp-server](https://github.com/complytime/gemara-mcp-server) |
| **Status** | 🟡 Incubating |
| **Language** | Go |
| **License** | Apache-2.0 |

A Model Context Protocol (MCP) server that provides AI-assisted automation for authoring Governance, Risk, and Compliance (GRC) documentation.

**Key Features:**
- MCP protocol support for AI integrations
- GRC documentation automation
- Integration with Gemara tooling

---

### `gemara2oscal`

> **A transpiler for converting the Gemara logic format to OSCAL.**

| | |
|---|---|
| **Repository** | [github.com/complytime/gemara2oscal](https://github.com/complytime/gemara2oscal) |
| **Status** | 🟢 Active |
| **Language** | Go |
| **License** | Apache-2.0 |

Converts Gemara's domain-specific logic format into OSCAL (Open Security Controls Assessment Language) documents, enabling interoperability with OSCAL-based tooling.

---

## SDKs & Libraries

Foundational libraries that power the ComplyTime ecosystem.

### `oscal-sdk-go`

> **OSCAL SDK for the Go programming language.**

| | |
|---|---|
| **Repository** | [github.com/complytime/oscal-sdk-go](https://github.com/complytime/oscal-sdk-go) |
| **Status** | 🔵 Supporting |
| **Language** | Go |
| **License** | Apache-2.0 |
| **Upstream** | Fork of [gocomply/oscal](https://github.com/gocomply/oscal) |

Provides Go types, parsing, and validation for OSCAL (Open Security Controls Assessment Language) documents.

---

### `compliance-to-policy-go`

> **Compliance-to-Policy (C2P) framework in Go.**

| | |
|---|---|
| **Repository** | [github.com/complytime/compliance-to-policy-go](https://github.com/complytime/compliance-to-policy-go) |
| **Status** | 🔵 Supporting |
| **Language** | Go |
| **License** | Apache-2.0 |
| **Upstream** | Fork of [oscal-compass/compliance-to-policy](https://github.com/oscal-compass/compliance-to-policy) |

Bridges the gap between compliance requirements and policy administration, enabling automated policy generation from compliance controls.

---

### `compliance-to-policy-plugins`

> **Plugin repository for C2P extensions.**

| | |
|---|---|
| **Repository** | [github.com/complytime/compliance-to-policy-plugins](https://github.com/complytime/compliance-to-policy-plugins) |
| **Status** | 🔵 Supporting |
| **Language** | Go |
| **License** | Apache-2.0 |

Contains plugins that extend the capabilities of the `complytime` CLI and C2P framework.

---

### `compliance-to-policy-python`

> **Compliance-to-Policy (C2P) framework in Python.**

| | |
|---|---|
| **Repository** | [github.com/complytime/compliance-to-policy-python](https://github.com/complytime/compliance-to-policy-python) |
| **Status** | 🔵 Supporting |
| **Language** | Python |
| **License** | Apache-2.0 |
| **Upstream** | Fork |

Python implementation of the C2P framework for environments preferring Python tooling.

---

## Content & Policies

Repositories containing compliance content, policies, and security automation.

### `complytime-policies`

> **Repository for ComplyTime engineering policies expressed in Gemara.**

| | |
|---|---|
| **Repository** | [github.com/complytime/complytime-policies](https://github.com/complytime/complytime-policies) |
| **Status** | 🟢 Active |
| **License** | Apache-2.0 |

Contains the reference implementation of engineering policies that demonstrate ComplyTime's capabilities.

---

### `oscal-content`

> **OSCAL content repository with test data for ComplyTime.**

| | |
|---|---|
| **Repository** | [github.com/complytime/oscal-content](https://github.com/complytime/oscal-content) |
| **Status** | 🔵 Supporting |
| **License** | Apache-2.0 |

Provides OSCAL-formatted content and test data used for validation and testing across ComplyTime projects.

---

### `cac-content`

> **Security automation content in SCAP, Bash, Ansible, and other formats.**

| | |
|---|---|
| **Repository** | [github.com/complytime/cac-content](https://github.com/complytime/cac-content) |
| **Status** | 🔵 Supporting |
| **Language** | Shell |
| **License** | Various |
| **Upstream** | Fork of [ComplianceAsCode/content](https://github.com/ComplianceAsCode/content) |

Provides security automation content that can be leveraged by ComplyTime for compliance validation.

---

## Infrastructure & Tooling

Supporting infrastructure, distributions, and developer tooling.

### `org-infra`

> **Repository for reusable workflows, shared configurations, and organizational infrastructure.**

| | |
|---|---|
| **Repository** | [github.com/complytime/org-infra](https://github.com/complytime/org-infra) |
| **Status** | 🟢 Active |
| **License** | Apache-2.0 |

Contains reusable GitHub Actions workflows, shared CI/CD configurations, and infrastructure-as-code for the ComplyTime organization.

---

### `.github`

> **Organization-level GitHub configuration managed via Peribolos.**

| | |
|---|---|
| **Repository** | [github.com/complytime/.github](https://github.com/complytime/.github) |
| **Status** | 🔵 Supporting |
| **License** | Apache-2.0 |

Manages organization-level GitHub settings, default community health files, and team configurations using Peribolos.

---

### `complytime-collector-distro`

> **Distribution packages for collector releases.**

| | |
|---|---|
| **Repository** | [github.com/complytime/complytime-collector-distro](https://github.com/complytime/complytime-collector-distro) |
| **Status** | 🔵 Supporting |
| **License** | Apache-2.0 |

Contains release artifacts and distribution configurations for compliance collectors.

---

### `complytime-demos`

> **Automation and examples for demonstrating ComplyTime features.**

| | |
|---|---|
| **Repository** | [github.com/complytime/complytime-demos](https://github.com/complytime/complytime-demos) |
| **Status** | 🔵 Supporting |
| **Language** | Jinja |

Provides demo automation, examples, and reference implementations for showcasing ComplyTime capabilities.

---

### `baseline-demo`

> **A demonstration of C2P to assess a project against a compliance baseline.**

| | |
|---|---|
| **Repository** | [github.com/complytime/baseline-demo](https://github.com/complytime/baseline-demo) |
| **Status** | 🔵 Supporting |
| **License** | Apache-2.0 |

Demonstrates how to use Compliance-to-Policy (C2P) to assess projects against compliance baselines.

---

### `vagrant-boxes`

> **Automation for creating Vagrant boxes.**

| | |
|---|---|
| **Repository** | [github.com/complytime/vagrant-boxes](https://github.com/complytime/vagrant-boxes) |
| **Status** | 🔵 Supporting |
| **Language** | Shell |

Provides Vagrant box definitions and automation for development and testing environments.

---

### `creme-brulee`

> **Template repository for new ComplyTime projects.**

| | |
|---|---|
| **Repository** | [github.com/complytime/creme-brulee](https://github.com/complytime/creme-brulee) |
| **Status** | 🔵 Supporting |
| **License** | MIT |

A template repository used to bootstrap new projects with ComplyTime's standard structure, CI/CD configurations, and documentation templates.

---

## Community

### `community`

> **Community-related documents for the ComplyTime project.**

| | |
|---|---|
| **Repository** | [github.com/complytime/community](https://github.com/complytime/community) |
| **Status** | 🟢 Active |
| **License** | Apache-2.0 |

Contains governance documentation, contribution guidelines, membership information, and community processes.

---

## Adding or Archiving Subprojects

### Proposing a New Subproject

To propose a new subproject:

1. **Open a Proposal Issue** in the [community repository](https://github.com/complytime/community/issues) with:
   - Project name and description
   - Problem statement and goals
   - Proposed maintainers (minimum 2)
   - Technical architecture overview
   - Alignment with ComplyTime's mission

2. **Community Review**: The proposal will be open for community discussion for at least 2 weeks.

3. **TOC Approval**: The [Technical Oversight Committee](./GOVERNANCE.md) will vote on the proposal.

### Criteria for Subprojects

New subprojects should:

- Align with ComplyTime's mission of streamlining compliance workflows
- Have clear scope that complements existing projects without significant overlap
- Demonstrate community interest and potential for adoption
- Have committed maintainers willing to follow ComplyTime governance
- Follow ComplyTime's licensing guidelines (Apache-2.0 preferred)

### Archiving a Subproject

Subprojects may be archived when:

- No active maintainers remain after reasonable recruitment efforts
- The project no longer aligns with ComplyTime's direction
- The project has been superseded by another solution
- A supermajority vote of the TOC approves archival

Archived projects remain available for reference but no longer receive updates or support.

---

## Project Relationships

```
┌───────────────────────────────────────────────────────────────────────────────┐
│                            ComplyTime Ecosystem                               │
├───────────────────────────────────────────────────────────────────────────────┤
│                                                                               │
│  ┌─────────────────────────────────────────────────────────────────────────┐  │
│  │                           Core Tools                                    │  │
│  │                                                                         │  │
│  │  ┌────────────┐ ┌────────────┐ ┌─────────────────┐ ┌────────────────┐   │  │
│  │  │ complytime │ │  complyctl │ │   complyscribe  │ │ gemara-mcp-srv │   │  │
│  │  │    CLI     │ │    CLI     │ │Content Authoring│ │   AI Assist    │   │  │
│  │  └─────┬──────┘ └─────┬──────┘ └────────┬────────┘ └───────┬────────┘   │  │
│  │        │              │                 │                  │            │  │
│  │        └──────────────┼─────────────────┼──────────────────┘            │  │
│  │                       │                 │                               │  │
│  │  ┌────────────────────┴─────────────────┴────────────────────────────┐  │  │
│  │  │                    Observability                                  │  │  │
│  │  │  ┌──────────────────────────┐  ┌──────────────────────────────┐   │  │  │
│  │  │  │ collector-components     │  │    collector-distro          │   │  │  │
│  │  │  └──────────────────────────┘  └──────────────────────────────┘   │  │  │
│  │  └───────────────────────────────────────────────────────────────────┘  │  │
│  └─────────────────────────────────────────────────────────────────────────┘  │
│                                                                               │
│  ┌─────────────────────────────────────────────────────────────────────────┐  │
│  │                        SDKs & Libraries                                 │  │
│  │                                                                         │  │
│  │  ┌──────────────┐ ┌───────────────┐ ┌─────────────┐ ┌───────────────┐   │  │
│  │  │ oscal-sdk-go │ │   c2p-go      │ │ c2p-plugins │ │  c2p-python   │   │  │
│  │  └──────────────┘ └───────────────┘ └─────────────┘ └───────────────┘   │  │
│  │                                                                         │  │
│  │  ┌──────────────────────────────────────────────────────────────────┐   │  │
│  │  │                     gemara2oscal (transpiler)                    │   │  │
│  │  └──────────────────────────────────────────────────────────────────┘   │  │
│  └─────────────────────────────────────────────────────────────────────────┘  │
│                                                                               │
│  ┌─────────────────────────────────────────────────────────────────────────┐  │
│  │                       Content & Policies                                │  │
│  │                                                                         │  │
│  │  ┌────────────────────┐ ┌───────────────┐ ┌─────────────────────────┐   │  │
│  │  │ complytime-policies│ │ oscal-content │ │      cac-content        │   │  │
│  │  └────────────────────┘ └───────────────┘ └─────────────────────────┘   │  │
│  └─────────────────────────────────────────────────────────────────────────┘  │
│                                                                               │
│  ┌─────────────────────────────────────────────────────────────────────────┐  │
│  │                       Infrastructure                                    │  │
│  │                                                                         │  │
│  │  ┌──────────┐ ┌─────────┐ ┌──────────────┐ ┌───────────┐ ┌───────────┐  │  │
│  │  │ org-infra│ │ .github │ │vagrant-boxes │ │   demos   │ │  template │  │  │
│  │  └──────────┘ └─────────┘ └──────────────┘ └───────────┘ └───────────┘  │  │
│  └─────────────────────────────────────────────────────────────────────────┘  │
│                                                                               │
└───────────────────────────────────────────────────────────────────────────────┘
```

---

## Repository Summary

| Category | Repository | Status | Description |
|----------|------------|--------|-------------|
| **Core** | [complytime](https://github.com/complytime/complytime) | 🟢 Active | Main CLI for compliance workflows |
| **Core** | [complyctl](https://github.com/complytime/complyctl) | 🟢 Active | CLI for compliance workflows |
| **Core** | [complytime-collector-components](https://github.com/complytime/complytime-collector-components) | 🟢 Active | Policy-driven observability toolkit |
| **Core** | [complyscribe](https://github.com/complytime/complyscribe) | 🟢 Active | Compliance content authoring |
| **Core** | [gemara-mcp-server](https://github.com/complytime/gemara-mcp-server) | 🟡 Incubating | MCP server for GRC automation |
| **Core** | [gemara2oscal](https://github.com/complytime/gemara2oscal) | 🟢 Active | Gemara to OSCAL transpiler |
| **SDK** | [oscal-sdk-go](https://github.com/complytime/oscal-sdk-go) | 🔵 Supporting | OSCAL SDK for Go |
| **SDK** | [compliance-to-policy-go](https://github.com/complytime/compliance-to-policy-go) | 🔵 Supporting | C2P framework in Go |
| **SDK** | [compliance-to-policy-plugins](https://github.com/complytime/compliance-to-policy-plugins) | 🔵 Supporting | C2P plugins |
| **SDK** | [compliance-to-policy-python](https://github.com/complytime/compliance-to-policy-python) | 🔵 Supporting | C2P framework in Python |
| **Content** | [complytime-policies](https://github.com/complytime/complytime-policies) | 🟢 Active | Engineering policies |
| **Content** | [oscal-content](https://github.com/complytime/oscal-content) | 🔵 Supporting | OSCAL test data |
| **Content** | [cac-content](https://github.com/complytime/cac-content) | 🔵 Supporting | Security automation content |
| **Infra** | [org-infra](https://github.com/complytime/org-infra) | 🟢 Active | Reusable workflows & configs |
| **Infra** | [.github](https://github.com/complytime/.github) | 🔵 Supporting | Org-level GitHub config |
| **Infra** | [complytime-collector-distro](https://github.com/complytime/complytime-collector-distro) | 🔵 Supporting | Collector distributions |
| **Infra** | [complytime-demos](https://github.com/complytime/complytime-demos) | 🔵 Supporting | Demo automation |
| **Infra** | [baseline-demo](https://github.com/complytime/baseline-demo) | 🔵 Supporting | C2P baseline demo |
| **Infra** | [vagrant-boxes](https://github.com/complytime/vagrant-boxes) | 🔵 Supporting | Vagrant automation |
| **Infra** | [creme-brulee](https://github.com/complytime/creme-brulee) | 🔵 Supporting | Project template |
| **Community** | [community](https://github.com/complytime/community) | 🟢 Active | Community docs |

---

## Getting Help
- **Bug Reports**: File issues in the relevant project repository
- **Security Issues**: See [SECURITY.md](./SECURITY.md)