
## 1. Describe what git is used for, what basic actions and commands it performs.

Git is a distributed version control system primarily used for tracking changes in source code during software development. It enables version control, allowing developers to recall specific versions of files, and supports collaboration by letting multiple developers work on the same project simultaneously. Git facilitates branching and merging for parallel development, acts as a backup system for reverting to previous states, and supports code review workflows to ensure quality before integrating changes.

### Workflow Example:

Initialize a Repository:

```bash
git init
```

Add and Commit Changes:

```bash
git add .
git commit -m "Initial commit"
```

Create and Switch to a New Branch:

```bash
git checkout -b branch_name
```

Make Changes and Commit:

```bash
git add .
git commit -m "Added new shit"
```

Merge Changes Back to Main Branch:

```bash
git checkout main
git merge feature-branch
```

Push Changes to Remote Repository:

```bash
git push origin main
```

## 2. What is a commit and how does it allow you to track changes in files?

A commit in Git is a snapshot of the changes made to the files in your repository%20at%20a specific point in time. It records the state of your project, including any modifications, additions, or deletions, and stores this information in the repository's history. Each commit is uniquely identified by a hash (a long string of characters) and includes metadata such as the author, timestamp, and a commit message describing the changes.

### Example Workflow:

Make changes to a file:

```bash
echo "New content" >> file.txt
```

Stage the changes:

```bash
git add file.txt
```

Commit the changes with a message:

```bash
git commit -m "Added new content to file.txt"
```

View the commit history:

```bash
git log


commit abc123 (HEAD -> main)
Author: John Doe <john@example.com>
Date:   Mon Oct 30 12:00:00 2023 +0000

    Added new content to file.txt
```

Compare changes:

```bash
git diff HEAD~1 HEAD
```
