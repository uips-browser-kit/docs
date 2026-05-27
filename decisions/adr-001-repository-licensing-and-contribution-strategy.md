**ADR-001: Repository Licensing and Contribution Strategy**

**Status**
Accepted

**Context**

The `uips-browser-kit` organization is intended for open collaboration around UiPath Studio libraries and related assets. Contributors may include developers, testers, documentation authors, and other collaborators with varying GitHub experience.

The project aims to encourage contribution while preserving future strategic flexibility. Some repositories represent strategic project assets, while others primarily exist for collaboration, experimentation, or documentation.

Future relicensing capability is a requirement.

**Decision**

Repository licensing is separated by artifact type:

| Repository category                |                          License |
| ---------------------------------- | -------------------------------: |
| Code repositories                  |               Apache License 2.0 |
| Documentation/content repositories | Creative Commons Attribution 4.0 |

Strategic repositories are defined as:

```text
library
rules
snippets
```

For these repositories:

* contribution agreements are required for external contributions
* maintainers control review and merge paths
* branch protection and CODEOWNERS are enforced
* future relicensing capability shall be preserved

Collaborative repositories:

```text
testproject
testharness-webapps
playground
```

Content repositories:

```text
docs
testdata
exploration
```

These repositories prioritize collaboration and lower contribution friction.

**Objectives**

1. Enable open collaboration.
2. Keep contribution friction low for RPA developers.
3. Preserve future relicensing capability.
4. Preserve future strategic and commercial flexibility.
5. Concentrate ownership of strategic assets.
6. Separate strategic assets from collaborative assets.
7. Permit experimentation in non-core repositories.
8. Use familiar and business-friendly licenses.
9. Avoid strong copyleft obligations.
10. Distinguish software artifacts from documentation/content artifacts.

**Consequences**

Positive:

* Contributors can participate with low friction.
* Strategic repositories remain controlled.
* Future licensing changes remain possible.
* Repository purpose aligns with governance and permissions.
* Code and content follow separate licensing models.

Negative:

* Strategic repositories require additional contribution process overhead.
* Repository classification must be maintained consistently.
* Contribution agreements introduce additional administration for selected repositories.
