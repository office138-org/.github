# Organization Contribution Standard

All repositories adopting GitHub Governance v1 use the following lifecycle:

1. Work on a non-main branch.
2. Open a pull request.
3. Pass the repository's PR Quality Gate.
4. Obtain Human Approval after the final material change.
5. Merge manually; Auto Merge remains disabled.
6. Verify Post-Merge Full Validation.

Direct push to `main` is prohibited.

PR CI should contain repository safety, lint, type checking, governance validation, critical smoke tests, and important unit tests. Comprehensive regression, integration, E2E, and exhaustive validation belong post-merge.

If post-merge validation fails, stop release/formal-closure activity until an immediate corrective PR or revert restores a compliant green default branch.
