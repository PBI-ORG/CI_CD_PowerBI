📊 CI/CD PowerBI Git Branching Workflow

This project uses a linear history workflow with 3 main branches:
- Prod — live, production-ready state
- Test — staging for QA and validation
- Dev — active development

---

🔀 Branching Flow:

Dev → Test → Prod

- New features are developed in Dev.
- Approved changes are moved to Test for QA.
- Validated changes are promoted to Prod.

---

📦 Commands and Workflow

✅ Develop in Dev:

-git checkout Dev
-Make your changes
-git add .
-git commit -m "Describe your changes"
-git push

---

🚀 Move changes from Dev to Test (linear rebase):

-git checkout Test
-git pull --rebase origin Test
-git rebase Dev
-git push

---

📦 Move changes from Test to Prod (linear rebase):

-git checkout Prod
-git pull --rebase origin Prod
-git rebase Test
-git push

---

🔧 Feature Branch Workflow (Recommended):

-git checkout Dev
-git checkout -b feature/my-new-feature
-Do your work
-git add .
-git commit -m "Add my new feature"
-git checkout Dev
-git rebase feature/my-new-feature
-git push

---

📖 Notes:

- Use git rebase instead of git merge to avoid messy merge commits.
- Protect Prod and Test branches in GitHub settings.
- Squash feature branch commits before rebasing.
- Avoid force-push on shared branches unless agreed by the team.

---

✅ Summary

| Branch | Purpose                  | Move Changes With         |
|:--------|:-----------------------------|:----------------------------|
| Dev     | Active development       | Direct commits, squash, rebase |
| Test    | Staging for QA/review    | git rebase Dev             |
| Prod    | Live, stable production  | git rebase Test            |

---



