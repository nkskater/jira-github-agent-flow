# Jira → GitHub development workflow

A reusable story-to-merge workflow for coding environments and human contributors.
Jira records claims and ownership. GitHub branches, development commits and PRs
carry the exact story key. Native Jira Development integration supplies the reverse
link; comments alone are not enough.

- [Shared lifecycle](tools/development-workflow/WORKFLOW.md)
- [Setup, adoption, integration diagnostics and maintenance](tools/development-workflow/README.md)
- [Example repository configuration](.github/development-workflow.json)
- [PR policy and tests](tools/development-workflow/policy.mjs)
- [Merge guard](tools/development-workflow/merge.mjs)

## Start here

Replace **all example settings** before enabling the policy for an application:
Jira origin, project keys, repository, base branch, statuses, local checks and
required CI check names. Update the PR template and workflow branch filter too.
The example values are placeholders and do not connect to a real Jira project.

Run the dependency-free test suite with Node 22:

```sh
node --test tools/development-workflow/*.test.mjs
```

Copy the package and GitHub templates into the target application, add the entry
point, and follow the adoption guide. No secrets, user IDs, real Jira sites or
local machine configuration belong in this reference repository.

## Reference repository CI

This reference repository runs its package tests without requiring a live Jira
project. The application policy workflow is provided as an adoption template;
activate it only in repositories with configured Jira stories. Initial publication
is a bootstrap commit; future development follows the adopting project's workflow.
