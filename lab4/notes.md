# Lab 4 — Git & GitHub

**Name:** Manvendra Bhati  
**Roll number:** U20260140

The GitHub repository already had three commits and uploaded notebooks. Sections 2–6 were reproduced in a separate local practice copy so the original history and coursework could be preserved; observations from that copy are identified below.

## Question 1 — What does `--global` mean?

`--global` saves the Git setting for my user account, so it applies to repositories unless a repository overrides it. Without `--global`, setting `user.name` or `user.email` normally affects only the current repository, and running that command outside a repository fails.

## Question 2 — What did `ls -a` reveal?

After `git init`, `ls -a` showed the hidden `.git` directory, which ordinary `ls` did not show. It contains Git's repository data, including `HEAD`, configuration, objects, references, and hooks; Git commands manage this data.

## Question 3 — What was Git offering to track?

Before adding `.gitignore` in the practice copy, Git listed five untracked files: `README.md`, `lab3.ipynb`, `lab5 .ipynb`, `LAB7.IPYNB`, and `lab8.ipynb`. These were the existing coursework files, and there was no `.venv/` or third-party package folder in this copy.

## Question 4 — What changed after `.gitignore`?

No existing entries disappeared in this practice copy because it contained no virtual environment, Python bytecode, or `.DS_Store` file. Instead, `.gitignore` appeared as a sixth untracked file; its rules will keep `.venv/`, `__pycache__/`, `*.pyc`, and `.DS_Store` out of future untracked-file listings.

## Question 5 — Should `.gitignore` be committed?

Yes, `.gitignore` should be committed because its rules are part of the project's setup. Tracking it gives everyone who clones the repository the same exclusions and helps prevent generated files from being added accidentally.

## Question 6 — What happened after staging `README.md`?

`README.md` moved from `Untracked files` to `Changes to be committed`, where it was shown as a new file. In the working-directory → staging-area → repository model, `git add` copied its current contents into the staging area, but a commit had not yet saved them in history.

## Question 7 — What did the first commit print?

In the practice copy, Git printed `[main (root-commit) 70d2ab5] Lab work so far`, followed by `6 files changed, 3925 insertions(+)` and a creation line for each file. This saved the staged snapshot as the practice repository's first commit, and `git status` then reported a clean working tree.

## Question 8 — What are the first seven characters?

They are an abbreviated commit hash, also called a short commit ID, used to identify a commit when viewing, comparing, or restoring history. The practice copy's first ID was `70d2ab5`; the original GitHub history was preserved and starts with `ba8cbad`.
