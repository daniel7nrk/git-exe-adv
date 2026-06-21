# initiation
```bash
touch test{1..4}.md

git add test1.md
git commit -m "chore: Create initial file"

git add test2.md
git commit -m "chore: Create another file"

git add test3.md
git commit -m "chore: Create third and fourth files"
```

## part 1
Q1.
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git add test4.md

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git commit --amend -m "chore: Create third and fourth files"
[main dc35116] chore: Create third and fourth files
 Date: Thu Jun 18 15:30:35 2026 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git log --oneline
dc35116 (HEAD -> main) chore: Create third and fourth files
ff30f81 chore: Create another file
43bd007 chore: Create initial file

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```
q2.
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git rebase -i HEAD~2
[detached HEAD bf7195a] chore: Create second file
 Date: Thu Jun 18 15:30:34 2026 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git log --oneline
502dab6 (HEAD -> main) chore: Create third and fourth files
bf7195a chore: Create second file
43bd007 chore: Create initial file

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```
q3.
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git rebase -i --root
[detached HEAD 62ccdd7] chore: Create initial file and second file
 Date: Thu Jun 18 15:30:34 2026 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git log --oneline
4f5c364 (HEAD -> main) chore: Create third and fourth files
62ccdd7 chore: Create initial file and second file

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```

q4
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git rebase -i --root
Stopped at 62ccdd7...  # chore: Create initial file and second file
You can amend the commit now, with

  git commit --amend 

Once you are satisfied with your changes, run

  git rebase --continue

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main|REBASE 1/2)
$ git add test3.md
git commit -m "chore: Create Third File"
fatal: pathspec 'test3.md' did not match any files
interactive rebase in progress; onto 75f7917
Last command done (1 command done):
   edit 62ccdd7 # chore: Create initial file and second file
Next command to do (1 remaining command):
   pick 4f5c364 # chore: Create third and fourth files
  (use "git rebase --edit-todo" to view and edit)
You are currently editing a commit while rebasing branch 'main' on '75f7917'.
  (use "git commit --amend" to amend the current commit)
  (use "git rebase --continue" once you are satisfied with your changes)

nothing to commit, working tree clean

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main|REBASE 1/2)
$ git add test4.md
git commit -m "chore: Create Fourth File"
fatal: pathspec 'test4.md' did not match any files
interactive rebase in progress; onto 75f7917
Last command done (1 command done):
   edit 62ccdd7 # chore: Create initial file and second file
Next command to do (1 remaining command):
   pick 4f5c364 # chore: Create third and fourth files
  (use "git rebase --edit-todo" to view and edit)
You are currently editing a commit while rebasing branch 'main' on '75f7917'.
  (use "git commit --amend" to amend the current commit)
  (use "git rebase --continue" once you are satisfied with your changes)

nothing to commit, working tree clean

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main|REBASE 1/2)
$ git rebase --continue
Successfully rebased and updated refs/heads/main.

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```

q5
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git log --oneline
4d5676d (HEAD -> main) chore: Create Fourth File
ab589cc chore: Create Third File
29e7b0b chore: Create initial file and second file

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git rebase -i HEAD~2
[detached HEAD a646503] chore: Create Third File and fourth files
 Date: Thu Jun 18 16:04:29 2026 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git log --oneline
a646503 (HEAD -> main) chore: Create Third File and fourth files
29e7b0b chore: Create initial file and second file

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```

q6
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ touch unwanted.txt

git add unwanted.txt

git commit -m "Unwanted commit"
[main 0e94c71] Unwanted commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 unwanted.txt

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git log --oneline
0e94c71 (HEAD -> main) Unwanted commit
a646503 chore: Create Third File and fourth files
29e7b0b chore: Create initial file and second file

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/main.

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git log --oneline
a646503 (HEAD -> main) chore: Create Third File and fourth files
29e7b0b chore: Create initial file and second file

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```

q7
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git log --oneline
a646503 (HEAD -> main) chore: Create Third File and fourth files
29e7b0b chore: Create initial file and second file

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ touch reorder.txt

git add reorder.txt

git commit -m "Reorder commit"
[main 9cea5b4] Reorder commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 reorder.txt

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git log --oneline
9cea5b4 (HEAD -> main) Reorder commit
a646503 chore: Create Third File and fourth files
29e7b0b chore: Create initial file and second file

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git rebase -i --root
Successfully rebased and updated refs/heads/main.

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git log --oneline
bd18662 (HEAD -> main) chore: Create Third File and fourth files
af341b9 Reorder commit
29e7b0b chore: Create initial file and second file

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```

q8
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git log --oneline
bd18662 (HEAD -> main) chore: Create Third File and fourth files
af341b9 Reorder commit
29e7b0b chore: Create initial file and second file

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (ft/branch)
$ touch test5.md

git add test5.md

git commit -m "Implemented test 5"
[ft/branch 4633cf0] Implemented test 5
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test5.md

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (ft/branch)
$ git log --oneline
4633cf0 (HEAD -> ft/branch) Implemented test 5
bd18662 (main) chore: Create Third File and fourth files
af341b9 Reorder commit
29e7b0b chore: Create initial file and second file

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (ft/branch)
$ git checkout main
Switched to branch 'main'

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git cherry-pick 4633cf0
[main 98c36da] Implemented test 5
 Date: Thu Jun 18 16:14:13 2026 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test5.md

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git log --oneline
98c36da (HEAD -> main) Implemented test 5
bd18662 chore: Create Third File and fourth files
af341b9 Reorder commit
29e7b0b chore: Create initial file and second file

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```

q9
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git log --graph --oneline --decorate --all
* 98c36da (HEAD -> main) Implemented test 5
| * 4633cf0 (ft/branch) Implemented test 5
|/  
* bd18662 chore: Create Third File and fourth files
* af341b9 Reorder commit
* 29e7b0b chore: Create initial file and second file

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```

q10
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git reflog
98c36da (HEAD -> main) HEAD@{0}: cherry-pick: Implemented test 5
bd18662 HEAD@{1}: checkout: moving from ft/branch to main
4633cf0 (ft/branch) HEAD@{2}: commit: Implemented test 5
bd18662 HEAD@{3}: checkout: moving from main to ft/branch
bd18662 HEAD@{4}: rebase (finish): returning to refs/heads/main
bd18662 HEAD@{5}: rebase (pick): chore: Create Third File and fourth files
af341b9 HEAD@{6}: rebase (pick): Reorder commit
29e7b0b HEAD@{7}: rebase: fast-forward
ef4c818 HEAD@{8}: rebase (start): checkout ef4c81878317ad217e0f283839b46bef40c270d1
9cea5b4 HEAD@{9}: commit: Reorder commit
a646503 HEAD@{10}: rebase (finish): returning to refs/heads/main
a646503 HEAD@{11}: rebase (start): checkout HEAD~2
0e94c71 HEAD@{12}: commit: Unwanted commit
a646503 HEAD@{13}: rebase (finish): returning to refs/heads/main
a646503 HEAD@{14}: rebase (squash): chore: Create Third File and fourth files
ab589cc HEAD@{15}: rebase (start): checkout HEAD~2

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```

## part 2
q1
```bash

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (ft/new-feature)
$ git branch
  ft/branch
* ft/new-feature
  main
```

q2
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (ft/new-feature)
$ touch feature.txt

echo "Core functionality" > feature.txt

git add feature.txt

git commit -m "Implemented core functionality for new feature"
warning: in the working copy of 'feature.txt', LF will be replaced by CRLF the next time Git touches it
[ft/new-feature 0011ed8] Implemented core functionality for new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (ft/new-feature)
$ git log --oneline -1
0011ed8 (HEAD -> ft/new-feature) Implemented core functionality for new feature
```

q3
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (ft/new-feature)
$ git checkout main

touch readme.txt

echo "Project introduction" > readme.txt

git add readme.txt

git commit -m "Updated project readme"
Switched to branch 'main'
warning: in the working copy of 'readme.txt', LF will be replaced by CRLF the next time Git touches it
[main a26e94b] Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```

q4
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git push -u origin main
Enumerating objects: 12, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 8 threads
Compressing objects: 100% (10/10), done.
Writing objects: 100% (12/12), 1.10 KiB | 280.00 KiB/s, done.
Total 12 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (3/3), done.
To https://github.com/daniel7nrk/git-exe-adv.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git push -u origin ft/new-feature
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 326 bytes | 326.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: 
remote: Create a pull request for 'ft/new-feature' on GitHub by visiting:
remote:      https://github.com/daniel7nrk/git-exe-adv/pull/new/ft/new-feature
remote: 
To https://github.com/daniel7nrk/git-exe-adv.git
 * [new branch]      ft/new-feature -> ft/new-feature
branch 'ft/new-feature' set up to track 'origin/ft/new-feature'.

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git branch -a
  ft/branch
  ft/new-feature
* main
  remotes/origin/ft/new-feature
  remotes/origin/main

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git pull origin main
From https://github.com/daniel7nrk/git-exe-adv
 * branch            main       -> FETCH_HEAD
Already up to date.

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git push -u origin main
git push -u origin ft/new-feature
branch 'main' set up to track 'origin/main'.
Everything up-to-date
branch 'ft/new-feature' set up to track 'origin/ft/new-feature'.
Everything up-to-date

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git checkout main
git pull origin main
Already on 'main'
Your branch is up to date with 'origin/main'.
From https://github.com/daniel7nrk/git-exe-adv
 * branch            main       -> FETCH_HEAD
Already up to date.

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```

q5
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main|MERGING)
$ git branch -d ft/new-feature
warning: deleting branch 'ft/new-feature' that has been merged to
         'refs/remotes/origin/ft/new-feature', but not yet merged to HEAD
Deleted branch ft/new-feature (was 0011ed8).

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main|MERGING)
$ git branch
  ft/branch
* main


```

q6
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git log --oneline
59c6983 (HEAD -> main) Merge branch 'ft/new-feature'
a26e94b (origin/main, origin/HEAD) Updated project readme
0011ed8 (origin/ft/new-feature) Implemented core functionality for new feature
98c36da Implemented test 5
bd18662 chore: Create Third File and fourth files
af341b9 Reorder commit
29e7b0b chore: Create initial file and second file

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git checkout -b ft/new-branch-from-commit bd18662
Switched to a new branch 'ft/new-branch-from-commit'

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (ft/new-branch-from-commit)
$ git branch
  ft/branch
* ft/new-branch-from-commit
  main

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (ft/new-branch-from-commit)
$ 
```

q7
```bash

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (ft/new-branch-from-commit)
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git merge ft/new-branch-from-commit
Already up to date.

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```

q8
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git checkout ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (ft/new-branch-from-commit)
$ git rebase main
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.

```

q9
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (ft/new-branch-from-commit)
$ git branch -m ft/improved-branch-name

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (ft/improved-branch-name)
$ git branch
  ft/branch
* ft/improved-branch-name
  main
```

q10
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (ft/improved-branch-name)
$ git log --oneline
59c6983 (HEAD -> ft/improved-branch-name, main) Merge branch 'ft/new-feature'
a26e94b (origin/main, origin/HEAD) Updated project readme
0011ed8 (origin/ft/new-feature) Implemented core functionality for new feature
98c36da Implemented test 5
bd18662 chore: Create Third File and fourth files
af341b9 Reorder commit
29e7b0b chore: Create initial file and second file

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (ft/improved-branch-name)
$ git checkout bd18662
Note: switching to 'bd18662'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at bd18662 chore: Create Third File and fourth files

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv ((bd18662...))
$ git status
HEAD detached at bd18662
nothing to commit, working tree clean

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv ((bd18662...))
$ git checkout main
Previous HEAD position was bd18662 chore: Create Third File and fourth files
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git commit
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git log --graph --oneline --decorate --all
*   59c6983 (HEAD -> main, ft/improved-branch-name) Merge branch 'ft/new-feature'
|\  
| * 0011ed8 (origin/ft/new-feature) Implemented core functionality for new feature
* | a26e94b (origin/main, origin/HEAD) Updated project readme
|/  
* 98c36da Implemented test 5
| * 4633cf0 (ft/branch) Implemented test 5
|/  
* bd18662 chore: Create Third File and fourth files
* af341b9 Reorder commit
* 29e7b0b chore: Create initial file and second file

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```

## part 3
q1
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ echo "temporary work" >> readme.txt

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git stash
warning: in the working copy of 'readme.txt', LF will be replaced by CRLF the next time Git touches it
Saved working directory and index state WIP on main: 59c6983 Merge branch 'ft/new-feature'

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git stash list
stash@{0}: WIP on main: 59c6983 Merge branch 'ft/new-feature'

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```
 
q2
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git stash pop
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (b77686c0af44c2fc8d8f1374976af84dff7fa5ae)

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git add readme.txt
git commit -m "Added temporary work after stash"
[main e33e311] Added temporary work after stash
 1 file changed, 1 insertion(+)

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```
q3
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (ft/conflict-demo)
$ echo "Version from feature branch" > readme.txt

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (ft/conflict-demo)
$ git add readme.txt
git commit -m "Feature branch change"
warning: in the working copy of 'readme.txt', LF will be replaced by CRLF the next time Git touches it
[ft/conflict-demo 7d792a1] Feature branch change
 1 file changed, 1 insertion(+), 2 deletions(-)

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (ft/conflict-demo)
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git add readme.txt
git commit -m "Main branch change"
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git add readme.txt

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git commit -m "Main branch change"
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ ^C

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ echo "Version from main branch" > readme.txt

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git add readme.txt
git commit -m "Main branch change"
warning: in the working copy of 'readme.txt', LF will be replaced by CRLF the next time Git touches it
[main b797526] Main branch change
 1 file changed, 1 insertion(+), 2 deletions(-)

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git merge ft/conflict-demo
Auto-merging readme.txt
CONFLICT (content): Merge conflict in readme.txt
Automatic merge failed; fix conflicts and then commit the result.

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main|MERGING)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main|MERGING)
$ 
```
 
q4
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main|MERGING)
$ git add readme.txt
git commit -m "Resolved merge conflict"
[main 2ac38f6] Resolved merge conflict

```
 
q5
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git mergetool

This message is displayed because 'merge.tool' is not configured.
See 'git mergetool --tool-help' or 'git help config' for more details.
'git mergetool' will now attempt to use one of the following tools:
opendiff kdiff3 tkdiff xxdiff meld tortoisemerge gvimdiff diffuse diffmerge ecmerge p4merge araxis bc codecompare smerge emerge vimdiff nvimdiff
No files need merging
```

q6
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git checkout bd18662
git checkout main
Note: switching to 'bd18662'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at bd18662 chore: Create Third File and fourth files
Previous HEAD position was bd18662 chore: Create Third File and fourth files
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 6 commits.
  (use "git push" to publish your local commits)

```

q7
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ touch .gitignore

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ echo "/tmp" >> .gitignore

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git add .gitignore
git commit -m "Added gitignore"
warning: in the working copy of '.gitignore', LF will be replaced by CRLF the next time Git touches it
[main 1b811b9] Added gitignore
 1 file changed, 1 insertion(+)
 create mode 100644 .gitignore

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ cat .gitignore
/tmp

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```

q8
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git tag v1.0

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git tag
v1.0

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```

q9
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git tag
v1.0

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git tag -d v1.0
Deleted tag 'v1.0' (was 1b811b9)

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git tag

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```

q10
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git push origin main
Enumerating objects: 20, done.
Counting objects: 100% (20/20), done.
Delta compression using up to 8 threads
Compressing objects: 100% (13/13), done.
Writing objects: 100% (17/17), 1.48 KiB | 79.00 KiB/s, done.
Total 17 (delta 7), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (7/7), completed with 1 local object.
To https://github.com/daniel7nrk/git-exe-adv.git
   a26e94b..1b811b9  main -> main

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git checkout main
git pull origin main
Already on 'main'
Your branch is up to date with 'origin/main'.
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 957 bytes | 47.00 KiB/s, done.
From https://github.com/daniel7nrk/git-exe-adv
 * branch            main       -> FETCH_HEAD
   1b811b9..e694c50  main       -> origin/main
Updating 1b811b9..e694c50
Fast-forward
 readme.txt | 2 ++
 1 file changed, 2 insertions(+)

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```

end 
```bash
IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ git log --graph --oneline --decorate --all
git branch -a
git tag
* e694c50 (HEAD -> main, origin/main, origin/HEAD) Add feature branch version to readme
* 1b811b9 Added gitignore
*   2ac38f6 Resolved merge conflict
|\  
| * 7d792a1 (ft/conflict-demo) Feature branch change
* | b797526 Main branch change
|/  
* e33e311 Added temporary work after stash
*   59c6983 (ft/improved-branch-name) Merge branch 'ft/new-feature'
|\  
| * 0011ed8 (origin/ft/new-feature) Implemented core functionality for new feature
* | a26e94b Updated project readme
|/  
  ft/branch
  ft/conflict-demo
  ft/improved-branch-name
* main
  remotes/origin/HEAD -> origin/main
  remotes/origin/ft/new-feature
  remotes/origin/main

IFAK@Daniel-Ngaruka MINGW64 ~/Desktop/git-exe-adv (main)
$ 
```