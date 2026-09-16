---
title: Split Legacy And Simple KOS Repositories
task: BOOT-050
created: 2026-09-16
status: in-progress
---

# BOOT-050: Split Legacy And Simple KOS Repositories

## Goal

Preserve the current implementation as a legacy repository and make the canonical KOS name and local path available for a fresh KOS Simple implementation.

## User Outcome

The existing implementation remains available at `atilla777/kos_big` and `/home/aleksei/plums/kos_big`, while a new public `atilla777/kos` repository at `/home/aleksei/plums/kos` provides a clean starting point for KOS Simple.

## Context

The current repository is clean and synchronized at `9514cd5`. Its architecture is intentionally being replaced rather than migrated incrementally. The approved KOS Simple specification remains in Obsidian until the following normative architecture-reset task.

## Requirements

- Rename the current public GitHub repository to `atilla777/kos_big` without rewriting its history.
- Rename the current local directory to `/home/aleksei/plums/kos_big` and update its `origin` URL.
- Create a new public `atilla777/kos` repository with an independent history and `main` default branch at `/home/aleksei/plums/kos`.
- Initialize the new repository with only a concise README and the task record for this repository split.
- Do not copy the Rails application or legacy Git history into the new repository.
- Preserve the approved KOS Simple specification in Obsidian for the next normative architecture-reset task.

## Non-Goals

- Implementing KOS Simple.
- Moving the approved specification into normative repository documentation.
- Completing the legacy quick-fix workflow.
- Maintaining old `atilla777/kos` links as links to the legacy implementation.

## Acceptance Criteria

- Both `atilla777/kos_big` and `atilla777/kos` exist and are public.
- Both local repositories have clean `main` branches synchronized with their respective `origin/main`.
- The legacy repository retains its existing history plus this administrative task record.
- The new repository has an independent root commit and contains no legacy application code.
- The external dashboard, roadmap, backlog, and archive identify the reset and the next task.

## Implementation Plan

1. Record this approved baseline and update the external development plan.
2. Commit and push this final administrative record to the existing repository.
3. Rename the GitHub repository and update its local remote.
4. Rename the local legacy directory.
5. Create the new local repository with a concise README and repository-split task record.
6. Create the new public GitHub repository and push `main`.
7. Verify names, remotes, branches, visibility, history separation, and clean worktrees.
8. Record completion in the external development plan.

## Verification

- Inspect both repositories with `gh repo view`.
- Run `git status --short --branch`, `git remote -v`, and compare local HEAD with `origin/main` in both repositories.
- Confirm the new repository has an independent root commit and no legacy application files.

## Risks

- Existing links to `atilla777/kos` will identify KOS Simple after the canonical name is reused.
- External clones of the legacy repository should update their remote to `atilla777/kos_big` rather than relying on redirects.
