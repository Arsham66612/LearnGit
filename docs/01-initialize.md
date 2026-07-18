# Initialize a Git Repository

Before Git can track your project, you need to tell Git that your project is a **Git repository**.

That's exactly what the `git init` command does.

---

## Step 1: Create a Project Folder

Create a directory for your project.

```bash
mkdir my-project
cd my-project
```

---

## Step 2: Check the Repository Status

Run:

```bash
git status
```

Since Git hasn't been initialized yet, you'll see something like this:

```text
fatal: not a git repository (or any of the parent directories): .git
```

### What does this mean?

Git is telling you that it can't track your project because it isn't a Git repository yet.

---

## Step 3: Initialize Git

Run:

```bash
git init
```

Output:

```text
Initialized empty Git repository in /path/to/your/project/.git/
```

### What happened?

Git created a hidden directory called **`.git`**.

This directory contains all the information Git needs to track your project's history. From this point on, Git can monitor changes, create commits, manage branches, and much more.

---

## Step 4: Verify Everything Worked

Run:

```bash
git status
```

You should now see something similar to:

```text
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

> **Note:** Newer versions of Git may display **`main`** instead of **`master`** as the default branch. Both are correct depending on your Git configuration.

You can also verify that Git was initialized by listing hidden files:

```bash
ls -a
```

Example output:

```text
.
..
.git
```

If you can see the **`.git`** directory, congratulations! Your project is now a Git repository, and Git is ready to start tracking your work.

---

## What You Learned

- How to initialize a Git repository
- Why `git init` is required
- How to verify that Git was initialized successfully
- Where Git stores its repository data (`.git` directory)

➡️ Continue to the next chapter: **Making Your First Commit**.
