📊 CI/CD PowerBI Git Branching Strategies

This project uses 3 main branches:
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

## Different Merging Strategies ##


### Using Git Merge ###

📦 Commands and Workflow

#### ✅ Develop in Dev:

```bash
git checkout Dev
# Make your changes
git add .
git commit -m "Describe your changes"
git push
```
#### 🚀 Move changes from Dev to Test (with merge):

```bash
git checkout Test
git pull origin Test
git merge Dev
git push
```
#### 📦 Move changes from Test to Prod (with merge):

```bash
git checkout Prod
git pull origin Prod
git merge Test
git push
```

![image](https://github.com/user-attachments/assets/7e58a4e4-231b-4cf6-be9b-b805cd12d19f)


When Performing a git merge, git will create a new "merge commit" that ties together the histories of both branches. But if we do this a lot, we end up with lots of knots, which can make the history a bit messy.

### Using Git Rebase ###

📦 Commands and Workflow

#### ✅ Develop in Dev:
```bash
-git checkout Dev
-Make your changes
-git add .
-git commit -m "Describe your changes"
-git push
```

#### 🚀 Move changes from Dev to Test (linear rebase):

```bash
git checkout Test
git pull --rebase origin Test
git rebase Dev
git push
```


#### 📦 Move changes from Test to Prod (linear rebase):
```bash
-git checkout Prod
-git pull --rebase origin Prod
-git rebase Test
-git push
```




Before Rebase:

![image](https://github.com/user-attachments/assets/94bb8c42-0ced-46c5-8014-4842c92efc7b)

After rebase

![image](https://github.com/user-attachments/assets/ff0f8c26-b2ef-4d69-8b08-56a9ed3bf9e2)

Using git rebase let us keeping a linear history.


### Using Git Squash ###

📦 Commands and Workflow

#### 1. Start from your development branch
```bash
git checkout Dev
```
#### 2. Create a feature branch
```bash
git checkout -b feature/my-new-feature
```
#### 3. Work and commit as usual (multiple commits possible)
```bash
git add .
git commit -m "First part of feature"
git add .
git commit -m "Second part of feature"
```
#### 4. Once your feature is ready, squash commits interactively
```bash
git rebase -i Dev
```

#### In the editor that opens:
- leave the first commit as 'pick'
- change the following commits to 'squash' or 's'
- save and close editor

#### 5. Move your squashed feature branch changes back into Dev (choose one):

#### Option A: Merge (creates a merge commit)

```bash
git checkout Dev
git merge feature/my-new-feature
git push
```

##### Option B: Rebase (linear history, preferred)
```bash
git checkout Dev
git rebase feature/my-new-feature
git push
```


Before

![image](https://github.com/user-attachments/assets/87b3c8bd-f604-48b0-b7bb-1df8f94b611d)


After

![image](https://github.com/user-attachments/assets/96a412c0-b02f-44e3-9404-ce64547041a4)


Squash commit keeps history linear but we lose teh fine details of individual feature commmits in the main branch's commit history.



🔧 Feature Branch Workflow (Recommended):

```bash
-git checkout Dev
-git checkout -b feature/my-new-feature
-Do your work
-git add .
-git commit -m "Add my new feature"
-git checkout Dev
-git rebase feature/my-new-feature
-git push
```

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



