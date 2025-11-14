## 1. Add the developer as a collaborator
1. Go to your GitHub repository.
2. Navigate to **Settings** → **Collaborators and teams** → **Add people**.
3. Add the GitHub username of the developer.
4. Set their permission as **"Write"** (this allows them to create branches and submit pull requests but not push directly to protected branches).

---

## 2. Set up branch protection
You need to protect your `main` (or `master`) branch so that:
- The developer cannot push directly to it.
- All changes must go through a **pull request**.
- You must **review and approve** the pull request before merging.

### Steps:
1. Go to **Settings** → **Branches**.
2. Under **Branch protection rules**, click **"Add branch protection rule."**
3. Set the following options:
   - **Branch name pattern**: Set to `main` or `master` (or your default branch).
   - **Require a pull request before merging**
     - Enable **"Require approvals"** → Set to **1 or more** (this means you need to approve before merging).
   - **Require status checks to pass before merging** (if you have any CI/CD tests).
   - **Include administrators** – if you want to apply the rule to yourself as well.
4. Save the rule.

---

## 3. Workflow for the Developer
1. The developer can:
   - Clone the repo.
   - Create a new branch.
   - Commit and push to that branch.
   - Open a pull request (PR) against the `main` branch.
2. You will receive a notification about the pull request.
3. You can:
   - Review the code.
   - Request changes or approve it.
   - Merge the PR once you’re satisfied.
   - The developer **cannot merge it themselves** unless you give them admin rights.

---

## 4. (Optional) Set Up CODEOWNERS for Auto Reviews
You can create a `CODEOWNERS` file to automatically assign yourself as a reviewer for every pull request:

1. Create a `.github/CODEOWNERS` file in your repository.
2. Add this content:
```plaintext
* @your-github-username
```
This ensures that you're always added as a reviewer for any changes.

---

## 5. (Optional) Use GitHub Actions for Automatic Checks
If you want to automatically check for code quality or tests before merging:
- Set up GitHub Actions to run checks (like linting, tests, etc.).
- Enable **"Require status checks to pass before merging"** in branch protection rules.

---

## Summary
🔹 Add the developer with **write access**.  
🔹 Enable **branch protection** to prevent direct pushes.  
🔹 The developer can create PRs but **cannot merge** without your approval.  
🔹 Use **CODEOWNERS** for automatic review requests (optional).  
🔹 Use **GitHub Actions** for additional automated checks (optional).  