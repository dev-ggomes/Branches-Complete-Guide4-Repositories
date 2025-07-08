<!-- |||||||||||||||||||| EN - PT |||||||||||||||||||| -->
<p align='center'>
  <a href="https://github.com/dev-ggomes/Branches-Complete-Guide4-Repositories/blob/main/README.md">🇺🇸 English</a> | 
  <a href="https://github.com/dev-ggomes/Branches-Complete-Guide4-Repositories/blob/main/README-pt-pt.md">ᴘᴛ Português</a> | 
  <a href="https://github.com/dev-ggomes/Branches-Complete-Guide4-Repositories/blob/main/README-pt-br.md">🇧🇷 Português</a>
</p>

<!-- |||||||||||||||||||| TITLE |||||||||||||||||||| -->

<div align="center">
  
  # Branches Guide
  
  :octocat: A comprehensive, intuitive guide to mastering branches in Git and GitHub.

</div> 

<!-- |||||||||||||||||||| STARS |||||||||||||||||||| -->
<p align="center">
  ⭐ If you enjoyed this repository, please give it a star
</p>

<!-- |||||||||||||||||||| SPONSORS & STARS |||||||||||||||||||| -->
<p align='center'>
  <a href="https://github.com/sponsors/dev-ggomes"><img alt="Sponsor" src="https://img.shields.io/badge/sponsor-30363D?style=social&logo=GitHub-Sponsors&logoColor=#white" /></a>
  &nbsp;
  <a href="#"><img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/dev-ggomes/Branches-Complete-Guide4-Repositories?style=social" /></a>
</p>

<!-- |||||||||||||||||||| CONTENT |||||||||||||||||||| -->

## 📖 Table of Contents (TOC)

1. [About](#-about)
2. [⚙️ Glossary](#️-Glossary)
3. [🚀 Quickstart](#-quickstart)
4. [🌳 Branch Concepts](#-branch-concepts)
5. [🗂️ Branch Types](#️-branch-types)
6. [⚙️ Workflow](#️-workflow)

   * [GitHub Flow](#github-flow)
   * [Git Flow](#git-flow)
7. [🔧 Essential Operations](#-essential-operations)

   * [Create a Branch](#create-a-branch)
   * [Update a Branch](#update-a-branch)
   * [Publish a Branch](#publish-a-branch)
   * [Pull Request & Merge](#pull-request-merge)
8. [⏰ When to Use Each Branch](#-when-to-use-each-branch)
9. [👍 Best Practices](#-best-practices)
10. [🚀 Next Steps](#-next-steps)

---

## 📌 About

This repository is a visual, step-by-step guide for both beginners and professionals to understand and apply branching strategies in Git and GitHub. It includes clear definitions, workflow diagrams, and practical examples.

---

## ⚙️ Glossary

| Term                           | Brief Description                                                      |
| ------------------------------ | ---------------------------------------------------------------------- |
| **branch** / **branches**      | An independent line of development.                                    |
| **commit** / **commits**       | A snapshot of changes in the repository.                               |
| **pull request** / **PR**      | A proposal to merge one branch into another, with code review.         |
| **merge** / **merges**         | The action of combining changes from different branches.              |
| **main**                       | The primary, stable branch (production).                               |
| **develop**                    | The integration branch for new features.                               |
| **feature/**                   | Prefix for branches developing new features.                           |
| **bugfix/**                    | Prefix for branches fixing bugs during development.                    |
| **hotfix/**                    | Prefix for branches with critical production fixes.                    |
| **release/**                   | Prefix for branches preparing a new software release.                  |
| **experiment/**                | Prefix for prototype and test branches without guaranteed merge.       |
| **squash**                     | Combines multiple commits into a single commit.                        |
| **rebase**                     | Reapplies commits from one branch onto another, creating a linear history. |

---

## 🚀 Quickstart

1. **Create a Branch**

   ```bash
   git switch -c feature/your-feature-name
   ```
2. **Make Commits**

   ```bash
   git add . && git commit -m "Clear description of your change"
   ```
3. **Push to GitHub**

   ```bash
   git push -u origin feature/your-feature-name
   ```
4. **Open a Pull Request**

   * On GitHub, select your branch and click **New Pull Request**.

5. **Review & Merge**

   * After approval, merge and delete your branch:

     ```bash
     git switch main && git pull
     git branch -d feature/nome-da-feature
     git push origin --delete feature/nome-da-feature
     ```

---

## 🌳 Branch Concepts

Each branch serves as an isolated workspace for your changes. Imagine your project history as the tree trunk (main), and each branch as a limb where you can work without impacting the trunk.

---

## 🗂️ Branch Types

| Prefixo         | Exemplo               | Propósito                           |
| --------------- | --------------------- | ----------------------------------- |
| **main**        | `main`                | Production-ready code                  |
| **develop**     | `develop`             | Integration of new features |
| **feature/**    | `feature/login`       | Development of a new feature |
| **bugfix/**     | `bugfix/erro-404`     | Bug fixes                    |
| **hotfix/**     | `hotfix/patch-1.0.1`  | Critical production fixes      |
| **release/**    | `release/2.0.0`       | Release preparation                |
| **experiment/** | `experiment/a-b-test` | Experimental prototypes and tests                 |

---

## ⚙️ Workflow

### GitHub Flow

1. Always work from `main`.
2. Create a feature branch.
3. Commit changes frequently.
4. Push and open a PR.
5. After approval, merge into `main` and deploy.

```bash
gitGraph
git checkout main
commit id:"v1.0.0 deploy"
branch feature/a
checkout feature/a
commit id:"Implementa A"
checkout main
merge feature/a
```

### Git Flow

1. **main**: production
2. **develop**: continuous integration
3. **feature/***: branches created from `develop`
4. **release/***: branches for release preparation
5. **hotfix/***: branches for urgent fixes

```bash
gitGraph
git checkout -b develop main
commit id:"Sprint Start"
branch feature/b
checkout feature/b
commit id:"Add Feature B"
checkout develop
merge feature/b
branch release/1.0.0
checkout release/1.0.0
commit id:"Finalize & Docs"
checkout main
merge release/1.0.0
 tag v1.0.0
checkout develop
merge release/1.0.0
```

---

## 🔧 Essential Operations

### Create a Branch

```bash
git switch -c prefix/branch-name
```

### Update a Branch

```bash
git fetch origin
# Rebase to sync with base
git rebase origin/main
```

### Publish Branch

```bash
git push -u origin prefix/branch-name
```

### Pull Request & Merge

> [!NOTE]\
> **Merge Options**
> * **Merge Commit**: preserves full commit history. Ideal for long-lived features.
> * **Squash and Merge**: consolidates all commits into one. Use for a cleaner history.
> * **Rebase and Merge**: creates a linear history. Best for atomic, well-defined commits.

---

## ⏰ When to Use Each Branch

* **feature/**: for new features.
* **bugfix/**: for fixes before release.
* **hotfix/**: for critical production patches.
* **release/**: for preparing a release.
* **experiment/**: for prototypes and tests.

---

## 👍 Best Practices 

* Use **clear** and **consistent** names.
* Make **small** and **descriptive** commits.
* Open **detailed PRs** with context.
* **Protect** key branches by requiring reviews.
* **Delete merged branches** to keep the repository tidy.

---

## 🚀 Next Steps

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/Branches-Complete-Guide4-Repositories.git
   ```


2. Follow the **Quickstart**.
3. Try out the **Workflows**.
4. Contribute improvements via **PR** or **Issue**.


---

<p align="center">
  
  Made with ❤️ & Markdown by [dev-ggomes](https://github.com/dev-ggomes) with contributions from [LeoSilva91](https://github.com/LeoSilva91)
  
</p>
