# GitHub Governance v1 — Organization Standard

GITHUB_GOVERNANCE_VERSION = 1

## Scope

This document defines the organization-wide GitHub lifecycle standard. Product-specific governance remains authoritative for product/runtime behavior.

## Mandatory lifecycle

- direct push to `main` is prohibited
- a pull request is mandatory
- PR Quality Gate must pass before merge
- Human Approval is mandatory after the final material PR change
- Auto Merge is disabled
- merge is manual after Human Approval
- Post-Merge Full Validation runs on the default branch
- post-merge failure blocks release/formal closure until corrected or reverted

## PR Quality Gate

Required categories:

- repository safety
- Ruff correctness lint
- type checking
- governance validation
- critical smoke tests
- important unit tests

Target: <= 3 minutes. Preferred for Python AI repositories: 1-2 minutes.

## Post-Merge Full Validation

Required categories:

- full regression
- integration
- E2E
- exhaustive validation

Python repositories use `pytest -n auto --dist worksteal` after bounded repository-specific compatibility validation.

## Central CI

Shared execution policy is owned by `office138-org/ci-standards`. Product repositories should contain thin caller workflows rather than copied CI orchestration.

## GitHub Free private-repository control

Where paid private-repository enforcement is unavailable, Human Approval and PR-only change are operational controls augmented by the central post-merge merged-PR provenance check. A default-branch push not associated with a merged PR fails with `GOVERNANCE_VIOLATION_DIRECT_MAIN_PUSH`.

## Public central repositories

Organization standard repositories are public and should use GitHub Free branch protection to require PR-based changes and Human review wherever repository settings support it.
