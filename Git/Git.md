# Git Notes - Personal Cheat Sheet
<img width="827" height="857" alt="Screenshot 2026-06-21 021741" src="https://github.com/user-attachments/assets/de20fa5d-90c9-43f4-9c2f-b92e30c408d4" />
<img width="807" height="621" alt="Screenshot 2026-06-21 021733" src="https://github.com/user-attachments/assets/e554b2eb-9ec0-4f24-aab0-4b45dc3ba910" />
<img width="925" height="1056" alt="Screenshot 2026-06-21 021712" src="https://github.com/user-attachments/assets/d6f6fb44-b6fe-4675-b3e5-7530de00bf69" />
<img width="911" height="701" alt="Screenshot 2026-06-21 021439" src="https://github.com/user-attachments/assets/b21081e2-63a6-4d48-8b59-584a30f9941b" />
<img width="876" height="845" alt="Screenshot 2026-06-21 021429" src="https://github.com/user-attachments/assets/15e993f2-f213-49d3-bc56-2a380baa85fb" />
<img width="686" height="638" alt="Screenshot 2026-06-21 021422" src="https://github.com/user-attachments/assets/29963689-dd35-4b32-adc9-ce9bc9ce9eca" />
<img width="742" height="385" alt="Screenshot 2026-06-21 014809" src="https://github.com/user-attachments/assets/70e2f95f-bbe5-43b9-91e5-ca543ec7ece2" />
<img width="953" height="522" alt="Screenshot 2026-06-21 013027" src="https://github.com/user-attachments/assets/c84334d5-030d-4ccd-91d1-465790beae4b" />
<img width="966" height="791" alt="Screenshot 2026-06-21 012131" src="https://github.com/user-attachments/assets/1b825283-c870-4cc6-a888-94ee2b5c92de" />
<img width="927" height="780" alt="Screenshot 2026-06-21 011916" src="https://github.com/user-attachments/assets/eea31516-64cc-4dbf-97ae-01e8965ad863" />
<img width="1200" height="623" alt="Screenshot 2026-06-21 011853" src="https://github.com/user-attachments/assets/db40e35d-27af-4634-a863-1295ae40b79e" />

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
