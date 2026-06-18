---
name: update-dependencies
description: Workflow command scaffold for update-dependencies in sonarqube-mcp-server.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /update-dependencies

Use this workflow when working on **update-dependencies** in `sonarqube-mcp-server`.

## Goal

Update external dependencies or tool versions used by the project.

## Common Files

- `gradle.lockfile`
- `gradle/libs.versions.toml`
- `its/build.gradle.kts`
- `its/gradle.lockfile`
- `.github/workflows/*.yml`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update dependency version in relevant configuration files (e.g., gradle.lockfile, gradle/libs.versions.toml, build.gradle.kts, .github/workflows/*.yml).
- Commit changes with a message referencing the dependency and new version.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.