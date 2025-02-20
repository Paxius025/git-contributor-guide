# **Comprehensive Guide to Using Git: Tips, Commands, and Best Practices**

Git is an essential tool for **contributors** who want to collaborate on open-source projects effectively. This guide covers key Git commands, best practices, and troubleshooting tips for managing branches, syncing with the upstream repository, resolving merge conflicts, and optimizing workflow efficiency.

[🇺🇸 English](./Contributor-guide.md) | [🇹🇭 ภาษาไทย](./Contributor-guide_th.md)

---


## **🔹 Essential Git Commands for Contributors**

### **1️⃣ Cloning a Repository**
Before making any contributions, you need to clone the repository

```sh
git clone https://github.com/your-username/repository-name.git
cd repository-name
```

If you're working on a forked repository, set up the upstream remote

```sh
git remote add upstream https://github.com/original-owner/repository-name.git
git remote -v  # Verify remotes
```

---

### **2️⃣ Creating a New Branch**
Never work directly on the `main` branch. Always create a new branch

```sh
git checkout -b feature/add-dark-mode
```

**Branch naming conventions:**
✅ `feature/add-dark-mode` → Adding a new feature  
✅ `bugfix/fix-login-issue` → Fixing a bug  
❌ `update` → Not descriptive enough  
❌ `fix` → Too vague  

---

### **3️⃣ Making Changes and Committing**

Check modified files before committing

```sh
git status
```

Stage and commit files with meaningful messages

```sh
git add filename1 filename2  # Or use git add .
git commit -m "🔧 Fix login issue affecting special characters"
```

#### **Commit Message Best Practices:**
- Use **clear and concise messages**
- Prefix messages with relevant icons or keywords:
  - 🆕 `feat:` for new features
  - 🐞 `fix:` for bug fixes
  - 📄 `docs:` for documentation updates
  - 🔧 `chore:` for maintenance tasks

**Example of a good commit message:**
```sh
git commit -m "🐞 Fix issue #42: Resolve login bug when using special characters"
```

---

### **4️⃣ Pushing Changes to GitHub**

After committing, push your branch to GitHub

```sh
git push origin feature/add-dark-mode
```

---

### **5️⃣ Opening a Pull Request (PR)**

Go to GitHub and open a **Pull Request (PR)**
- Select the correct branch
- Add a meaningful PR title
- Provide a clear description with relevant Issue links, e.g., `Fixes #42`

**Example PR description:**
```
## 🔥 What does this PR do?
- Fix login issue when email contains special characters
- Improve authentication flow

## ✅ How to test
- Try logging in with an email like `user+test@example.com`
- Ensure authentication works correctly
```

---

### **6️⃣ Syncing with Upstream Repository**

If the original project (upstream) has new updates, pull the latest changes before continuing your work

```sh
git fetch upstream
git checkout main
git merge upstream/main
```

Update your feature branch
```sh
git checkout feature/add-dark-mode
git rebase main
```

---

### **7️⃣ Handling Merge Conflicts**

If you encounter a merge conflict
- Open the conflicted files and look for `<<<<<<< HEAD` and `>>>>>>> branch-name`
- Manually resolve the conflicts
- Add the resolved files and commit:

```sh
git add conflicted-file.js
git commit -m "🔀 Resolve merge conflict in conflicted-file.js"
```

---

### **8️⃣ Deleting a Merged Branch**

Once your PR is merged, delete the branch

```sh
git branch -d feature/add-dark-mode  # Local branch
git push origin --delete feature/add-dark-mode  # Remote branch
```

---

## **🛠️ Git Workflow Optimization Tips**

### **🔹 Using Git Stash to Save Uncommitted Changes**
If you need to switch branches but have uncommitted changes

```sh
git stash  # Save changes temporarily
git checkout main
git stash pop  # Restore saved changes
```

### **🔹 Using Git Log for a Clear History**

```sh
git log --oneline --graph --decorate --all
```

### **🔹 Interactive Rebase to Squash Commits**
For a cleaner commit history, squash multiple commits into one

```sh
git rebase -i HEAD~3
```

### **🔹 Setting Up Git Aliases for Efficiency**

```sh
git config --global alias.co checkout
git config --global alias.cm "commit -m"
git config --global alias.st status
```
Now you can use
```sh
git co -b new-feature  # Instead of git checkout -b new-feature
git cm "Updated readme"  # Instead of git commit -m "Updated readme"
```

---

## **🎯 Summary**
✅ **Clone & Fork** → Bring the project to your workspace  
✅ **Branch Management** → Create branches for structured work  
✅ **Commit Messages** → Keep messages clear and meaningful  
✅ **Push & PR** → Submit work and provide detailed PR descriptions  
✅ **Stay Updated** → Sync with upstream regularly  
✅ **Resolve Conflicts** → Handle merge conflicts carefully  
✅ **Optimize Workflow** → Use aliases, stash, and rebase to improve efficiency  

Mastering Git will make your workflow **smoother, faster, and more organized! 🚀**
