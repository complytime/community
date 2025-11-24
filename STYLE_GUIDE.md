# ComplyTime Organization Style Guide

This document serves as the central source of truth for engineering standards, contribution workflows, and architectural principles for the ComplyTime organization. All contributors and maintainers are expected to adhere to these guidelines to ensure consistency, quality, and compliance.

---

## 1. High-Level Engineering Principles

These principles guide *how* we think about problems and *why* we make specific technical decisions. We value long-term sustainability over short-term speed.

### Core Value: Maintainability & Robustness

**1. Single Source of Truth (Centralized Constants)**
* **Principle:** Centralize values that are used in multiple places or may change over time.
* **Implementation:**
    * **No Magic Strings/Numbers:** Avoid using raw strings (e.g., `"active"`, `"https://api..."`) or raw numbers (e.g., `86400`) inline within your logic.
    * **Dedicated Files:** Move these values into a dedicated file (e.g., `internal/consts/consts.go`, `settings.py`).
* **Why?**
    * **Prevent Divergence:** If a timeout changes from 30s to 60s, updating it in *one* file ensures every part of the application updates automatically.
    * **Avoid "Shotgun Surgery":** You should never have to search and replace a value across 10 different files to make 1 logical change. This reduces the risk of missing an instance and introducing bugs.

**2. Simplicity & Isolation**
* **Principle:** Complexity is the enemy of security and maintenance.
* **Implementation:** Keep functions small and focused (Single Responsibility Principle). It is easier to test and maintain a system composed of small, isolated parts than a monolithic script.

**3. Incremental Improvement**
* **Principle:** We encourage contributors to improve the code they interact with, while ensuring individual contributions remain focused.
* **Implementation:** If you identify areas for improvement (such as refactoring, formatting fixes, or better naming) while working on a specific bug or feature, **consider opening a separate Pull Request or an Issue on GitHub** for those changes. Keeping improvements separate from logic fixes ensures that your original PR remains atomic and easier for maintainers to review.

### Core Value: Readability

**1. Code is Written for Humans First**
* **Principle:** [Code is read 10x more often than it is written](https://www.goodreads.com/quotes/835238-indeed-the-ratio-of-time-spent-reading-versus-writing-is). Optimizing for the reader (your future self or a teammate) is more important than optimizing for the writer's speed.
* **Implementation:**
    * **Explicit Naming:** Variable and function names should clearly describe their intent (e.g., use `days_until_expiration` instead of `d`).
    * **Avoid "Clever" Code:** Avoid complex one-liners or obscure language features that require deep mental parsing. If the implementation is hard to explain, it is a bad implementation.
    * **Self-Documenting:** The code structure itself should explain the logic. Comments should explain the *why* (business logic/intent), not the *what* (syntax).

### Core Value: Efficiency

**1. Do Not Reinvent the Wheel**
* **Principle:** Leverage existing solutions, but validate their quality and contribute back.
* **Implementation:**
    * **Research First:** Always research existing open-source libraries or cloud-native solutions before writing custom code.
    * **Vet Dependencies:** Don't just pick the first result. Evaluate the library's **reliability**: check its adoption rate, governance model, maintenance frequency (last commit date), and community health.
    * **Contribute Upstream:** If an existing library is close to what we need but missing a feature or bug fix, **contribute to it**. Prefer sending a Pull Request to the upstream repository over creating a local workaround or a hard fork.
* **Why:** Using well-maintained libraries reduces our maintenance burden. Contributing back improves the ecosystem for everyone and reduces the technical debt of maintaining internal patches.


### Core Value: Architecture

**1. Composability (The Unix Philosophy)**
* **Principle:** Write programs that do one thing and do it well. Write programs to work together.
* **Implementation:** Our tools (like `complyctl`) should be modular. Output from one tool should be easily consumable as input for another (e.g., standard JSON/YAML streams).

**2. Convention Over Configuration**
* **Principle:** Decrease the number of decisions a developer or user needs to make.
* **Implementation:** Use sensible defaults. Users should only need to specify configuration for things that deviate from the standard norm.

---

## 2. Repository Structure & Standards

Every repository under the ComplyTime organization must contain the following standard files in the root directory to ensure a consistent developer experience:

| File                 | Description                                | Standard                                         |
|:---------------------|:-------------------------------------------|:-------------------------------------------------|
| `README.md`          | Project overview, installation, and usage. | Markdown                                         |
| `LICENSE`            | Legal terms of use.                        | **Apache License 2.0**                           |
| `CONTRIBUTING.md`    | Guidelines for contributors.               | Link to org-wide guide or repo-specific details. |
| `CODE_OF_CONDUCT.md` | Community standards.                       | Standard Contributor Covenant                    |
| `SECURITY.md`        | Security policy.                           | Vulnerability reporting instructions             |
| `.github/`           | GitHub configuration.                      | Issue templates, PR templates, workflows.        |

> Content of all these files can link to org-wide files, and eventually incremented with repository specific content.

---

## 3. Contribution Workflow

* **Branching Strategy:**
    * **Main Branch:** `main` is the stable production branch.
    * **Feature Branches:** Create branches from `main` for all changes.
* **Pull Requests (PRs):**
    * **Atomic Changes:** PRs should be small enough to be reviewed in one sitting. Large, sprawling PRs may be requested to be split.
    * **Review Requirement:** All PRs require review from at least two Maintainers.
    * **CI/CD Gates:**
      * **Standard:** All PRs must generally pass automated checks (linting, testing, build) before merging.
      * **Exceptions:** We recognize that checks may occasionally fail due to external issues outside our control or transient flakes that pass locally. In these rare instances, **maintainers can discuss and agree on exceptions** to merge specific PRs despite a red status.

* **Commit Messages:**
    * Follow the **Conventional Commits** [specification](https://www.conventionalcommits.org/).
    * **Format:** `<type>: <description>`
    * **Example:** `feat: implement oscal validation logic`

---

## 4. Centrally manages configuration files, templates, and standardized CI/CD workflows

We should centralize workflows, configurations, and templates as much as possible. Refer to [org-infra](https://github.com/complytime/org-infra).

## 5. Coding Standards

### Guidelines for all programming language

- **Empty Line at End of File**: Ensure that all files include an empty line at the end. This helps with version control diffs and adheres to POSIX standards.
- The pre-commit and pre-push hooks can be configured by installing [pre-commit](https://pre-commit.com/) and running code repo specific make commands.

### Go (e.g., `complyctl`)

#### General Guidelines

- **File Naming**: Use lowercase letters and underscores for file names (e.g., `my_file.go`).
- **Package Names**: Use short, concise, and lowercase names for packages. Avoid underscores and mixed caps.
- **Error Handling**: Always check for errors and handle them appropriately. Return errors to the caller when necessary.
- **Testing**: Write tests for your code. Use descriptive names for test functions and include edge cases.
- **Line Length**: Limit lines to 99 characters when reasonable to improve readability.

#### Licensing and File Headers

```go
// SPDX-License-Identifier: Apache-2.0
```

#### Code Formatting

- **Imports**: Use [`goimports`](https://pkg.go.dev/golang.org/x/tools/cmd/goimports) to format and organize imports. Separate standard library, third-party, and project-specific imports with blank lines. Also ensure only necessary imports.
- **Indentation and Spacing**: Use the [`go fmt`](https://go.dev/blog/gofmt) tool to automatically format your code. This ensures consistent indentation with tabs and proper spacing after commas, colons, and semicolons.
- **Braces**: Place opening braces on the same line as the statement (e.g., `if`, `for`, `func`).

#### Additional Guidelines

- Other [Go checks](https://github.com/complytime/complyctl/blob/main/.golangci.yml) are present in CI/CD, and therefore it may be useful to also run them locally before submitting a PR.
- Complyctl leverages the [charmbracelet/log](https://github.com/charmbracelet/log) library for logging all command and plugin activity. By default, this output is printed to stdout.


### Python (e.g., `complyscribe`)

#### General Guidelines

- **Testing**: Write tests for your code. Use descriptive names for test functions and include edge cases.
- **Line Length**: Limit lines to 99 characters when reasonable to improve readability.
- **Type Hinting:** Use Python type hints to improve readability and tooling support.

#### Licensing and File Headers

```python
# SPDX-License-Identifier: Apache-2.0
```

#### Code Formatting

- **Style:** Uses `black` and `isort` for formatting.
- **Lint:** Use `flake8` for linting.
- **Static type check:** Use `mypy` as static type checker.
- **Non-Python files:** Use [Megalinter](https://github.com/oxsecurity/megalinter) to lint in a CI task. See [megalinter.yaml](https://github.com/complytime/complyscribe/blob/main/.mega-linter.yml) for more information.

---
