<!--
  Project Brief and Plan

  - One-paragraph elevator pitch: what uips-browser-kit is and who it is for
  - Problem statement: what UiPath browser automation currently lacks that this project addresses
  - Scope summary: what is in (library, rules, snippets, skills) and what is out
  - Target audience: UiPath developers, automation architects, community contributors
  - High-level delivery plan: phases or milestones (M0 Bootstrap → M1 → ... → M6)
  - Key constraints: platform (UiPath Studio), language (.xaml / NuGet), team size, open-source governance
  - Success criteria: how the project will know it has achieved its goals
  - Risks and mitigations identified at planning time

  DRAFT — problem statement evidence from community (Marcelo Cruz, via cprima):
  - Bots break when devs navigate through the UI the way humans do — menus, submenus, buttons —
    because any UI change breaks the selector chain. Navigating directly to stable URLs is the
    fix, but it is not the default habit. The library should make the right thing easy.
    (Source: Marcelo Cruz post on URL navigation; cprima commented in agreement)
  - Stale state between runs — leftover cookies, localStorage, cached assets — causes hard-to-
    reproduce failures. Incognito/private mode solves this but requires explicit opt-in in UiPath.
    The library should default to clean-state runs.
    (Source: Marcelo Cruz post on incognito mode)

  DRAFT — target audience constraints from community (Liga Kalnina, pain-points.md):
  - Many orgs ban advanced activities (ixd, Invoke Code) so that any developer can maintain
    the automation later. The library must work within pure-activity constraints.
  - API access is frequently restricted by client policy. For this audience, browser UI
    automation is not a workaround — it is the only available channel.
  - Both constraints are "pretty common" per Liga; they must be first-class design targets,
    not edge cases.
-->

## Background

## Objectives

## Requirements

### Functional

### Non-Functional

## Deliverables

## Project Approach

## Work Breakdown

## Dependencies

## Timeline

## Team Responsibilities

## Risks & Mitigations

## Communication Plan

## Decision Log
