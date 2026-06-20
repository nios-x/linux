# Git Notes - Personal Cheat Sheet

## 1. Git Areas

Git has 3 important areas:

```text
Working Directory
      |
      | git add
      v
Staging Area (Index)
      |
      | git commit
      v
Repository (Commits)
```

Check status:

```bash
git status
```

---

# 2. Basic Commit Workflow

Create or modify files:

```bash
echo "Hello" > app.txt
```

Stage changes:

```bash
git add .
```

Commit:

```bash
git commit -m "message"
```

View history:

```bash
git log --oneline
```

---

# 3. Branches

Create branch:

```bash
git branch feature
```

Create and switch:

```bash
git checkout -b feature
```

Switch branch:

```bash
git checkout master
```

View branches:

```bash
git branch
```

Current branch has a *:

```text
* master
  feature
```

---

# 4. Merge

Definition:

Combine changes from one branch into another.

Rule:

Stand on the destination branch.

Example:

```bash
git checkout master
git merge feature
```

Meaning:

"Bring feature into master."

---

## Fast Forward Merge

Before:

```text
A --- B (master)
         \
          C --- D (feature)
```

Master has no extra commits.

Git simply moves master pointer:

```text
A --- B --- C --- D
                  ^
            master, feature
```

No merge commit created.

---

## Real Merge

Before:

```text
          C --- D (feature)
         /
A --- B
         \
          E (master)
```

Both branches have unique commits.

Git creates a merge commit:

```text
          C --- D
         /       \
A --- B --------- M
         \
          E
```

M = Merge Commit

---

## Merge Conflicts

Git may stop:

```text
CONFLICT (content)
```

Resolve file.

Stage:

```bash
git add .
```

Complete merge:

```bash
git commit
```

Or abort:

```bash
git merge --abort
```

---

# 5. Rebase

Definition:

Move a branch on top of another branch.

Rule:

Stand on the branch being rewritten.

Example:

```bash
git checkout feature
git rebase master
```

Meaning:

"Replay feature commits on top of master."

---

Before:

```text
master:
A --- B --- C

feature:
A --- B --- D --- E
```

After:

```text
A --- B --- C --- D' --- E'
```

D' and E' are NEW commits.

Hashes change.

---

## Rebase Conflict

Git stops:

```text
CONFLICT (content)
```

Resolve file.

Stage:

```bash
git add .
```

Continue:

```bash
git rebase --continue
```

Abort:

```bash
git rebase --abort
```

---

## Merge vs Rebase

Merge:

```text
Keeps history.
Creates merge commit.
Hashes stay same.
```

Rebase:

```text
Rewrites history.
Creates new hashes.
Makes history linear.
```

Memory:

```text
merge  = combine branches
rebase = move branch
```

---

# 6. Revert

Definition:

Create a new commit that undoes another commit.

Example:

```bash
git revert <commit_hash>
```

Git creates:

```text
Revert "old commit"
```

Original commit stays.

New commit undoes it.

---

Before:

```text
A --- B
```

After:

```text
A --- B --- C
```

C undoes B.

---

## Revert Without Conflict

```bash
git revert <hash>
```

Editor opens.

Save and exit:

```vim
Esc
:wq
```

Git creates revert commit automatically.

No git add needed.

No git commit needed.

---

## Revert With Conflict

Git stops:

```text
CONFLICT (content)
```

Resolve file.

Stage:

```bash
git add .
```

Continue:

```bash
git revert --continue
```

Abort:

```bash
git revert --abort
```

Skip commit:

```bash
git revert --skip
```

---

## Important

Wrong:

```bash
git add .
git commit -m "fixed"
```

Correct:

```bash
git add .
git revert --continue
```

---

# 7. Reset

Definition:

Move branch pointer to another commit.

---

## Soft Reset

```bash
git reset --soft <hash>
```

Moves HEAD.

Keeps staged changes.

```text
HEAD moves
Files stay
Stage stays
```

---

## Mixed Reset (Default)

```bash
git reset <hash>
```

or

```bash
git reset --mixed <hash>
```

Moves HEAD.

Unstages files.

```text
HEAD moves
Files stay
Stage cleared
```

---

## Hard Reset

```bash
git reset --hard <hash>
```

Moves HEAD.

Resets everything.

```text
HEAD moves
Stage cleared
Files reset
```

Dangerous.

---

Memory:

```text
soft  = staged
mixed = unstaged
hard  = gone
```

---

# 8. Stash

Definition:

Temporarily save work without committing.

Save:

```bash
git stash
```

View:

```bash
git stash list
```

Example:

```text
stash@{0}
stash@{1}
```

---

## Apply Stash

Keep stash:

```bash
git stash apply stash@{0}
```

---

## Pop Stash

Apply and remove:

```bash
git stash pop
```

or

```bash
git stash pop stash@{0}
```

---

## Delete Stash

One stash:

```bash
git stash drop stash@{0}
```

All stashes:

```bash
git stash clear
```

---

# 9. Cherry Pick

Definition:

Copy one specific commit from another branch.

Example:

```bash
git checkout master
git cherry-pick <hash>
```

Meaning:

"Apply only this commit."

---

Before:

```text
feature:
A --- B --- C --- D

master:
A --- B
```

Cherry-pick D:

```text
feature:
A --- B --- C --- D

master:
A --- B --- D'
```

D' = copied commit.

New hash.

---

## Cherry Pick Conflict

Resolve file.

Stage:

```bash
git add .
```

Continue:

```bash
git cherry-pick --continue
```

Abort:

```bash
git cherry-pick --abort
```

---

# 10. Reflog (Git Time Machine)

Shows every HEAD movement.

```bash
git reflog
```

Useful after:

```bash
git reset --hard
```

Recover commit:

```bash
git reset --hard <reflog_hash>
```

---

# 11. Most Important Mental Models

Merge:

```text
Stand on destination branch.

git checkout master
git merge feature
```

Meaning:

Bring feature into master.

---

Rebase:

```text
Stand on branch being rewritten.

git checkout feature
git rebase master
```

Meaning:

Move feature on top of master.

---

Cherry Pick:

```text
Take one commit.
```

---

Revert:

```text
Undo via new commit.
```

---

Reset:

```text
Move branch pointer.
```

---

Stash:

```text
Temporary save without commit.
```

---

Final Memory Trick

merge      = take branch
rebase     = move branch
cherry-pick = take commit
revert     = undo commit
reset      = move pointer
stash      = temporary save

```
```
