# Builder Operating Procedure

Use this procedure for small sandbox builder tasks only.

## Scope

Allowed tasks:

- Documentation additions or edits.
- Small text-only cleanup.
- Reviewer fixture maintenance.
- Changes that touch one narrow area and are easy to reverse.

Do not use this builder for:

- Production repositories.
- Secrets or credentials.
- Vault or Personal Zone content.
- Runtime, daemon, service, or LaunchAgent changes.
- Mac mini, DGX, or OpenClaw work.
- Broad refactors or ambiguous cleanup.

## Request Format

Create a GitHub issue or PR body that states:

- The exact file or narrow area to change.
- The expected outcome.
- Any files that must not be touched.
- Whether auto-merge is allowed after GPT approval.

## Review Gate

Every PR must pass the required status check:

- GPT schema review

The verdict must be APPROVE before merge.

Do not merge when the verdict is MODIFY, REJECT, or BLOCKED.

## Stop Rules

Stop if:

- The PR touches files outside the request.
- The diff contains secret-like material.
- The reviewer returns anything except APPROVE.
- The task crosses a protected boundary.
- The requested scope is unclear.

## Recovery

If a bad sandbox PR merges:

- Record the PR number and verdict.
- Fix the reviewer prompt or workflow first.
- Rerun the failing fixture.
- Do not promote the workflow until the rerun passes.
