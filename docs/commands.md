# Practice command examples

These examples complement the [collaboration guide](collaboration.md).
Replace account names, email addresses, and repository paths with your own.

## Check the current account and repository

```sh
gh api user --jq .login
gh repo view --json nameWithOwner,defaultBranchRef
git status --short
```

## Configure identity for this checkout

```sh
git config --local user.name "Your name"
git config --local user.email "YOUR_ID+YOUR_LOGIN@users.noreply.github.com"
git config --local --get user.email
```

Copy your exact noreply address from GitHub email settings. A local identity
setting affects this checkout without changing other repositories.

## Create a coauthored documentation change

Both contributors should contribute before using the coauthor trailer.

```sh
git switch -c docs/practice-example
# Edit the documentation together, then inspect the staged change.
git add docs/example.md
git diff --cached
git commit -m "Add a practice example" -m "Co-authored-by: Collaborator <VERIFIED_EMAIL>"
git show --format=fuller --stat HEAD
git push -u origin docs/practice-example
gh pr create --base main --title "Add a practice example" --body "Describe the change and its validation."
```

`docs/example.md` represents the file created during the exercise. The two
`-m` options keep a blank line before the coauthor trailer.

## Verify the merge

```sh
gh pr view PR_NUMBER --json state,mergedAt,url
```

Confirm the state is `MERGED` and the commit page links the intended authors.
Inspect the profile separately to see whether GitHub has awarded a badge.
