<!--
  Project Foundation Document

  - Why this project exists: the core problem in the UiPath browser automation ecosystem
  - Guiding principles: open development, community-first, tested and shipped, scope discipline
  - Explicit non-goals: what the project will never try to do
  - Repository model: how the multi-repo org is structured and why (library / rules / snippets / skills / docs / ...)
  - Contribution model: tiers (owners → maintainers → contributors → community), CLA requirement
  - Licensing rationale: Apache 2.0 for code, CC-BY-4.0 for content — why these were chosen
  - Quality bar: what "shippable" means for this project (test coverage, review requirements)
  - Relationship to UiPath platform: what is assumed, what is abstracted, versioning policy
  - Long-term vision: where the project should be in 2–3 years

  DRAFT — guiding principles from community sources:

  Clean state by default (from Marcelo Cruz / cprima):
  - Every automated run should start from a known-clean browser state
  - Incognito/private mode is the mechanism; the library should expose it as a default,
    not an opt-in property developers must remember to set
  - Principle: "predictable session lifecycle" — open, run, close; no state leaks between runs

  Works within org constraints (from Liga Kalnina / pain-points.md):
  - The library must not require ixd or Invoke Code — activities only, so any UiPath developer
    can read, debug, and maintain the automation without specialist knowledge
  - This is a hard design constraint, not a nice-to-have
  - Non-goal: providing escape hatches that bypass the activity model (those belong in exploration/)

  Look outward before designing (from cprima):
  - Playwright, Selenium, Puppeteer, Cypress have solved many of these problems — study their
    patterns before inventing new ones
  - The library should feel familiar to developers who have used other browser automation tools,
    mapped onto UiPath's activity model
-->

## Purpose

## Background

## Problem Definition

## Users & Customers

## Goals & Non-Goals

## Assumptions

## Constraints

## Initial Solution Direction

## System Context

## Key Risks

## Open Decisions

## Next Actions
