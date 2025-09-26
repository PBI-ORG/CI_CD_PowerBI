# CI/CD Solution for Power BI

Implementing CI/CD for Power BI with Azure DevOps provides structure, collaboration, and governance for your report development lifecycle. By integrating version control with Azure Repos, teams can track changes, collaborate securely, and restore previous versions when necessary. Automated deployment pipelines promote reports and datasets across workspaces (Dev, Test, Prod), minimizing manual effort, reducing errors, and enforcing consistent standards. This streamlined approach accelerates development, enhances data reliability, and ensures full visibility into how business reports evolve over time.

## 📝 Create an Azure DevOps Organization Account

To set up your CI/CD solution for Power BI, you’ll first need an **Azure DevOps Organization**. Follow these steps to create one for free:

### 1. Sign in with a Microsoft account
- Go to [[https://dev.azure.com](https://aex.dev.azure.com/me?mkt=en-US)]  
- Sign in using your Microsoft work account.

### 2. Create a new organization
- After signing in, select **New Organization**.  
- Confirm your region (choose the region closest to your team for performance).  
- Click **Continue**.  

### 3. Name your organization
- Provide a unique name for your Azure DevOps Organization.  
- Your organization will be accessible at a URL like: URL: https://dev.azure.com/<OrganizationName>/ 

### 4. Create your first project
- Once your organization is created, set up a project.  
- Choose a **project name**, **visibility** (PRIVATE), and **version control system** (Git recommended).  
- Click **Create Project**.  

### 5. Invite team members (optional)
- Go to **Organization Settings > Users**.  
- Add members by email and assign access levels (**Basic**, **Stakeholder**, etc.).

  <img width="852" height="925" alt="image" src="https://github.com/user-attachments/assets/984c4a76-66bb-40cc-ade6-68be41fffded" />

  <img width="2568" height="408" alt="image" src="https://github.com/user-attachments/assets/d50f1d3e-6df7-4e15-97f4-10307c64d908" />



✅ You now have an **Azure DevOps Organization** ready to use for managing repositories, pipelines, and deploying your Power BI CI/CD solution.

## 📦 How to Create a New Repository in Azure DevOps

To create a new repository in your Azure DevOps organization, follow these steps:

1. Go to [https://dev.azure.com](https://dev.azure.com) and sign in.  
2. Select your **organization** and then choose your **project**.  
3. In the left-hand menu, go to **Repos**.  
4. Click the **dropdown next to the current repository name** and select **New Repository**.

<img width="838" height="302" alt="image" src="https://github.com/user-attachments/assets/1bf9a733-ff00-44c7-815c-dc2bb5fe07a4" />

   
5. Enter a **repository name**.
6. Optionally, check **Add a README** to initialize the repository.  
7. Click **Create** to finish.  

Your new repository will now be available under **Repos** in your Azure DevOps project.  

---

## 🌿 Branching Strategy

We recommend using three main branches to structure your development workflow in Azure DevOps:

- `main` – Production-ready code (default branch).  
- `dev` – Ongoing development work.  
- `test` – Integration testing before merging into `main`.  

📌 In Azure DevOps, you can enforce branch policies (e.g., requiring pull requests, code reviews, or build validations) under **Project Settings > Repositories > Branches**. This ensures consistent quality and governance across your Power BI CI/CD pipeline.


## 🔗 Connecting Azure DevOps to Power BI Workspaces

We integrate Power BI with Azure DevOps to enable source control and versioned deployment of reports and datasets across three separate environments:

- `Prod` workspace ⟶ `main` branch  
- `Test` workspace ⟶ `test` branch  
- `Dev` workspace ⟶ `dev` branch  

---


### ⚙️  Link Azure DevOps to Power BI

1. In the Power BI service, navigate to the target workspace (e.g., `Dev`, `Test`, or `Prod`).  
2. Go to **Workspace Settings** > **Git Integration**.
3. Choose **Azure DevOps (Repos)** as the Git provider.
4. Click **Connect**.

   <img width="820" height="654" alt="image" src="https://github.com/user-attachments/assets/2109286d-b2d3-4c76-a8e5-58310211c379" />

6. Provide the required details when prompted:  
   - **Organization**
   - **Project** 
   - **Git repository**  
   - **Branch**: main,dev or test

     <img width="783" height="784" alt="image" src="https://github.com/user-attachments/assets/1e057398-63a9-4754-8a0c-50794ba2f795" />
 
7. Click **Connect and sync**.  

Once connected, your Power BI workspace will stay in sync with the chosen Azure DevOps branch, enabling automated version control and structured deployments across environments.



-----------------------------------------------------------------


## ⚙️ Set up the necessary tools to manage the Repositories from Remote

### 📥 Download and Install Visual Studio Code

To work with this project, we recommend using [Visual Studio Code (VS Code)](https://code.visualstudio.com/), a free and powerful source-code editor.

#### 🔽 Step 1: Download

Visit the official Visual Studio Code website:

👉 [https://code.visualstudio.com/](https://code.visualstudio.com/)

Click the **Download** button for your operating system

#### 🛠️ Step 2: Install

#### On Windows:
1. Run the downloaded `.exe` file.
2. Follow the setup instructions.
3. ✅ Recommended: Select **"Add to PATH"** during installation.

#### 🧩 Step 3: Install VS Code Extensions

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


### 🔧 Install Git

Git is required to clone this repository and manage version control. Follow the steps below to install Git on your system.

#### 🔽 Step 1: Download Git

Visit the official Git website:

👉 [https://git-scm.com/](https://git-scm.com/)

Click the **Download** button for your operating system.


#### 🛠️ Step 2: Install Git

#### On Windows:
1. Run the downloaded `.exe` file.
2. Follow the installation wizard.
3. ✅ Recommended: Keep default settings unless you have specific preferences.

### 👤 Set Up Git Username and Email

Before making commits, configure your Git identity:

#### 📌 Run these commands in **Git Bash**:

```bash
git config --global user.name "Your Full Name"
git config --global user.email "your.email@example.com"
```
---

### 📂 Cloning the Repository Using Visual Studio Code

You can easily clone a repository to your local machine using Visual Studio Code. Follow these steps:

#### 🔗 Step 1: Copy the Repository URL

1. Go to the AzureDevOps repository.
2. Click the **Clone** button.

   <img width="2290" height="213" alt="image" src="https://github.com/user-attachments/assets/0038e776-9cf4-4c50-8489-904d1e866171" />

3. Copy the **HTTPS** URL or just click on **Clone in VS Code**


#### 💻 Step 2: Open VS Code and Clone

1. Open **Visual Studio Code**.
2. Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on macOS) to open the **Command Palette**.
3. Type and select `Git: Clone`.
4. Paste the repository URL you copied earlier and press **Enter**.
5. Choose a folder on your computer where the repository will be saved.

#### ✅ Step 3: Open the Project

Once cloning is complete, VS Code will ask:

> **"Would you like to open the cloned repository?"**

Click **Open** to load the project in VS Code.

---

## 📂 Organizing Power BI Files in the Repository
To enable smooth integration of Power BI reports in our CI/CD pipeline, we recommend saving your Power BI project files using the Power BI Project (PBIP) format. This format breaks down your report into structured, source-control-friendly JSON files alongside the dataset and report definitions.

📌 Why Use .pbip?
Easier to track changes with Git

Enables code review and versioning for report definitions

Supports better collaboration and CI/CD automation

Avoids storing large binary .pbix files which aren't diff-friendly

📥 How to Save as PBIP
1. In Power BI Desktop (from version December 2022+), go to File → Save As

2. Select Power BI Project Files (*.pbip)

3. Choose your project folder within the repository (if applicable)

##### ℹ️  If you don't have the option for saving a Power BI file as .Pbip you should enable the following options from Power BI desktop:

![Pbip](https://github.com/user-attachments/assets/d1d9105b-1f48-48e4-84ac-a48d3e296388)

---





