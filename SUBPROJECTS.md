# ComplyTime Subprojects

This document provides an overview of the subprojects under the ComplyTime umbrella. Each subproject has its own maintainers, roadmap, and contribution guidelines while adhering to the overall ComplyTime [governance](./GOVERNANCE.md) and [code of conduct](./CODE_OF_CONDUCT.md).

## Project Lifecycle

Subprojects follow a defined lifecycle to ensure quality and community alignment:

| Status | Description |
|--------|-------------|
| **🟢 Active** | Production-ready, actively maintained with regular releases |
| **🟡 Incubating** | Under active development, working toward stability |
| **🔵 Supporting** | Foundational/utility project, stable but lower release cadence |
| **⚪ Archived Or Empty** | Empty or No longer actively maintained, kept for historical reference |

---

## Core Projects

These are the primary user-facing tools that form the backbone of the ComplyTime ecosystem.

### `complyctl`

> **Leverages OSCAL to perform compliance assessment activities, using plugins for each stage of the lifecycle.**

| | |
|---|---|
| **Repository** | [github.com/complytime/complyctl](https://github.com/complytime/complyctl) |
| **Status** | 🟢 Active |
| **Language** | Go |
| **License** | Apache-2.0 |
| **Badges** | [OpenSSF Best Practices](https://www.bestpractices.dev/projects/9761), [OpenSSF Scorecard](https://scorecard.dev/viewer/?uri=github.com/complytime/complyctl), [SonarCloud](https://sonarcloud.io/summary/new_code?id=rh-psce_complyctl) |

The `complyctl` CLI is the primary interface for compliance assessment using OSCAL and a plugin architecture.

**Commands:**
- `list` — Show available frameworks
- `info <framework-id>` — Display framework/control/rule/parameter details
- `plan <framework-id>` — Create OSCAL Assessment Plan (supports `--scope-config` customization)
- `generate` — Generate plugin-specific policy artifacts
- `scan` — Execute PVP plugins, create Assessment Results (`--with-md` for Markdown)

📖 [Installation](https://github.com/complytime/complyctl/blob/main/docs/INSTALLATION.md) | [Quick Start](https://github.com/complytime/complyctl/blob/main/docs/QUICK_START.md) | [Plugin Guide](https://github.com/complytime/complyctl/blob/main/docs/PLUGIN_GUIDE.md)

---

### `complytime-collector-components` (ComplyBeacon)

> **An open-source observability toolkit designed to collect, normalize, and enrich compliance evidence, extending the OpenTelemetry (OTEL) standard.**

| | |
|---|---|
| **Repository** | [github.com/complytime/complytime-collector-components](https://github.com/complytime/complytime-collector-components) |
| **Status** | 🟡 Incubating |
| **Language** | Go |
| **License** | Apache-2.0 |

⚠️ All components are under initial development and are **not** ready for production use.

ComplyBeacon bridges the gap between raw policy scanner output and modern logging pipelines, providing a unified, enriched, and auditable data stream for security and compliance analysis.

**Components:**
- **ProofWatch** — Instrumentation library that emits pre-normalized compliance evidence as OpenTelemetry log streams
- **Beacon** — Custom OpenTelemetry Collector distribution that receives log records from ProofWatch
- **TruthBeam** — Custom OpenTelemetry Collector processor that enriches log records with compliance and risk data
- **Compass** — Central enrichment service providing risk, threat, and compliance framework attributes

**Related Repositories:**

| Repository | Purpose |
|------------|---------|
| [complytime-collector-distro](https://github.com/complytime/complytime-collector-distro) | Distribution packages for Beacon collector releases |

---

### `complyscribe`

> **A CLI tool that assists users in leveraging Compliance-Trestle in CI/CD workflows for OSCAL formatted compliance content management.**

| | |
|---|---|
| **Repository** | [github.com/complytime/complyscribe](https://github.com/complytime/complyscribe) |
| **Status** | 🟡 Incubating |
| **Language** | Go |
| **License** | Apache-2.0 |

⚠️ Currently under initial development. APIs may change incompatibly from one commit to another.

ComplyScribe integrates with [Compliance-Trestle](https://github.com/oscal-compass/compliance-trestle) to manage OSCAL content in CI/CD pipelines.

**Available Commands:**
- `autosync` — Sync trestle-generated Markdown to OSCAL JSON
- `rules-transform` — Transform rules YAML to OSCAL Component Definition
- `create compdef` — Create new OSCAL Component Definition
- `create ssp` — Create new OSCAL System Security Plan
- `sync-upstreams` — Sync upstream OSCAL content from git repos
- `sync-cac-content` — Transform CaC content to OSCAL models
- `sync-oscal-content` — Sync OSCAL models to CaC content

Also available as GitHub Actions. Supports GitHub and GitLab CI.

---

### `gemara-mcp-server`

> **A Model Context Protocol (MCP) server for [Gemara](https://github.com/ossf/gemara) — the GRC Engineering Model for Automated Risk Assessment.**

| | |
|---|---|
| **Repository** | [github.com/complytime/gemara-mcp-server](https://github.com/complytime/gemara-mcp-server) |
| **Status** | 🟡 Incubating |
| **Language** | Go |
| **License** | Apache-2.0 |

⚠️ **Prototype implementation.** The API, behavior, and data structures may change without notice.

This MCP server enables AI assistants to help users create and manage Gemara artifacts through a standardized interface.

**Features:**
- **Storage & Validation** — Store and validate Layer 1-3 artifacts (Guidance, Controls, Policies)
- **Query & Discovery** — List, search, and retrieve artifacts
- **Scoping & Applicability** — Find artifacts applicable to policy scopes
- **File Loading** — Load artifacts from files

**Related:** [Gemara (OSSF)](https://github.com/ossf/gemara), [Model Context Protocol](https://modelcontextprotocol.io/)

---

### `gemara2oscal`

> **A library for translating Gemara (GRC Engineering Model for Automated Risk Assessment) to OSCAL with support for OSCAL Compass extensions.**

| | |
|---|---|
| **Repository** | [github.com/complytime/gemara2oscal](https://github.com/complytime/gemara2oscal) |
| **Status** | 🟡 Incubating |
| **Language** | Go |
| **License** | Apache-2.0 |

⚠️ **For experimentation purposes only.**

Translates Gemara artifacts to OSCAL (Open Security Controls Assessment Language) documents, with support for OSCAL Compass extensions.

---

## SDKs & Libraries

Foundational libraries that power the ComplyTime ecosystem.

### `oscal-sdk-go`

> **Complements the compliance-trestle SDK by providing the core SDK functionality in Go.**

| | |
|---|---|
| **Repository** | [github.com/complytime/oscal-sdk-go](https://github.com/complytime/oscal-sdk-go) |
| **Status** | 🟡 Incubating |
| **Language** | Go |
| **License** | Apache-2.0 |
| **Type** | Fork |
| **Upstream** | [oscal-compass/oscal-sdk-go](https://github.com/oscal-compass/oscal-sdk-go) |

⚠️ Currently under initial development. APIs may change incompatibly.

**Supported Functionality:**
- OSCAL Types with Basic Trestle Extensions ✓
- OSCAL Schema Validation ✓
- Multiple Parameters per Rule ✓
- OSCAL to OSCAL Transformation ✓

**SDK Concepts:** Extensions, Rules, Settings

Leverages [`go-oscal`](https://github.com/defenseunicorns/go-oscal) for Go types.

---

### `compliance-to-policy-go`

> **Bridges Compliance as Code (OSCAL) and Policy as Code used by Policy Validation Points (PVP).**

| | |
|---|---|
| **Repository** | [github.com/complytime/compliance-to-policy-go](https://github.com/complytime/compliance-to-policy-go) |
| **Status** | 🔵 Supporting |
| **Language** | Go |
| **License** | Apache-2.0 |
| **Type** | Fork |
| **Upstream** | [oscal-compass/compliance-to-policy](https://github.com/oscal-compass/compliance-to-policy) (CNCF Sandbox) |

Compliance-to-Policy (C2P) generates policies in native PVP format from OSCAL Component Definitions and produces OSCAL Assessment Results from PVP assessment results. Originally created by IBM.

**CLI Commands:**
- `oscal2policy` — Transform OSCAL to policy artifacts
- `result2oscal` — Transform policy results to OSCAL Assessment Results
- `oscal2posture` — Generate Compliance Posture from OSCAL

**Supported Policy Engines:**
- [Kyverno](https://kyverno.io/) (Kubernetes)
- [Open Cluster Management Policy Framework](https://open-cluster-management.io/)

**Versions:** v1 (stable), v2 on main branch (experimental, APIs may change)

---

### `compliance-to-policy-plugins`

> **C2P/ComplyTime plugins that are not delivered in the core repository.**

| | |
|---|---|
| **Repository** | [github.com/complytime/compliance-to-policy-plugins](https://github.com/complytime/compliance-to-policy-plugins) |
| **Status** | 🔵 Supporting |
| **Language** | Go |
| **License** | Apache-2.0 |

Contains additional C2P plugins for policy engine integrations.

**Available Plugins:**
- [opa-plugin](https://github.com/complytime/compliance-to-policy-plugins/tree/main/opa-plugin) — Plugin for Open Policy Agent (OPA)

---

### `compliance-to-policy-python`

> **Bridges Compliance as Code (OSCAL) and Policy as Code used by Policy Validation Points (PVP) — Python implementation.**

| | |
|---|---|
| **Repository** | [github.com/complytime/compliance-to-policy-python](https://github.com/complytime/compliance-to-policy-python) |
| **Status** | 🔵 Supporting |
| **Language** | Python |
| **License** | Apache-2.0 |
| **Type** | Fork |
| **Upstream** | [oscal-compass/compliance-to-policy](https://github.com/oscal-compass/compliance-to-policy) (CNCF Sandbox) |

C2P generates policies from OSCAL Component Definitions and produces OSCAL Assessment Results from PVP results. Can be used as CLI or Python library. Originally created by IBM.

**Supported Policy Engines:**
- [Kyverno](https://kyverno.io/) (Kubernetes)
- [Open Cluster Management Policy Framework](https://open-cluster-management.io/)
- [Auditree](https://auditree.github.io/) (REST API-based resources)

**Roadmap:** OPA/Gatekeeper, Ansible

---

## Content & Policies

Repositories containing compliance content, policies, and security automation.

### `complytime-policies`

> **CALM (Common Architecture Language Model) architectures, standards, and controls for the ComplyTime ecosystem.**

| | |
|---|---|
| **Repository** | [github.com/complytime/complytime-policies](https://github.com/complytime/complytime-policies) |
| **Status** | 🟢 Active |
| **License** | Apache-2.0 |

Demonstrates integration of [CALM](https://github.com/finos/calm-cli) architectures with Gemara compliance policies.

**Contents:**
- **CALM Architecture** — ComplyTime deployment patterns
- **CALM Patterns** — Deployment patterns that validate required components
- **CALM Standards** — Custom standards for node/relationship metadata and Gemara policy inclusion
- **Control Requirements** — Gemara assessment requirements mapped to CALM control requirements

---

### `oscal-content`

> **An OSCAL content repository with test data for ComplyTime.**

| | |
|---|---|
| **Repository** | [github.com/complytime/oscal-content](https://github.com/complytime/oscal-content) |
| **Status** | ⚪ Empty |

⚠️ This repository is currently empty (placeholder).

---

### `cac-content`

> **Security policy content for various platforms (RHEL, Fedora, Ubuntu, Debian, SLES, etc.) in SCAP, Ansible, and Bash formats.**

| | |
|---|---|
| **Repository** | [github.com/complytime/cac-content](https://github.com/complytime/cac-content) |
| **Status** | 🔵 Supporting |
| **Language** | YAML, Python, Shell |
| **License** | Various |
| **Type** | Fork |
| **Upstream** | [ComplianceAsCode/content](https://github.com/ComplianceAsCode/content) |

Fork of the ComplianceAsCode project (formerly SCAP Security Guide). Creates security content in multiple formats from OpenControl-inspired YAML rules.

**Output Formats:**
- **SCAP** — XCCDF, OVAL, SCAP source data streams
- **Ansible** — Playbooks for compliance check and remediation
- **Bash** — Scripts for machine compliance

**Scan Targets:** Bare-metal, VMs, VM images, containers, container images

📖 [Documentation](https://complianceascode.readthedocs.io/) | [Online Workshops](https://github.com/ComplianceAsCode/content/blob/master/docs/workshop/README.adoc)

---

## Infrastructure & Tooling

Supporting infrastructure, distributions, and developer tooling.

### `org-infra`

> **Reusable workflows, shared configurations, and templates for the ComplyTime organization.**

| | |
|---|---|
| **Repository** | [github.com/complytime/org-infra](https://github.com/complytime/org-infra) |
| **Status** | 🟢 Active |
| **Language** | Python |
| **License** | Apache-2.0 |

Centrally manages **pre-vetted, security-hardened CI/CD pipeline steps** for consistency across all repositories.

**Contents:**
- **Reusable Workflows** — CI checks, dependency review, vulnerability scans, Gemini AI code review
- **Templates** — PR templates, Issue templates (bug report, feature request)
- **Config Files** — `.golangci.yml`, `.mega-linter.yml`, `.yamllint.yml`, `ruff.toml`, `commitlint.config.js`
- **Sync Script** — Python script integrated with Peribolos for repository consistency

---

### `.github`

> **Applies Peribolos to manage the ComplyTime GitHub organization.**

| | |
|---|---|
| **Repository** | [github.com/complytime/.github](https://github.com/complytime/.github) |
| **Status** | 🔵 Supporting |
| **License** | Apache-2.0 |

Uses [Peribolos](https://docs.prow.k8s.io/docs/components/cli-tools/peribolos/) (from Kubernetes Prow) to manage organization members, teams, and repository settings via configuration as code.

**Prerequisites:** Go, GitHub App with user access token (device flow enabled)

---

### `complytime-collector-distro`

> **Repository for beacon collector releases.**

| | |
|---|---|
| **Repository** | [github.com/complytime/complytime-collector-distro](https://github.com/complytime/complytime-collector-distro) |
| **Status** | 🔵 Supporting |
| **License** | Apache-2.0 |

Distribution repository for ComplyBeacon collector releases. Currently minimal (LICENSE only).

---

### `complytime-demos`

> **Automation and examples used to demo ComplyTime features (complyctl, complyscribe, ComplyBeacon).**

| | |
|---|---|
| **Repository** | [github.com/complytime/complytime-demos](https://github.com/complytime/complytime-demos) |
| **Status** | 🔵 Supporting |
| **Language** | Jinja, Shell |

Base for complyctl and complyscribe demos using Vagrant (VMs) + Ansible (configuration).

**Contents:**
- `base_vms/` — Vagrant instructions for Fedora, RHEL9 demo VMs
- `base_ansible_env/` — Ansible playbooks, inventory, templates
- Automated demos: `demo_complyctl_fedora.yml`, `run_complybeacon_fedora.yml`
- `CONTENT_TRANSFORMATION.md` — Examples for trestle-bot OSCAL content generation

---

### `baseline-demo`

> **Demonstrates using compliance-to-policy to automate evidence generation for [OSPS Baseline](https://baseline.openssf.org/versions/2025-02-25) controls.**

| | |
|---|---|
| **Repository** | [github.com/complytime/baseline-demo](https://github.com/complytime/baseline-demo) |
| **Status** | 🔵 Supporting |
| **Language** | Rego |
| **License** | Apache-2.0 |

Evaluates a GitHub Repository component using C2P + [Conforma](https://github.com/conforma) OPA plugin.

**Workflows:**
1. **Generate Policy** — Transforms Gemara Layers 2-4 → OSCAL Component Definition → OPA bundle (via c2pcli)
2. **Create Compliance Report** — Uses `snappy` + `ec validate` → OSCAL Assessment Results + Markdown report

**Contents:** `governance/` (Gemara content), `checks/opa/` (Rego policies), `policy.yaml` (Conforma config)

---

### `vagrant-boxes`

> **Automation for creating Vagrant Boxes for development, testing, and demo environments.**

| | |
|---|---|
| **Repository** | [github.com/complytime/vagrant-boxes](https://github.com/complytime/vagrant-boxes) |
| **Status** | 🔵 Supporting |
| **Language** | Shell |
| **Registry** | [complytime on HashiCorp Vagrant](https://portal.cloud.hashicorp.com/vagrant/discover/complytime) |

**Supported Providers:**
- libvirt (amd64)
- VirtualBox (arm64)

Build with `make build` (requires Vagrant + provider plugin on matching architecture).

---

### `creme-brulee`

> **Bite-sized ComplyTime 🍮 — Learn to use ComplyTime organization projects and tools.**

| | |
|---|---|
| **Repository** | [github.com/complytime/creme-brulee](https://github.com/complytime/creme-brulee) |
| **Status** | 🔵 Supporting |
| **License** | MIT |

A self-paced training course for Compliance Managers to learn about ComplyTime tools, OSCAL content workflows, Git flow, and Agile Authoring practices. The course takes approximately 2 hours to complete.

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

**Communication:**
- **Slack**: [complytime workspace](https://join.slack.com/t/complytime/shared_invite/zt-3icuo77ir-XynRgEh0S8_ycHHpNgth2A)
- **Mailing List**: [complytime@googlegroups.com](https://groups.google.com/g/complytime)
- **Meetings**: [Google Calendar](https://calendar.google.com/calendar/embed?src=f3702601238a1df31910d273cddf7597f4000aadbdf5338c66742eb2d2cfd408%40group.calendar.google.com&ctz=America%2FNew_York)

**Docs:** CONTRIBUTING.md, CODE_OF_CONDUCT.md, GOVERNANCE.md, MEMBERSHIP.md, MAINTAINERS.md, SECURITY.md

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
│  │  ┌────────────────┐ ┌─────────────────┐ ┌────────────────┐              │  │
│  │  │    complyctl   │ │   complyscribe  │ │ gemara-mcp-srv │              │  │
│  │  │    Main CLI    │ │Content Authoring│ │   AI Assist    │              │  │
│  │  └───────┬────────┘ └────────┬────────┘ └───────┬────────┘              │  │
│  │          │                   │                  │                       │  │
│  │          └───────────────────┼──────────────────┘                       │  │
│  │                              │                                          │  │
│  │  ┌───────────────────────────┴───────────────────────────────────────┐  │  │
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
│  │  │ org-infra│ │ .github │ │vagrant-boxes │ │   demos   │ │ training  │  │  │
│  │  └──────────┘ └─────────┘ └──────────────┘ └───────────┘ └───────────┘  │  │
│  └─────────────────────────────────────────────────────────────────────────┘  │
│                                                                               │
└───────────────────────────────────────────────────────────────────────────────┘
```

---

## Repository Summary

| Category | Repository | Status | Description |
|----------|------------|--------|-------------|
| **Core** | [complyctl](https://github.com/complytime/complyctl) | 🟢 Active | Main CLI for compliance workflows |
| **Core** | [complytime-collector-components](https://github.com/complytime/complytime-collector-components) | 🟡 Incubating | ComplyBeacon — OTEL-based compliance evidence toolkit |
| **Core** | [complyscribe](https://github.com/complytime/complyscribe) | 🟡 Incubating | CLI for Compliance-Trestle & OSCAL in CI/CD |
| **Core** | [gemara-mcp-server](https://github.com/complytime/gemara-mcp-server) | 🟡 Incubating | MCP server for OSSF Gemara framework (prototype) |
| **Core** | [gemara2oscal](https://github.com/complytime/gemara2oscal) | 🟡 Incubating | Gemara to OSCAL library (experimental) |
| **SDK** | [oscal-sdk-go](https://github.com/complytime/oscal-sdk-go) | 🟡 Incubating | Go SDK complementing compliance-trestle (fork) |
| **SDK** | [compliance-to-policy-go](https://github.com/complytime/compliance-to-policy-go) | 🔵 Supporting | C2P: OSCAL ↔ Policy bridge (CNCF Sandbox fork) |
| **SDK** | [compliance-to-policy-plugins](https://github.com/complytime/compliance-to-policy-plugins) | 🔵 Supporting | C2P plugins for ComplyTime |
| **SDK** | [compliance-to-policy-python](https://github.com/complytime/compliance-to-policy-python) | 🔵 Supporting | C2P Python: OSCAL ↔ Policy (CNCF Sandbox fork) |
| **Content** | [complytime-policies](https://github.com/complytime/complytime-policies) | 🟢 Active | CALM architectures & Gemara controls |
| **Content** | [oscal-content](https://github.com/complytime/oscal-content) | ⚪ Empty | Placeholder (empty repository) |
| **Content** | [cac-content](https://github.com/complytime/cac-content) | 🔵 Supporting | ComplianceAsCode fork: SCAP/Ansible/Bash content |
| **Infra** | [org-infra](https://github.com/complytime/org-infra) | 🟢 Active | CI/CD reusable workflows, templates, configs |
| **Infra** | [.github](https://github.com/complytime/.github) | 🔵 Supporting | Org-level GitHub config |
| **Infra** | [complytime-collector-distro](https://github.com/complytime/complytime-collector-distro) | 🔵 Supporting | Beacon collector releases |
| **Infra** | [complytime-demos](https://github.com/complytime/complytime-demos) | 🔵 Supporting | Demo automation |
| **Infra** | [baseline-demo](https://github.com/complytime/baseline-demo) | 🔵 Supporting | OSPS Baseline demo with C2P + Conforma |
| **Infra** | [vagrant-boxes](https://github.com/complytime/vagrant-boxes) | 🔵 Supporting | Vagrant automation |
| **Infra** | [creme-brulee](https://github.com/complytime/creme-brulee) | 🔵 Supporting | Training course for Compliance Managers |
| **Community** | [community](https://github.com/complytime/community) | 🟢 Active | Community docs |

---

## Getting Help

- **General Questions**: Open a [discussion](https://github.com/complytime/community/discussions)
- **Bug Reports**: File issues in the relevant project repository
- **Security Issues**: See [SECURITY.md](./SECURITY.md)

## Acknowledgements

This document structure was inspired by [KServe Community](https://github.com/kserve/community), [Kubernetes SIGs](https://github.com/kubernetes/community), and other CNCF project governance models.
