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
   - **Display Name**: a friendly name for the connection  
   - **Repository URL**: the URL of your Azure DevOps repository (e.g., `https://dev.azure.com/<org>/<project>/_git/<repo>`)  
   - **Branch**: select the appropriate branch (`dev`, `test`, or `main`)  
   - **Personal Access Token**: paste the PAT you created in Step 1

     <img width="783" height="784" alt="image" src="https://github.com/user-attachments/assets/1e057398-63a9-4754-8a0c-50794ba2f795" />
 
7. Click **Connect and sync**.  

Once connected, your Power BI workspace will stay in sync with the chosen Azure DevOps branch, enabling automated version control and structured deployments across environments.





