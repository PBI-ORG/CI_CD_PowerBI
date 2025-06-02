## 📝 Create a Free GitHub Organization Account

To set up your CI/CD solution for Power BI, you'll need a **GitHub Organization account**. Follow these steps to create one for free:

### 📌 Steps to Create a GitHub Organization:

1. **Go to GitHub**
   - Visit [https://github.com](https://github.com) and sign in with your existing GitHub account.
   - If you don’t have one, [create a personal GitHub account first](https://github.com/join).

2. **Create a New Organization**
   - Click on your profile icon in the top-right corner.
   - Select **Your organizations** from the dropdown menu.
   - On the **Organizations** page, click **New organization**.

3. **Choose a Plan**
   - Select the **Free** plan and click **Continue**.

4. **Enter Organization Details**
   - **Organization account name:** Enter a unique name for your organization.
   - **Contact email:** Add an email address for organization notifications.
   - Click **Next**.

5. **Invite Team Members (Optional)**
   - You can invite team members now or skip this step and add them later.

6. **Complete Setup**
   - Click **Create organization**.

✅ Your GitHub Organization is now created and ready for setting up your CI/CD solution!


### 📌 Set up Organization Role Permissions

For a full and up-to-date list of permissions for each organization role, see the official [GitHub Docs: Permissions for organization roles](https://docs.github.com/en/organizations/managing-peoples-access-to-your-organization-with-roles/roles-in-an-organization#permissions-for-organization-roles).


## 📦 How to Create a New Repository

To create a new repository in your GitHub organization, go to [https://github.com](https://github.com), click your profile icon in the top-right corner, and select **Your organizations**. Choose your organization, then click the green **New** button on the **Repositories** tab. Enter a repository name, description (optional), and choose whether it will be **public** or **private**. You can also initialize it with a README file if you’d like. Finally, click **Create repository** to finish.


## 🌿 Branching Strategy

We use three main branches to organize our development workflow:

- `main` – Production-ready code (default branch)
- `dev` – Ongoing development
- `test` – Integration testing before merging into `main`


## 🔗 Connecting GitHub to Power BI Workspaces

We integrate Power BI with GitHub to enable source control and versioned deployment of reports and datasets across three separate environments:

- `Prod` workspace ⟶ `main` branch
- `Test` workspace ⟶ `test` branch
- `Dev` workspace ⟶ `dev` branch

### 🛠️ Step 1: Create a GitHub Personal Access Token (PAT)

1. Go to your GitHub account.
2. Navigate to **Settings** > **Developer settings** > **Personal access tokens** > **Tokens (classic)**.
3. Click **Generate new token (classic)**.
4. Select the appropriate scopes (minimum required for Power BI GitHub integration):
   - `repo` (Full control of private repositories)
5. Set an expiration date (e.g., 90 days).
6. Click **Generate token** and **copy the token** immediately — you won’t be able to see it again.

### ⚙️ Step 2: Link GitHub to Power BI

1. In the Power BI service, go to the workspace (e.g., `Dev`, `Test`, or `Prod`).
2. Click **Workspace Settings** > **Git Integration**.
3. Choose **GitHub** as the source and clieck **Connect**.
4. You will need to provide **Display name**, **Repository URL**, **Personal access token** when prompted.
![image](https://github.com/user-attachments/assets/f633b98c-4a43-44e9-a5ef-621be503d5c1)


5. Select the correct:
   - **Repository**
   - **Branch**: choose `dev`, `test`, or `main` depending on the workspace.
   - (Optional) Specify a folder path if your Power BI files are not in the root directory.

### ✅ Branch-to-Workspace Mapping

| GitHub Branch | Power BI Workspace |
|---------------|--------------------|
| `main`        | Prod               |
| `test`        | Test               |
| `dev`         | Dev                |

---


## 🔐 How to Give Access to Specific People for a Single Repository

By default, organization members might have access to many repositories, but you can **limit access** and invite collaborators only to a specific repo:

### Steps to Grant Access to a Specific Repository:

1. **Go to the Repository**  
   Navigate to the specific repository in your GitHub organization where you want to manage access.

2. **Open Repository Settings**  
   Click on the **Settings** tab at the top of the repository page.

3. **Manage Access**  
   In the left sidebar, click **Collaborators & teams**.

4. **Invite Collaborators or Teams**  
   In section **Manage access** select **Direct access** then Click **Add people** or **Add teams** (if you want to give access to a whole team).

5. **Search and Select Users or Teams**  
   Enter the GitHub username(s) or team name(s) you want to grant access to and select them.

6. **Choose Permission Level**  
   Select the permission level for each collaborator:
   - **Read** — Can view and clone the repository.
   - **Triage** — Can manage issues and pull requests.
   - **Write** — Can push to the repository.
   - **Maintain** — Can manage the repository without access to sensitive or destructive actions.
   - **Admin** — Full control of the repository.

7. **Send Invitation**  
   Click **Send invitation** — the invited collaborators will get an email and must accept to gain access.

---

### Important Notes:

- Only repository **owners and admins** can manage access.
- Teams are the best way to manage permissions if you have multiple people needing the same access level.
- Organization members without explicit access to a repository cannot see or contribute to it.


## 📥 Download and Install Visual Studio Code

To work with this project, we recommend using [Visual Studio Code (VS Code)](https://code.visualstudio.com/), a free and powerful source-code editor.

### 🔽 Step 1: Download

Visit the official Visual Studio Code website:

👉 [https://code.visualstudio.com/](https://code.visualstudio.com/)

Click the **Download** button for your operating system

### 🛠️ Step 2: Install

#### On Windows:
1. Run the downloaded `.exe` file.
2. Follow the setup instructions.
3. ✅ Recommended: Select **"Add to PATH"** during installation.

### 🧩 Step 3: Install VS Code Extensions

To enhance your development experience, it's recommended to install the following Visual Studio Code extensions:

- **GitHub Pull Requests**  
  Manage GitHub pull requests and issues directly from VS Code.

- **GitHub Repositories**  
  Browse and edit GitHub repositories without cloning them locally.

- **Remote Repositories**  
  Work with source code in GitHub repositories without needing to clone them to your machine.

To install extensions:
1. Open VS Code.
2. Go to the **Extensions** view (`Ctrl+Shift+X` or `Cmd+Shift+X` on macOS).
3. Search for each extension by name and click **Install**.


## 🔧 Install Git

Git is required to clone this repository and manage version control. Follow the steps below to install Git on your system.

### 🔽 Step 1: Download Git

Visit the official Git website:

👉 [https://git-scm.com/](https://git-scm.com/)

Click the **Download** button for your operating system.


### 🛠️ Step 2: Install Git

#### On Windows:
1. Run the downloaded `.exe` file.
2. Follow the installation wizard.
3. ✅ Recommended: Keep default settings unless you have specific preferences.


## 📂 Cloning the Repository Using Visual Studio Code

You can easily clone a repository to your local machine using Visual Studio Code. Follow these steps:

### 🔗 Step 1: Copy the Repository URL

1. Go to the GitHub page of this repository.
2. Click the green **Code** button.
3. Copy the **HTTPS** URL (e.g., `https://github.com/your-username/your-repo.git`).

### 💻 Step 2: Open VS Code and Clone

1. Open **Visual Studio Code**.
2. Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on macOS) to open the **Command Palette**.
3. Type and select `Git: Clone`.
4. Paste the repository URL you copied earlier and press **Enter**.
5. Choose a folder on your computer where the repository will be saved.

### ✅ Step 3: Open the Project

Once cloning is complete, VS Code will ask:

> **"Would you like to open the cloned repository?"**

Click **Open** to load the project in VS Code.

---



## 📚 Branch Merging Strategies

This repository uses a structured branching strategy to manage feature development, testing, and production deployment.

### 🔀 Branch Overview

- **main** — Stable, production-ready code
- **dev** — Integration branch for ongoing development
- **test** — QA branch for feature validation before merging to `main`

---

### 🚀 Merge Types & Workflow

| Merge Type               | Usage                                                | Command / GitHub Option            |
|:-------------------------|:-----------------------------------------------------|:-----------------------------------|
| **Fast-Forward Merge**   | When no new commits in target branch since branching | `git merge --ff <source-branch>`   |
| **Three-Way Merge**      | When both branches have diverged                     | `git merge --no-ff <source-branch>`|
| **Squash and Merge**     | Combine multiple commits into one clean commit       | GitHub UI: _Squash and Merge_      |
| **Rebase**               | Reapply commits from one branch onto another         | `git rebase <target-branch>`       |

---

### 📊 Example Flow

1. Feature development happens in `test`.
2. Once tested, merge `test` into `dev` using **Fast-Forward** or **Three-Way Merge**.
3. QA completes on `dev`.
4. Merge `dev` into `main` using **Squash and Merge** for a clean history.

---

### 💡 Notes

- Always **sync `dev` and `test` with `main` regularly** to minimize merge conflicts.
- Use **Rebase** before merging long-running branches to keep history linear.











