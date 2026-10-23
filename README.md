# Project Documentation: Hosting a Static Website Using GitHub Pages

## 1. Project Overview

**Project Name:** Simple HTML Website Hosting Using GitHub Pages

**Objective:** Create a simple static website using HTML, store the source code in a GitHub repository, and deploy it using GitHub Pages. Update the website through Git and verify that the latest changes are available at the same public URL.

**GitHub Repository:** [https://github.com/praful0419/simple-html-website](https://github.com/praful0419/simple-html-website)

**Live Website:** [https://praful0419.github.io/simple-html-website/](https://praful0419.github.io/simple-html-website/)

## 2. Technologies and Tools Used

- **HTML5:** To create the website.
- **Git:** For version control and tracking code changes.
- **GitHub:** To store and manage the source code remotely.
- **GitHub Personal Access Token (PAT):** To authenticate Git operations over HTTPS.
- **GitHub Pages:** To host and publish the static website.
- **Ubuntu Linux Terminal:** To execute Git commands and manage the local project.

## 3. Project Implementation Steps

### Step 1: Create a GitHub Repository

Created a new GitHub repository named `simple-html-website` to store the website's source code.

Repository URL:

[https://github.com/praful0419/simple-html-website](https://github.com/praful0419/simple-html-website)

### Step 2: Clone the Repository Locally

Cloned the remote repository to the local Ubuntu system using Git.

```bash
git clone https://github.com/praful0419/simple-html-website.git
cd simple-html-website
```

### Step 3: Create the HTML Website

Created an `index.html` file in the project directory and added the initial HTML code.

The `index.html` file serves as the default entry point for the static website.

### Step 4: Configure Git Authentication

Used a GitHub Personal Access Token (PAT) to authenticate Git operations over HTTPS when pushing local changes to GitHub.

The token was used for authentication instead of a GitHub account password.

**Security note:** A PAT should be kept private and never committed to the repository or shared publicly.

### Step 5: Push the Website Code to GitHub

Added, committed, and pushed the website files to the remote repository.

```bash
git add index.html
git commit -m "uploading-html-file"
git push
```

### Step 6: Configure GitHub Pages

Opened the repository's **Settings → Pages** section and configured GitHub Pages to publish the website from the appropriate branch and directory.

The published website became accessible at:

[https://praful0419.github.io/simple-html-website/](https://praful0419.github.io/simple-html-website/)

### Step 7: Update the Website

Modified the existing `index.html` file to introduce changes to the website.

Committed and pushed the updated code to the GitHub repository.

```bash
git add index.html
git commit -m "updating-code-in-index-file"
git push
```

### Step 8: Verify the Deployment

Opened the live website at the same GitHub Pages URL and verified that the updated content was being served.

A hard refresh (`Ctrl + Shift + R`) can be used to rule out browser caching when changes are not immediately visible.

## 4. Challenge Faced: Divergent Git Branches

During an update, a Git pull operation failed because the local `main` branch and remote `origin/main` branch had diverged.

The terminal displayed the following error:

```text
hint: You have divergent branches and need to specify how to reconcile them.
fatal: Need to specify how to reconcile divergent branches.
```

### Root Cause

The local and remote branches contained different commits. Git required an explicit strategy for integrating the remote changes with the local branch before proceeding.

### Solution: Git Rebase

Used Git rebase to integrate the remote changes into the local branch's history.

```bash
git rebase
```

The command completed successfully and reported:

```text
Successfully rebased and updated refs/heads/main.
```

After the rebase, pushed the updated code to GitHub.

**Technical note:** `git rebase` without additional arguments uses the configured upstream branch when one is set. In other situations, the appropriate command may be `git pull --rebase origin main`. If conflicts occur, they must be resolved before the rebase can finish.

Rebasing helped reconcile the divergent histories while maintaining a linear commit history.

## 5. Final Deliverables

- **GitHub Repository:** [https://github.com/praful0419/simple-html-website](https://github.com/praful0419/simple-html-website)
- **Live Website:** [https://praful0419.github.io/simple-html-website/](https://praful0419.github.io/simple-html-website/)

The project demonstrates the complete workflow of creating a static website, managing source code with Git, authenticating with GitHub using a PAT, deploying with GitHub Pages, troubleshooting divergent branches, and publishing subsequent updates.

## 6. Key Learnings

- Creating and managing repositories on GitHub.
- Cloning a remote repository to a local Linux environment.
- Creating and updating HTML files.
- Using Git commands for staging, committing, pulling, rebasing, and pushing changes.
- Authenticating Git operations with a Personal Access Token.
- Configuring GitHub Pages for static website hosting.
- Troubleshooting divergent branches and understanding Git history reconciliation.
- Verifying updates on a deployed website.

## 7. Conclusion

Successfully created and deployed a static HTML website using GitHub Pages. The project also involved troubleshooting a Git branch divergence issue using rebase and pushing the updated website code to the remote repository. The final website is publicly accessible through its GitHub Pages URL.
