# Harness Subagents Governance

**Adopted** November 5, 2026

Harness Subagents is a lightweight, open format for defining reusable subagents for AI agent harnesses. The project maintains the specification and its documentation. This document describes how the project is organized, who makes decisions, and how it accepts contributions.

## 1. General Project Policies

The project is developed in the open and governed by its Maintainer, with input from contributors. Decisions and the discussion that supports them are recorded publicly on GitHub.

Contributors acknowledge that the copyright in all new contributions will be retained by the copyright holder as independent works of authorship and that no contributor or copyright holder will be required to assign copyrights to the project.

All code and specification contributions are made under the Apache License, Version 2.0 (available here: [https://www.apache.org/licenses/LICENSE-2.0](https://www.apache.org/licenses/LICENSE-2.0)) (the "Project License"). All outbound code and specifications are made available under the Project License.

All documentation (excluding specifications) is made available under the Creative Commons Attribution 4.0 International license, available at: [https://creativecommons.org/licenses/by/4.0](https://creativecommons.org/licenses/by/4.0).

Contributors are expected to participate constructively and respectfully with everyone who takes part in the project.

## 2. Roles

| Role | Scope |
| --- | --- |
| **Maintainer** | Final decision authority over the specification and the project direction |
| **Contributors** | Issues, pull requests, and discussions |

### Contributors

Anyone who files an issue, opens a pull request, or takes part in a discussion is a Contributor. There are no formal requirements.

### Maintainer

The Maintainer steers the specification and the overall direction of the project. They decide on substantive changes to the specification, resolve disputes, and may appoint additional Maintainers as the project grows. The current Maintainer is listed in MAINTAINERS.md.

The project favors a small specification and a high bar for additions. The Maintainer is expected to hold that line.

## 3. Decision Process

Decisions are made by the Maintainer and recorded on GitHub. Bug fixes, typo corrections, clarifications and new examples are made by ordinary pull requests.

## 4. Changes to the Specification

The project keeps a high bar for additions to the specification. As the contributing guide puts it, "it is much easier to add things to a specification than to remove them." Proposals should address real implementation challenges, not theoretical concerns.

Any change to the specification that adds, removes or alters normative behavior is a substantive change and requires the Maintainer's explicit approval. A substantive change moves through the following steps:

1. **Proposal.** The author opens a pull request that adds the proposal as a file in the repository, or describes it in a Discussion. The proposal states the problem, the change to the specification, the reasoning, the effect on existing subagents and harnesses, and any security implications.

2. **Review.** Discussion takes place in public on the pull request. The author is responsible for recording dissenting views.

3. **Decision.** The Maintainer accepts or rejects the proposal and records the decision.

4. **Final.** An accepted proposal becomes final when the specification text is merged and at least one working implementation demonstrates the change.

Releases of the specification are tagged and carry a changelog, so implementers can declare and test against a specific version.

## 5. Communication

Questions and early ideas are raised in GitHub Discussions, and concrete bugs are filed as GitHub Issues. The project may keep private channels for certain communications, including security reports and conduct matters. Except for matters handled in those channels, decisions and the discussion that supports them must be recorded on GitHub.

## 6. Adding Maintainers

The Maintainer may appoint additional Maintainers as the project grows. Appointments are merit-based, recorded on GitHub, and listed in MAINTAINERS.md. A candidate is expected to show sustained, high-quality contribution to the project, working knowledge of the specification, independence from any single employer or organization, and a commitment to restraint in how the specification evolves.

## 7. Amendment

Amendments to this document are proposed and decided by the Maintainer and recorded on GitHub with their rationale.

## 8. Provenance

Portions of this document are adapted from the governance documents of the Agent Skills and Model Context Protocol projects, which the Model Context Protocol project makes available under the [Creative Commons Attribution 4.0 International license](https://creativecommons.org/licenses/by/4.0/).
