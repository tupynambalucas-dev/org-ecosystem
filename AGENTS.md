# tupynambalucas-dev Product Ecosystem Meta-Repository Agent Context

This document serves as the root context router (Layer 1) for AI agents operating in the
`tupynambalucas-dev/org-ecosystem` product portfolio meta-repository.

## Workspace Navigation

- [README.md](./README.md): Primary developer documentation and Mani portfolio orchestration runbook.
- [mani.yaml](./mani.yaml): Declarative multi-repository manifest managing product repositories, remotes, and batch tasks.
- [org-ecosystem.code-workspace](./org-ecosystem.code-workspace): Canonical multi-root IDE workspace binding portfolio solutions.
- [LICENSE](./LICENSE): Apache License 2.0 governing meta-repository orchestration assets.
- [commercial/omnichannel](./commercial/omnichannel/README.md): Commercial omnichannel messaging engine and client platform (Turborepo Monorepo).
- [internal/tessel](./internal/tessel/README.md): Proprietary enterprise core platform and internal software asset (Turborepo Monorepo).
- [oss/](./oss/): Directory for open-source community repositories and SDKs.

## Governance Standards

- **Branching Model**: Single-Branch GitHub Flow on `main`. Short-lived branches MUST use Conventional Commit prefixes (`feat/`, `fix/`, `docs/`, `chore/`, `refactor/`, `ci/`, `perf/`, `test/`, `build/`, `style/`, `revert/`, `hotfix/`).
- **Cryptographic Signature**: All Git commits and annotated tags MUST be signed with SSH (`git commit -S -m "..."`).
- **Conventional Commits**: All commit messages must follow `<type>[optional (<scope>)][!]: <description>` (`<= 72` chars target, `<= 100` chars maximum).
- **Zero-Emoji Policy**: Emojis are strictly forbidden across all code, PRs, comments, and agent interactions.
- **Secret Hygiene**: Never commit plaintext tokens. Sourced via Infisical (`infisical run -- ...`) or local `.env` files.
- **License**: `Apache-2.0` (`Copyright (c) 2026 tupynambalucas.dev`) across public portfolio assets.
- **Workspace Orchestration**: Repositories are managed as sovereign Git repositories coordinated via `mani`. Git submodules and `160000` commit gitlinks are deprecated and removed.

## Multi-Repository Operations with Mani

Cross-repository commands and queries are executed using `mani`:

```bash
# Check status across all portfolio projects
mani run status

# Fetch remote changes for all projects
mani run fetch

# Pull latest main across all projects
mani run pull

# Display current branches
mani run branch

# Selective synchronization by category tags
mani sync --tags commercial
mani sync --tags internal
mani sync --tags oss
```

## AI Agent Plugin Consumption

Portfolio applications consume domain plugins and sovereign MCP servers from the `@tupynambalucas-dev/agent-mesh` umbrella package:
- **Package Dependency**: Pinned via `catalogs.plugins-stack` (`github:tupynambalucas-dev/agent-mesh`) in child monorepos.
- **Runtime Discovery**: Registered in `.agents/plugins.json` pointing to `node_modules/@tupynambalucas-dev/agent-mesh/plugins/packages`.
- **Sovereign Execution**: MCP servers run via self-contained launchers (`scripts/launcher.cjs`) and committed bundles (`dist/bin.cjs`).

## Architectural Plans & Artifact Dual-Storage Standard

Architectural blueprints, technical plans, and master plans follow strict enterprise storage standards:
- **Storage Location**: Blueprints reside in `<repo>/.agents/plans/<plan-slug>/`.
- **Topologies**: Topology 1 (Single-File Plan) for atomic refactors/features; Topology 2 (Multi-Artifact Plan Suite) for multi-domain frameworks with master `README.md` and numbered domain documents.
- **Dual-Storage Invariant**: Whenever an agent creates a plan artifact in the Antigravity conversation directory (`<appDataDir>/brain/<conversation-id>/`), an identical synchronized copy MUST ALWAYS be mirrored in `<repo>/.agents/plans/<plan-slug>/`.
- **Ignore & Index Triad**: All repositories ignore `.agents/plans/` and `plans/` in `.gitignore`, while explicitly un-ignoring them in `.ignore` and `.rgignore` (`!.agents/plans/`, `!.agents/plans/**`, `!plans/`, `!plans/**`) and setting `"search.useIgnoreFiles": false` in `.vscode/settings.json` so files can always be attached with `@`.

## Required Skills

Agents operating at the `org-ecosystem` meta-repository layer MUST autonomously engage the domain skills:

- **Atelier Plugin (`@tupynambalucas-dev/plugin-atelier`)**: `router-architect`, `skill-architect`, `rule-architect`, `hook-architect`, `plugin-architect`, `plan-architect`.
- **Repository Governance Plugin (`@tupynambalucas-dev/plugin-repo`)**: `readme-architect`, `monorepo-architect`, `community-health-architect`, `license-architect`, `github-standards-architect`, `mani-operator`.
- **GitHub Flow Plugin (`@tupynambalucas-dev/plugin-github-flow`)**: `github-flow-operator`, `github-actions-operator`.
- **Secrets Plugin (`@tupynambalucas-dev/plugin-secrets`)**: `infisical-vault-operator`, `secret-rotation-operator`.
