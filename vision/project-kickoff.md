# Project Kickoff

## Executive Summary

## Problem Statement
<!--
-->
Current RPA browser automation approaches in UiPath primarily emphasize replication of human interaction patterns within existing operational environments. As a result, automation workflows frequently depend on shared browser state, installed browser configurations, sequential UI traversal, and frontend-specific interaction paths. These characteristics can reduce reproducibility, increase coupling to UI changes, and raise maintenance effort when applications evolve. In contrast, modern browser automation frameworks used in software testing provide mechanisms such as isolated execution contexts, deterministic environment provisioning, direct navigation capabilities, and standardized runtime management. The absence of comparable abstractions in UiPath creates a gap in maintainability, portability, and robustness of browser-based automations. This project aims to develop a reusable UiPath Studio library that introduces such capabilities and provides a more deterministic and resilient browser automation model.

## Goals
<!--
-->
Planned library capabilities are:

* Browser version pinning
* Managed browser profile provisioning
* Isolated browser contexts
* Dynamic URL/direct navigation support
* Resilient selector strategies
* Session lifecycle management
* Deterministic startup/cleanup
* Diagnostics and trace logging

## Success Metrics

tbd

## Scope

### In Scope

<!--
-->


**Core browser runtime management**

* Browser initialization and lifecycle management
* Browser version selection/pinning where technically feasible
* Managed browser profile creation and cleanup
* Isolated execution contexts/sessions
* Deterministic startup and teardown procedures

**Navigation and interaction abstractions**

* Direct URL navigation activities
* Reusable navigation patterns
* Configurable page loading and synchronization mechanisms
* Standardized interaction wrappers for browser actions

**Robustness and maintainability**

* Configuration-driven behavior
* Resilient selector handling strategies
* Error handling and retry mechanisms
* Logging and diagnostics support
* Session state management

**UiPath integration**

* Reusable UiPath Studio activities/components
* Documentation and usage examples
* Packaging as a reusable library for multiple projects

**Validation**

* Demonstration against representative web applications
* Stability and maintainability evaluation

### Out of Scope

<!--
-->
**General-purpose RPA platform development**

* Replacing native UiPath browser activities
* Modifying UiPath Studio internals

**Advanced testing framework capabilities**

* Test case management
* Assertions and verification frameworks
* Unit/integration/end-to-end test orchestration
* Test coverage analysis
* Cross-browser testing suites

**AI and intelligent automation**

* AI-based selector generation
* Machine learning models
* Autonomous workflow generation

**Infrastructure and deployment**

* Container orchestration
* Cloud execution platforms
* CI/CD pipeline implementation

**Non-browser automation**

* Desktop application automation
* Mobile application automation
* OCR/document processing workflows
* ERP-specific connectors

**Security and enterprise governance**

* Authentication platform development
* Credential vault implementation
* Enterprise access management solutions

## Stakeholders & Owners

## Constraints & Assumptions

<!--
-->
**Assumptions**

* UiPath Studio environment is available
* Supported target browsers are limited to selected modern browsers
* Target applications expose navigable URLs and accessible UI elements
* Existing UiPath extension mechanisms remain available

## High-Level Solution

<!--
-->
The solution is a layered ecosystem of cooperating repositories, each with a single
responsibility, that together deliver a complete browser automation toolkit for UiPath.

Deliverables — what ships to consumers:
- library     Core NuGet package. Browser lifecycle, isolated contexts, direct navigation,
              resilient selectors, session management, diagnostics. The foundation everything
              else builds on.
- rules       Companion Workflow Analyzer rule set. Enforces library best practices at
              design time — static analysis, not runtime.
- snippets    Reusable sequences and reference patterns built on library's APIs. Ready-to-use
              starting points for common browser automation scenarios.
- skills      Higher-level composable building blocks for attended and unattended automations.
              Built on library; consumed by end-user projects directly.

Validation — how correctness is assured:
- testproject     A real UiPath consumer project. Exercises library and skills end-to-end;
                  serves as the regression baseline for every release.
- testdata        Fixtures, browser profiles, and sample web pages consumed by testproject
                  and testharness-webapps. Stable, versioned inputs for repeatable runs.
- testharness-webapps  Scripts and tooling that orchestrate testproject runs against
                  testdata and produce consistent pass/fail signals for CI.
- other testharness implementations

Knowledge & community:
- docs        Structured documentation (vision, decisions, guides, reference, releases).
- exploration Research spikes and dead ends — findings that informed or ruled out scope.
- playground  Safe sandbox for contributors to experiment without affecting main artifacts.
- slides      Community presentations and workshop decks.

Dependency flow (simplified):
  skills, snippets  →  library
  testproject       →  library, skills
  testharness-webapps → testproject, testdata
  rules             →  (consumed at design time by any project using library)

## Risks

<!--
-->
| Risk                                                                                             | Likelihood | Impact | Mitigation                                                                                                                     |
| ------------------------------------------------------------------------------------------------ | ---------- | ------ | ------------------------------------------------------------------------------------------------------------------------------ |
| UiPath platform changes break library internals (activity model, extension API, selector engine) | Medium     | High   | Pin tested Studio version; maintain a compatibility matrix; regression suite catches regressions early                         |
| Browser vendor updates (Chrome/Edge/Firefox) change behaviour that library depends on            | High       | Medium | testharness-webapps runs against pinned and latest browser; issues surface before they reach consumers                         |
| Scope creep — community requests pull the library toward general-purpose RPA tooling             | Medium     | High   | Explicit out-of-scope list in charter; scope decisions require maintainer approval; rules repo enforces design-time guardrails |
| Key contributor availability — small team, knowledge concentration risk                          | Medium     | High   | Multi-repo structure limits blast radius; docs and decisions captured in writing, not in people                                |
| Adoption low — library solves the right problem but is not discovered or trusted                 | Medium     | Medium | Public org, open issues, discussion repo, slides and community content lower the barrier to discovery                          |
| Test coverage insufficient — library ships with undetected regressions                           | Low        | High   | testproject + testharness-webapps form the regression baseline; no release without a passing run                               |
| Configuration coupling — consumers hardwire config, making upgrades painful                      | Medium     | Medium | Configuration decoupling is a first-class design requirement (injectable at activity level, no config-file dependency)         |

## Milestones & Timeline

## Open Questions

## Next Steps
