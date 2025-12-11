# Git - A shit source code management software

## Part 1 - Git Fundamentals ( Beginner Level )

**Lession 1: What is Git, and Why do we use it?**

### **What is Git?**

Git is a Version Control System(VCS) used to track changes in files, especially code. Think of it as a powerful "save game" system for projects.


### **Why do we need Git?**

Because without git:

- You cannot go back to an older version of code.
- You cannot collaborate safely.
- You canot experiment or fix bugs without risk.
- You cannot maintain multiple versions of a project.


### **Real use case**
Imagine you're building an Android app. You are trying a new UI design - but it break things. Without git you're stuck. With Git:

- You can create a new branch named ui-design
- Experiment freely.
- If bad - discard
- If good - merge

No tension, no fear.

## **Lession 2: Installing and Configuring git**

### ***Installation***

Git can be installed from the website or native package manager:

- Linux (debian): sudo apt install git
- Windows: Git for Windows installer
- macOS: bew isntall git

### ***First time configuration***

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

### **Why needed?**

git logs every changes with an identity -> essential for collaboration and history.

**Pro tip**
You can view all configs:

```bash
git config --list
```

## **Lession 3: Creating and Understanding a Git Repository**

### **What is a repository (repo)**

A repository is a directory tracked by Git.

### **How to create one?**
1. Create a folder manually
2. Run:
```bash
git init
```

### **What git init does**
- creates a .git folder
- Begins tracking changes
- No backup, no history yet -> just preparation.

### **Real use case**

You start building a Node.js backend -> you run git init inside project folder -> version control begins.

**Pro tip**
Use git status every few minutes. It is your best friend. :)


## **Lession 4: Git's 3 Main States**

Understanding this is *CRUCIAL* for becoming pro:

|**Git State**|**Meaning**|**Command to Move**|
|**Working Directory**|Your real files|--|
|**Staging Area**|Marked for commit|git add|
|**Repository**|Permanently saved history|git commit|

***Imagine this is a pipeline***
Write code --> Stage --> Commit

### ***Real Example***

You modify main.py

1. Working directory: main.py changed
2. git add main.py -> file staged
3. git commit -m "Add greeting function" -> stored forever

**Pro Tip:**
To stage everything
```bash
git add .
```


## **Lession 5: First Commit**

***Basic commands***

```bash
git add filename
git commit -m "Message"
```

### ***Commit message should:***

- Describe what changed
- Be short but clear
- Be written in the present tense ("Add feature", not "Added feature")


### **Real use case**

```bash
git commit -m "Implement user login API"
```


# **PART 2 - Branching, Merging & Collaboration (Intermediate Level)**

This part is where Git becomes useful in real projects.

## **Lession 6: What are Branches in Git?**

### ***What is a branch?***

A branch is like a separate timeline of your project.

Imagine your project is like a tree:

- **main** branch = trunk
- new branches = side branches where you experiment or add features


### ***Why do we need brenches?***

- To develop new features without touching main code.
- To fix bugs safely.
- To try experiments.
- To work in teams without conflicts.
- To maintain multiple versions of a project (e.g v1, v2, beta)


### **Real use case**

You need to add a "Dark Mode" feature.

Instead of doing it directly on the main branch:

```bash
git checkout -b dark-mode
```

You work freely. if it fails, simply delete the branch. If it succeeds, merge it.


## **Lesson 7: Creating and Switching Branches**

### **Create a branch**

```bash
git branch feature1
```

### **Switch to a branch**

```bash
git checkout feature1
```

### **Create and switch in one step (commonly used)**

```bash
git checkout -b feature1
```

### **Check current branch**

```bash
git branch
```

The active branch will be hightlighted with *.


## **Lesson 8: Merging Branches**

### **What is merging?**

Merging combines one branch's changes into another.

Example: merge feature1 into main.

```bash
git checkout main
git merge feature1
```

### **Why Merging is needed?**

- To bring new features into main project.
- To integrate bug fixes
- To sync team contributions.


## **Lesson 9: Merge Conflicts**

### **What is a merge conflict?**

When Git cannot automatically combines changes because:

- Two developers edited the same line
- A file is deleted in one branch but modified in another.

In these cases, Git will ask you to decide.

### **How to resolve?**

1. Open the file
2. Look for Git conflict markers:

```markdown
<<<<<<< HEAD
Your changes
=======
Branch changes
>>>>>>> feature1
```
3. Edit manually to decide the final version
4. Save the file.
5. Run:
```bash
git add .
git commit
```

### **Real scenario**

Two developers edited the same function. Git cannot decide whose update is correct --- that's why merge conflicts exists.


## **Lesson 10: Deleting Branches**

## **Local delete**
```bash
git branch -d feature1
```

## **Force delete (dangerous)**
```bash
git branch -D feature1
```

Use -D only when you know the branch is no longer needed.


## **Lesson 11: What is .gitignore?**

.gitignore tells Git which files NOT to track.

***Examples***
- Node modules (node_modules/)
- Build files
- Secrets
- Logs (\*.log)
- IDE files (.vscode/, .idea/)

***Create one:***
```bash
touch .gitignore
```

***Example content***
```bash
node_modules/
.env
*.log
dist/
```

**Real Scenario**:
You don't want to push your secret API keys -> .env file added to .gitignore.


# **PART 3 - Remote Repos, GitHub, Collaboration & Professional Workflows**

## **Lesson 12: What is a Remote Repository?**

***Definition***
A *remote repository* is a Git repo stored on a server (e.g., GitHub, GitLab, Bitbucket).

### **Why do we need remote repos?**

- Backup
- Collaboration
- CI/CD Pipelines
- Code reviews
- Deployement
- Open-source contribution

### **Real Example**

GitHub hosts your project -> teamates clone -> contribute -> workflow becomes organized and professional.


## **Lesson 13: Connecting Local Git to GitHub**

1. **Step 1: Create a new repo on GitHub**
Just click ***New Repository***.

2. **Step 2: In your project folder, run:**
```bash 
git remote add origin <repository-url>
```

3. **Step 3: Push code for the first time**
```bash 
git push -u origin main
```

### **Why -u?**

It sets upstream tracking so future pushes only require:
```bash
git push
```


## **Lesson 14: Cloning Repositories**

If you want to download someone else's repo:

```bash
git clone <url>
```

### **Real use case:**

You clone an Android project template, then start customizing.


## **Lesson 15: Pulling & Fetching**

### **git pull**

Downloads changes and merges them into your branch.

```bash
git pull
```

### **git fetch**

Downloads changes but does not merge.

```bash
git fetch
```

### **When to use pull vs fetch?**

- **use git pull** when you want update immediately.
- **use git fetch** when you want to review before merging.

### **Real Example**
You fetch updates first to ensure a teammate's commit dosen't break your local code.


## **Lesson 16: Push (sending changes)**

```bash
git push
```

If pushing a new branch:

```bash
git push -u origin feature1
```

## **Lesson 17: Forking (For open-source)**

### **What is a fork?**

A copy of someone's repo into your account.

### **Why needed?**

You can contribute without affecting the original project.


## **Lesson 18: Pull Requests (PRs)

### What is a PR?

A request to merge your branch into another branch (often  into main).

### **Why used?**

- Code review
- Discussion
- Automated test (CI)
- Collaboration process

### **Typical PR flow**

1. Create branch feature-login.
2. Commit your changes
3. Push branch
4. Open PR on GitHub
5. Team reviews
6. Merge when approved


## **Lesson 19: Git Stash (life saver)

### **What is stash?**

Temprarily saves your uncommited changes.

### **When to use?**

- You need to switch branches but have uncommited files
- You don't want to commit half-finished work

### **Commands:**
```bash
git stash
git stash list
git stash apply
git stash drop
```

### **Real scenario:**
You're working on a bug fix and you got a urgent call to switch to main. then main --> stash --> switch --> come back --> apply stash


## **Lesson 20: Pulling with PR(Protected Branches)

In professional companies:
- main branch is protected.
- Direct push is blocked.
- Only PR merging is allowed.

This ensures code quality, testing and reviews.



# **PART 4 -- Advanced Git (Professional-Level Skills)

These concepts differentiate a beginner developer from a senior engineer.


## **Lesson 21: Understanding Git Rebase (Super Important!)

### **What is rebase?**

Rebase moves your branch's commits on top of another branch's latest commits.

### **Why is rebase needed?**

- To maintain a clean commit history
- To keep your feature branch updated without merge commits
- To avoid messy graphs
- Often required in professional teams

### **Example**
You are on a branch feature1 and want to update it with the latest main.

Instead of:

```bash
git merge main
```

You use: 

```bash
git rebase main
```

This rewrites your commits on top of main --> results in clean linear history.


## **Lesson 22: Merge vs Rebase**

|Feature|Merge|Rebase|
|History|Messy, branching|clean, straight line|
|Use case|Team work|Personal branch cleanup|
|Risk|No rewrite|Rewrites commits(danger!)|
|Remote usage|safe|only safe before pushing|

***Golden Rule***: Never rebase a branch that other's are using.


## **Lesson 23: Squashing Commits**

### **What is squashing?**

Combining multiple commits into one single commit.

*Used when*
- You have too many "WIP", "Fix typo", "Again fix bug" commits.
- You want to clean history before PR merge.


***Command (interactive rebase)***
```bash
git rebase -i HEAD~5
```

Then mark unnecessary commit as:

```bash
pick <hash>
squash<hash>
squash<hash>
```

Result --> single clean commit.

***Real example***

Instead of this:

- Add login page
- Fix bug
- Correct typo
- Improve layout
- Final fix for login

***You squash into:***
***"Implement login feature***

## **Lesson 24: Cherry-Pick**

**What is cherry-pick?**

Copy a specific commit from one branch to another.

***Example:***

You want commit abc123 from featureX but not entire branch.

```bash
git cherry-pick abc123
```

### **Real use case**

A bug fix done on a feature branch needs to be applied to main quickly.

Cherry-pick brings that commit only.


## **Lesson 25: Git Reset vs Revert (Most misunderstood commands)**

**A) git reset(dangerous)**

Changes history --> removes commits.

```bash
git reset --hard HEAD~1
```

- Deletes the last commit
- Deletes file changes
- Dangerous if already pushed

**Use case:**
Fix local mistakes before commit is pushed.

**B) git revert (safe)**
Creates a NEW commit that undoes a previous commit

```bash
git revert <commit-hash>
```

**Use case:**
Undo commit on production or shared branches safely.

## **Lesson 26: Git Worktrees (Super Powerful)**

### **What are worktrees?**

Multiple working directories connected to the same Git repo.

**Why needed?**
- Work on 2 branches at the same time.
- No need to stash or commit to switch.
- Save massive time

### ***Example**

```bash
git worktree add ../bugfix-branch bugfix
```

You now have two folders:

- Project/ (main)
- Project-bugfix/ (bugfix branch)

Work peacefully on both.


## **Lesson 27: Git Bisect (Debugging tool)**

### **What is bisect?**

Binary search for the commit that introduced a bug.

### ***Workflow:***

```bash
git bisect start
git bisect bad
git bisect good <old_hash>
```
Git automatically checks commits -> leads you to the faulty one.

***Real use case:***
Your Android build suddenly stop working.
Bisect finds exact commit that broke it.

## **Lesson 28: Branching Strategies (Used in Companies)**

1. **Git Flow**

Total: main, develop, feature branches, release branches.

Used in large enterprise systems.

2. **GitHub Flow**
- main
- feature branches
- pull requests

used in startups & open source.

3. **Trunk-Based Development**
- One main branch
- Short-lived feature branches

Used at Google, Meta, Netflix.



