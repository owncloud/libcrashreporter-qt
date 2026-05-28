# agents.md -- libcrashreporter-qt

## Repository Overview

Archived/legacy C++/Qt library for Google Breakpad crash reporting integration. Licensed under LGPL-2.1 (with GPL for drkonqi integration). This is a fork used as a submodule by the ownCloud Desktop Client.

## Architecture & Key Paths

- `src/` -- Library source code
- `3rdparty/` -- Third-party dependencies
- `CMakeLists.txt` -- CMake build configuration

## Development Conventions

- C++ with Qt framework
- CMake build system
- Cross-platform targeting Linux, Windows, macOS

## Build & Test Commands

```bash
mkdir build && cd build
cmake ..
cmake --build .
```

## Important Constraints

- Licensed under LGPL-2.1 (copyleft). The drkonqi integration requires GPL-2.0.
- Do not introduce new **copyleft-licensed dependencies** (GPL, AGPL, LGPL, MPL) without explicit discussion in an issue first. This is especially important for repos that are migrating to or already under Apache 2.0, as copyleft dependencies would block or complicate that migration.
- This is an archived/legacy fork. Active development is unlikely.
- The OSPO is working toward Apache 2.0 migration across the organization, but this fork's LGPL-2.1 and GPL copyleft dependencies must be audited first.
- All contributions require a DCO sign-off.


## OSPO Policy Constraints

### GitHub Actions
- **Only** use actions owned by `owncloud`, created by GitHub (`actions/*`), verified on the GitHub Marketplace, or verified by the ownCloud Maintainers.
- Pin all actions to their full commit SHA (not tags): `uses: actions/checkout@<SHA> # vX.Y.Z`
- Never introduce actions from unverified third parties.

### Dependency Management
- Dependabot is configured for automated dependency updates.
- Review and merge Dependabot PRs as part of regular maintenance.
- Do not introduce new dependencies without discussion in an issue first.

### Git Workflow
- **Rebase policy**: Always rebase; never create merge commits. Use `git pull --rebase` and `git rebase` before pushing.
- **Signed commits**: All commits **must** be PGP/GPG signed (`git commit -S -s`).
- **DCO sign-off**: Every commit needs a `Signed-off-by` line (`git commit -s`).
- **Conventional Commits & Squash Merge**: Use the [Conventional Commits](https://www.conventionalcommits.org/) format where the repository enforces it. Many repos use squash merge, where the PR title becomes the commit message on the default branch — apply Conventional Commits format to PR titles as well. A reusable GitHub Actions workflow enforces this.

## Context for AI Agents

This is a small library with a simple CMake-based build. It wraps Google Breakpad for Qt applications. The codebase is legacy and changes should focus on bug fixes only.
