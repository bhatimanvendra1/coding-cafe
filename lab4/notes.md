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

## Question 9 — What are the four steps of the loop?

The four steps are edit or create files, inspect the changes with `git status`, stage the intended files with `git add`, and save them with `git commit`. Repeating this with `lab4/notes.md` produced the practice copy's second commit, `2162948`, and `git log --oneline` showed both commits.

## Question 10 — Why is `README.md` special?

`README.md` is the conventional starting point for understanding a repository, and GitHub automatically renders a root README on the repository's front page. Keeping the name, roll number, purpose, and contents there helps a visitor find their way around without opening individual lab notes.

## Question 11 — How does GitHub authentication avoid password prompts?

`gh auth login` authorizes GitHub CLI and stores an access token, using the system credential store when available; choosing to authenticate Git also lets Git use that authentication for HTTPS operations. This computer was already signed in through its keyring, so the push used the existing authentication instead of asking for a GitHub account password.

## Question 12 — What appears on the GitHub front page?

The front page shows the repository's files and renders `README.md` below them with headings, my name and roll number, and links to the lab files. GitHub gives README files this special treatment so visitors immediately see the project's introduction.

## Question 13 — Did pushing change the local history?

No: the complete list of local commit IDs was identical before and after `git push -u origin main`. Pushing transferred the commits to GitHub and updated the remote branch; `-u` also set `origin/main` as the upstream so later pushes can use just `git push`.

## Question 14 — Private repository versus no GitHub repository?

A private repository still exists on GitHub with its files and commit history, but access is restricted to the owner and people who have been granted access, such as the invited TAs after they accept. If there is no repository on GitHub, there is no GitHub-hosted copy for the TAs to access, even if a local Git repository exists on my computer.
