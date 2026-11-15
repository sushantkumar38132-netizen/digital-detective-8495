# Mission 6 — Git and GitHub

## 1. Task
The objective of this mission is to master version control and team collaboration workflows:
- Understand the core Git workflow: checking status, staging modifications, committing snapshots, and viewing commit logs.
- Differentiate clearly between the staging area (`git add`) and the repository commit history (`git commit`).
- Create and publish an isolated feature branch (`update-about`) to update documentation.
- Open, document, and review a Pull Request (PR) on GitHub, and merge changes back into the `main` branch.
- Compile a comprehensive Git command glossary for everyday development operations.

---

## 2. Work completed
- **Task 6.1:** Analyzed and documented the four primary Git workflow operations and clarified the distinction between staging and committing.
- **Task 6.2:** Created the branch `update-about`, added the "My Learning" section to the root `README.md`, committed the update, and published the branch to GitHub.
- **Task 6.3:** Created a Pull Request comparing `update-about` against `main` on GitHub, verified the diff, completed the merge, and synced local `main`.
- **Task 6.4:** Assembled a 9-command Git glossary explaining daily version-control operations.

---

## 3. Commands / tools used

| Command / Tool | Purpose |
| :--- | :--- |
| `git status` | Displays the state of the working directory and staging area. |
| `git add <file>` | Moves file changes from the working tree to the staging area (index). |
| `git commit -m "..."` | Records a permanent snapshot of staged changes with a descriptive message. |
| `git log --oneline` | Displays a compact chronological history of previous commits. |
| `git checkout -b <branch>` | Creates and immediately switches to a new local branch. |
| `git push -u origin <branch>` | Uploads a local branch and its commits to the remote GitHub repository. |
| `git checkout main` / `git switch main` | Switches the active working branch back to `main`. |
| `git pull origin main` | Fetches and merges the latest updates from the remote GitHub branch. |
| **GitHub Web UI** | Used to inspect branch comparisons, open Pull Requests, and review code diffs. |

---

## 4. My understanding

### Task 6.1 — Understand the basic Git workflow

| Git operation | What it does in your own words |
| :--- | :--- |
| **Check repository status (`git status`)** | Checks which files have been modified, which are staged for the next commit, and which remain untracked by Git. |
| **Stage selected changes (`git add`)** | Moves specific file modifications into a staging area (index), preparing them to be bundled into the next commit. |
| **Create a commit (`git commit -m`)** | Takes a permanent, cryptographic snapshot of all staged changes with an author timestamp and descriptive log message. |
| **View commit history (`git log`)** | Displays the linear audit trail of past commits, showing commit hashes, authors, dates, and messages. |

#### Difference between Staging and Committing:
- **Staging (`git add`):** Staging acts as an intermediate draft area. It gives developers fine-grained control to selectively choose which file modifications or lines of code should be grouped together into a logical unit of work.
- **Committing (`git commit`):** Committing permanently records that staged snapshot into the Git repository's permanent history. Once committed, the change receives a unique SHA-1 hash and can always be reviewed, referenced, or restored.

---

### Task 6.2 & 6.3 — Branches and Pull Requests

#### Definitions and Purpose
- **What is a branch?** A branch is an independent, lightweight movable pointer along the line of commits. It allows a developer to diverge from the main codebase (`main`) to build features, fix bugs, or experiment in isolation without breaking the working production code.
- **What is a Pull Request (PR)?** A Pull Request is a collaborative GitHub feature where a developer proposes merging their feature branch into another branch (such as `main`). It provides a dedicated space for peer code review, discussion, automated testing, and diff inspection before changes are accepted.
- **Why they are essential for collaboration:** Without branches and PRs, multiple developers working on the same repository would constantly overwrite each other's code, commit broken work into production, and struggle with merge conflicts. Branches allow parallel, conflict-free development.

#### GitHub PR Record:
- **Feature Branch Created:** `update-about`
- **Target Branch:** `main`
- **Changes Proposed:** Added the "My Learning" overview to the root `README.md`.
- **Pull Request Status:** Completed and Merged into `main` on GitHub (local `main` updated via `git pull origin main`).

---

### Task 6.4 — Git Command Glossary

| Git Operation | One-Line Explanation |
| :--- | :--- |
| **Initialise a repository** | `git init` creates a new, blank Git repository and tracks changes inside a hidden `.git` folder. |
| **Check status** | `git status` displays untracked files, modified files, and files currently staged for commit. |
| **Stage changes** | `git add <file>` adds specific modifications from the working directory to the staging index. |
| **Commit changes** | `git commit -m "<msg>"` saves the staged snapshot permanently into the repository history. |
| **View history** | `git log --oneline` shows a concise list of past commits, hashes, and messages. |
| **Create or list branches** | `git branch` lists existing branches; `git branch <name>` creates a new branch pointer. |
| **Switch branches** | `git checkout <branch>` (or `git switch <branch>`) switches the working files to the target branch. |
| **Publish changes** | `git push origin <branch>` uploads local branch commits to the remote GitHub repository. |
| **Retrieve remote changes** | `git pull origin <branch>` downloads and integrates changes from the remote server into the current local branch. |

---

## 5. Difficulties faced
- Understanding the difference between local branches on the computer and remote branches on GitHub.
- Ensuring that after merging the Pull Request on GitHub, the local `main` branch was synchronized properly.

---

## 6. How I resolved them
- Used `git push -u origin update-about` to establish upstream tracking so GitHub recognized the branch.
- Switched back to `main` locally using `git checkout main` and pulled the merged changes down using `git pull origin main`.

---

## 7. Evidence / files
- Root `README.md`: Updated with the "My Learning" section via branch `update-about`.
- GitHub Pull Request: Branch `update-about` created, compared, and merged into `main`.

---

## 8. Commit details
- **Commit Message:** `Complete Git and GitHub collaboration mission`
- git commit -m "Complete Git and GitHub collaboration mission"

## 9. Terminal commands to create branch and publish.

git checkout -b update-about

git add README.md
git commit -m "Add My Learning section to root README"

git push -u origin update-about