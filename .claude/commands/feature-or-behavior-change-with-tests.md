---
name: feature-or-behavior-change-with-tests
description: Workflow command scaffold for feature-or-behavior-change-with-tests in sonarqube-mcp-server.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-or-behavior-change-with-tests

Use this workflow when working on **feature-or-behavior-change-with-tests** in `sonarqube-mcp-server`.

## Goal

Implement a feature or change behavior, updating both implementation and associated tests.

## Common Files

- `src/main/java/**`
- `src/test/java/**`
- `its/src/test/java/**`
- `src/main/resources/**`
- `Dockerfile`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Modify or add implementation files in src/main/java/...
- Update or add test files in src/test/java/... or its/src/test/java/...
- Update configuration or resource files if needed (e.g., Dockerfile, resources).
- Commit all related changes together.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.