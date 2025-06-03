# How to Reset the HEAD of a Branch for Already Pushed Commits

If you need to reset your branch to a previous commit (removing some commits that have already been pushed), follow these steps:

## 1. Hard Reset to the Desired Commit

Find the commit hash you want to reset to (e.g., `abc1234`):

    git log

Then reset:

    git reset --hard abc1234

## 2. Force Push to Remote

This will overwrite the remote branch with your local state:

    git push --force

**Warning:** This rewrites history and can affect collaborators. Communicate with your team before force-pushing.

## Alternative: Revert Commits (Safer)

If you don't want to rewrite history, you can revert the commits instead:

    git revert <commit_hash_1> <commit_hash_2> ...

This creates new commits that undo the changes.
