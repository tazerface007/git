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
