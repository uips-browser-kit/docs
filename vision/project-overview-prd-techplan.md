<!--
  Project Overview — PRD and Technical Plan

  Product Requirements:
  - User stories: who uses browser-kit, in what context, to achieve what outcome
  - Functional requirements: what the library/skills/snippets must be able to do
  - Non-functional requirements: reliability, cross-browser support, UiPath version compatibility
  - Out-of-scope requirements: explicitly deferred or rejected features

  Technical Plan:
  - Architecture overview: how library, rules, snippets, and skills relate to each other
  - Technology choices and rationale: UiPath activity model, NuGet packaging, Workflow Analyzer extension points
  - Repo-to-artifact mapping: which repo produces which deliverable (NuGet package, rule set, ...)
  - CI/CD approach: how changes are validated and released (GitHub Actions, test harness)
  - Versioning strategy: semantic versioning, release cadence, breaking-change policy
  - Dependencies: UiPath Studio version floor, third-party browser drivers, test infrastructure
  - Open technical questions or spikes still needed

  DRAFT — product requirements from community sources:

  User story (Liga Kalnina / pain-points.md):
  - As a developer in an org with strict activity restrictions (no ixd, no Invoke Code), I need
    browser automation building blocks that are implemented as plain UiPath activities so that
    any team member can maintain them without specialist knowledge.
  - As a developer working with API-restricted client apps, I need reliable UI-based browser
    automation as a first-class capability, not a fallback afterthought.

  Functional requirement (Marcelo Cruz / cprima):
  - Navigate to URL directly: the library must provide a clean navigate-by-URL primitive that
    replaces UI click-through navigation for pages with stable or predictable URL patterns.
  - Private/incognito session: the library must make clean-state browser sessions the easy
    default (one property, not a multi-step setup).

  Open technical question (Liga Kalnina / pain-points.md):
  - CheckAppState appears to be broken by invisible overlay elements on modern pages — Liga
    observed this as a widespread pattern ("as most pages are having invisible blanket that
    prevents UiPath from seeing it"). Needs a spike: reproduce the issue, identify root cause,
    determine whether the library can provide a reliable alternative.
    → Candidate spike issue in the library or exploration repo.

  DRAFT — technical plan notes:

  Configuration decoupling (cprima / pain-points.md):
  - cprima noted a solved pattern from another library: configuration that does not require
    reading a config file — two alternative approaches both avoid file I/O at runtime.
  - This should be documented as a design requirement: the library must not impose a config-file
    dependency on consumers; configuration must be injectable at activity level.
-->

## Executive Summary

## Problem

### Current State

### Pain Points

## Goals

## Success Metrics

## Scope

### In Scope

### Out of Scope

## Product Requirements

### User Stories

### Functional Requirements

### Non-Functional Requirements

## Technical Design

### Architecture

### Components

### APIs & Interfaces

### Data Model

### Dependencies

## Alternatives Considered

## Risks & Tradeoffs

## Delivery Plan

### Milestones

### Owners

### Timeline

## Decision Log

## Open Questions
