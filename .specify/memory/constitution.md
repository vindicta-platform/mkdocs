<!--
Sync Impact Report
===================
Version change: (none) → 1.0.0 (initial fill from template)
Modified principles: N/A (all new — template placeholders replaced)
Added sections:
  - Core Principles (5 principles: Doc Integrity, Spec-Driven, Arch Fidelity,
    Economic Prime Directive, Zero-Issue Stability)
  - Documentation Standards
  - Development Workflow
  - Governance (amendment rules, versioning, compliance)
Removed sections: None
Templates requiring updates:
  - .specify/templates/plan-template.md — ✅ No changes needed (Constitution
    Check section already generic)
  - .specify/templates/spec-template.md — ✅ No changes needed (no
    constitution-dependent gates)
  - .specify/templates/tasks-template.md — ✅ No changes needed (task format
    is principle-agnostic)
Follow-up TODOs: None
-->

# Platform-Docs Constitution

## Core Principles

### I. Doc Integrity (NON-NEGOTIABLE)

All documentation MUST pass automated quality validation before merge:

- Markdown link validation MUST succeed (no broken internal or external links).
- Markdown linting (markdownlint) MUST pass on all files under `docs/`.
- Every ADR, SPIKE, and specification MUST use relative links to reference
  other documents within the repository.
- Image assets MUST be stored in `docs/assets/` and referenced via relative
  paths — never absolute filesystem paths.

### II. Spec-Driven Development (SDD)

Every feature or structural change to Platform-Docs MUST follow the SDD
lifecycle:

1. **Specify**: Create a feature specification in `specs/[NNN]-[name]/spec.md`
   using the spec template.
2. **Plan**: Produce an implementation plan with research and design artifacts.
3. **Tasks**: Generate a dependency-ordered task list from the plan.
4. **Implement**: Execute tasks atomically with commits tied to task IDs.

Ad-hoc documentation changes (typo fixes, formatting) are exempt from full
SDD but MUST still pass CI quality gates.

### III. Architectural Fidelity

The C4 architecture model (`c4/workspace.dsl`) is the single source of truth
for the Vindicta Platform's structural design:

- Container names, domain groups, and relationships in documentation MUST
  match the DSL definitions.
- ADRs and SPIKEs MUST reference container IDs (camelCase identifiers from
  the DSL), not informal display names.
- Any structural change to the platform (new repo, repo rename, domain
  reassignment) MUST be reflected in the DSL before documentation is updated.

### IV. Economic Prime Directive

All tooling and infrastructure choices for Platform-Docs MUST comply with
GCP/GitHub free-tier limits:

- MkDocs MUST be built and served via GitHub Pages (free).
- CI workflows MUST use GitHub Actions with public-repo free minutes.
- Diagram rendering MUST use open-source tools (Structurizr CLI) — no paid
  SaaS subscriptions.
- Scaling beyond free-tier limits requires explicit architectural review.

### V. Zero-Issue Stability

Documentation stability and technical debt resolution take precedence over
new content:

- Broken links, stale references, and formatting violations MUST be fixed
  before new features are merged.
- The repository MUST maintain a zero-issue state — all open issues are
  either actively worked or triaged within 7 days.
- CI MUST block merges when quality gates fail.

## Documentation Standards

- **Format**: All documentation is authored in Markdown and built with MkDocs
  (Material theme).
- **Structure**: Content is organized under `docs/` following the directory
  layout defined in `mkdocs.yml`.
- **ADRs**: Architecture Decision Records follow the template at
  `docs/adr/000-template.md` and are numbered sequentially.
- **SPIKEs**: Time-boxed investigation documents live in `docs/spikes/` with
  naming convention `spike-NNN-short-description.md`.
- **Commit messages**: Follow Conventional Commits (`feat:`, `fix:`, `docs:`,
  `chore:`).
- **Branching**: Feature branches use the pattern `NNN-short-name` matching
  the spec directory number.

## Development Workflow

1. **Branch**: Create a feature branch from `main` via the SpecKit
   `create-new-feature.ps1` script.
2. **Specify → Plan → Tasks**: Run the SDD pipeline to produce spec, plan,
   and task artifacts before writing content.
3. **Implement**: Author documentation changes tied to task IDs. Commit
   atomically per task.
4. **CI Validation**: Every PR triggers `ci.yml` which validates Markdown
   quality. For `c4/` changes, `c4-render.yml` validates DSL and renders
   diagrams.
5. **Review**: PRs require at least one approval. Reviewers verify Doc
   Integrity (Principle I) and Architectural Fidelity (Principle III).
6. **Merge**: Squash-merge to `main`. GitHub Pages deploys automatically.

## Governance

This constitution supersedes all other documentation practices within the
Platform-Docs repository. It inherits core principles from the
[Vindicta Platform Constitution v1.0.0](https://github.com/vindicta-platform/.specify)
and specializes them for the documentation domain.

- **Amendments**: Any change to this constitution MUST be documented as an
  amendment with a version bump, rationale, and migration plan if dependent
  templates are affected.
- **Versioning**: Follows Semantic Versioning — MAJOR for principle removals
  or redefinitions, MINOR for additions or material expansions, PATCH for
  clarifications and wording fixes.
- **Compliance**: All PRs and reviews MUST verify adherence to these
  principles. The Sync Impact Report (HTML comment at top of this file)
  tracks propagation status.
- **Precedence**: If a conflict arises between this constitution and the
  platform-wide constitution, the platform-wide constitution takes
  precedence.

**Version**: 1.0.0 | **Ratified**: 2026-02-07 | **Last Amended**: 2026-02-07
