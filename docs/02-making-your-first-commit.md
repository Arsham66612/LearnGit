# Make Your First Commit

Now that Git is tracking our project, it's time to learn how to **save our progress**.

Think of a commit as a **checkpoint in a game**. You've worked on your project, created new files, modified existing ones, or deleted some. At the end of the day, you want to save that point in history so you can always come back to it later.

Let's see how this workflow works.

---

## Step 1: Check Your Current Status

The first command you should get used to is:

```bash
git status
```

This command gives you a summary of everything you've changed in your working directory.

For example, while writing this documentation, my output looked like this:

```text
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .commit_and_pray.txt.swp
        commit_and_pray.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

### What does all of this mean?

For now, ignore the first two lines about branches. We'll learn about branches later.

Let's focus on the important parts.

### **Changes not staged for commit**

```text
modified: README.md
```

This means Git knows about `README.md`, but you've changed it since your last commit.

Git is basically saying:

> "I noticed you changed this file, but you haven't told me to include it in your next commit yet."

---

### **Untracked files**

```text
commit_and_pray.txt
```

This means you've created a brand-new file.

Git doesn't know anything about this file yet because you've never asked Git to track it.

---

**Tip**

Read Git's output carefully.

Most of the time, Git tells you exactly what command you should run next.

---

# Step 2: Stage Your Changes

Before making a commit, you need to **stage** the files you want to include.

The command is:

```bash
git add <filename>
```

For example:

```bash
git add README.md
```

---

## What is the Staging Area?

Imagine Git has three different places.

```text
+----------------------+     +----------------------+     +----------------------+
|   Working Directory  | --> |    Staging Area      | --> |   Git Repository     |
+----------------------+     +----------------------+     +----------------------+

README.md
initialize.md
commit_and_pray.md
```

### Working Directory

This is where you write code and edit files.

### Staging Area

Think of this as a **waiting room**.

Only the files you place here will be included in the next commit.

### Git Repository

This is where Git permanently stores your commits.

---

After running:

```bash
git add README.md
```

our visualization becomes:

```text
+----------------------+     +----------------------+     +----------------------+
|   Working Directory  | --> |    Staging Area      | --> |   Git Repository     |
+----------------------+     +----------------------+     +----------------------+

initialize.md               README.md
commit_and_pray.md
```

Now let's check the status again.

```bash
git status
```

Output:

```text
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)

        modified: README.md
```

Perfect!

Git is telling us that `README.md` is now staged and ready to be committed.

---

# Step 3: Create a Commit

Once you've staged your files, it's time to save your progress.

```bash
git commit -m "Your commit message"
```

Example:

```bash
git commit -m "Add project introduction"
```

Every commit **must** have a message.

A good commit message should clearly describe what changed.

---

## Write Small, Meaningful Commits

Imagine you did two different tasks today:

- Added a new checkout feature.
- Fixed a bug in the shopping cart.

Instead of making one huge commit like this:

```text
Updated project
```

make two separate commits:

```text
Add checkout feature
```

and

```text
Fix cart total calculation
```

This makes your project's history much easier to understand.

---

# Good Practices

- Write clear and meaningful commit messages.

- Stage and commit files that are related to the same task.

For example:

```text
Checkout Logic
├── CheckoutController.php
├── CheckoutService.php
└── checkout.blade.php
```

↓

```bash
git add .
git commit -m "Add checkout logic"
```

Then work on another feature separately.

Keeping your commits organized makes life much easier for both you and your teammates.

---

# View Your Commit History

To see every commit you've made, run:

```bash
git log
```

Example output:

```text
commit **********

Author: Arsham <mohkamiarsham234@gmail.com>
Date: Sat Jul 11 14:17:06 2026 +0330

    Fix typos

commit **********

Author: Arsham <mohkamiarsham234@gmail.com>
Date: Sat Jul 11 14:11:54 2026 +0330

    Add Git initialization guide

commit **********

Author: Arsham <mohkamiarsham234@gmail.com>
Date: Sat Jul 11 14:08:40 2026 +0330

    Initial commit
```

As you can see, every commit appears here along with its author, date, and commit message.

Your commit history tells the story of your project.
