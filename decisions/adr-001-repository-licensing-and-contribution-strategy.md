# ADR-001 — Repository Licensing and Contribution Strategy

## Status

Accepted

## Date

2026-05-27

## Context

The `uips-browser-kit` organization is intended for open collaboration around
UiPath Studio libraries and related assets. Contributors may include developers,
testers, documentation authors, and other collaborators with varying GitHub
experience.

The project aims to encourage contribution while preserving future strategic
flexibility. Some repositories represent strategic project assets; others exist
primarily for collaboration, experimentation, or documentation.

Forces at play:

- future relicensing capability is a stated requirement
- contribution friction must be kept low for RPA developers
- strategic code assets need controlled ownership and merge paths
- documentation and content follow different norms than code (CC rather than Apache)
- strong copyleft (GPL, AGPL) would conflict with commercial UiPath environments

## Decision

We separate repository licensing by artifact type and apply a contribution
agreement requirement only to strategic repositories.

Licensing by category:

| Repository category | License |
|---|---|
| Code repositories | Apache License 2.0 |
| Documentation and content repositories | Creative Commons Attribution 4.0 |

Strategic repositories — contribution agreement required, maintainer-controlled
review and merge, branch protection and CODEOWNERS enforced, future relicensing
capability preserved:

- `library`
- `rules`
- `snippets`

Collaborative repositories — lower contribution friction, no CLA:

- `testproject`
- `testharness-webapps`
- `playground`

Content repositories — CC-BY-4.0, no CLA:

- `docs`
- `testdata`
- `exploration`

### Rationale

Apache 2.0 satisfies the objectives of open collaboration, business-friendly
use, and future relicensing: it is permissive, patent-explicit, and does not
impose copyleft obligations on consumers. CC-BY-4.0 is the standard for
documentation and content assets where attribution matters but code licensing
terms are inappropriate.

Concentrating the CLA requirement on strategic repositories reduces
administration overhead while preserving control over the assets most likely
to be relicensed or commercialised. Collaborative and content repositories
accept contributions without agreements because the risk profile is lower and
the contribution base is broader.

## Consequences

### Positive

- contributors can participate with low friction across most repositories
- strategic repositories remain under controlled ownership
- future licensing changes remain possible for the assets that matter most
- repository purpose aligns with governance model and team permissions
- code and content follow separate, well-understood licensing models

### Negative

- strategic repositories require additional contribution process overhead (CLA bot, signatures branch)
- repository classification must be maintained consistently as new repos are added
- contributors to strategic repos face an extra step that may deter casual fixes

### Neutral

- new repositories must be classified at creation time and assigned to the appropriate tier
- the `skills` repository was added after this ADR was accepted and classified as strategic (Apache 2.0, CLA required)

## Alternatives Considered

### MIT for all code repositories

Simpler and more widely recognised. Rejected because MIT lacks an explicit
patent grant, which matters for a toolkit shipping into enterprise UiPath
environments. Apache 2.0 provides equivalent permissiveness with the patent
clause included.

### No contribution agreement on any repository

Maximum contribution friction reduction. Rejected because it removes the
ability to relicense strategic assets without contacting every contributor —
a stated requirement from the outset.

### GPL for code repositories

Ensures all derivatives remain open. Rejected because GPL is incompatible
with many enterprise and commercial UiPath deployment contexts, which would
block adoption by the target audience.

## References

- [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0)
- [Creative Commons Attribution 4.0](https://creativecommons.org/licenses/by/4.0/)
- [contributor-assistant/github-action](https://github.com/contributor-assistant/github-action) — CLA bot used for signature collection
- [CONTRIBUTING.md](https://github.com/uips-browser-kit/.github/blob/main/CONTRIBUTING.md)
