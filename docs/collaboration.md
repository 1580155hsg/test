# Collaboration guide

## Account and author identity

Before committing, check the active GitHub account with `gh api user --jq .login`.
Use an email verified on that account, or its GitHub-provided noreply address.
Set identity in this repository with `git config user.name` and
`git config user.email` when different machines use different accounts.

## Coauthored changes

Use a `Co-authored-by: Name <verified-email>` trailer only for someone who
contributed to the change. Keep a blank line between the commit description
and trailers. Confirm the resulting commit links both authors before merging.

## Review and merge

Read the complete diff and verify links before merging documentation.
A solo practice change may be merged without a formal review when repository
rules allow it. Shared or production changes should follow that project's
review requirements. Do not relax branch protection just to earn a badge.

## Completion checklist

- The pull request targets the default branch.
- The change has a clear purpose and contains no credentials.
- Commit author attribution is correct.
- The pull request is merged, rather than merely closed.
- The temporary branch is deleted after merging.
- Any achievement result is checked on the profile; pending results are
  recorded as pending rather than claimed as earned.

[Return to the repository overview](../README.md).
