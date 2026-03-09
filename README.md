# Modules

This repository is intended to add new third party JASP modules.
If anything is unclear just send us a message on our mattermost server or by making an issue [here](https://github.com/jasp-stats/jasp-issues/issues)

# How to add a new module

### Option 1
Send us message or by making an issue [here](https://github.com/jasp-stats/jasp-issues/issues), we love to be in contact and help you out!

### Option 2

- fork this repository
- add a new `yaml` file in `modules-metadata` folder with the following structure:

```yaml
name: "ModuleName" 
gitUrl: "Your JASP module git repository"
```

- create a pull request to this repository
- after review, and successful merge, your module will be added to the `beta-modules` folder

# How to Update Your Community Module

When you have new features or bug fixes ready, Open a Pull Request (PR) against **our fork** of your module. 

Here is how the process works:

## Step-by-Step Workflow

### 1. Locate Our Fork
Find our organization's fork of your module. It will typically be located at:
`https://github.com/jasp-stats-modules/[Your-Module-Name]`

### 2. Open a Pull Request Across Forks
Because you are sending changes from your repository to our fork, you need to use GitHub's cross-fork comparison feature.



1. Go to **our fork** of your repository on GitHub.
2. Click the **Pull requests** tab, then click the green **New pull request** button.
3. On the Compare page, click the link that says **"compare across forks"**.
4. Set up the dropdowns exactly like this:
   * **base repository:** `jasp-stats-modules/[Your-Module-Name]` (Our fork)
   * **base:** `master` or `main` (Our default branch)
   * **head repository:** `jasp-stats-modules/[Your-Module-Name]` (Your original repository)
   * **compare:** `your-update-branch` (The branch with your new changes)
5. Click **Create pull request**.

### 3. The Review Process
Once your PR is open on our fork, our team will be notified. 
* We will review your code to ensure it integrates smoothly with the current ecosystem.
* We may leave comments or request minor adjustments.
* Once approved, we will merge the PR into our fork. 

### 4. Automated Sync
You're done! Once your code is merged into our fork, our automated systems will detect the update and sync it into the main application for the next release.

---
*If you run into any permission issues or have questions about the review process, please reach out to us!*
