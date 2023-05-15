<!-- Project initialization -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git init
Initialized empty Git repository in /home/ivy/Development/ojemba/git/gym-git-exercise-solution/.git/

<!-- Branch main creation and switching -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git branch
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout -b main
Switched to a new branch 'main'

<!-- Staging changes made to readme file and committing them -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "Add first terminal history in readme file"
[main (root-commit) 64c6f41] Add first terminal history in readme file
 1 file changed, 7 insertions(+)
 create mode 100644 README.md

 <!-- Connecting remote repo to local project -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git remote add origin git@github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git

<!-- Pushing local changes into the main branch in remote repo -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push -u origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 414 bytes | 414.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.

<!-- Create a dev branch and switch to it -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout -b dev
Switched to a new branch 'dev'

<!-- Create a test branch and switch to it -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout -b test
Switched to a new branch 'test'

<!-- Switch back to dev branch -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout dev
M       README.md
Switched to branch 'dev'

<!-- Check all the created branches -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git branch -a
* dev
  main
  test
  remotes/origin/main

  <!-- Delete test branch -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git branch --delete test
Deleted branch test (was 64c6f41).

<!-- List the remaining branches -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git branch -a
* dev
  main
  remotes/origin/main

<!-- Create home page stage changes and stash the changes -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ touch home.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash save "temporily save changes in home page file"
Saved working directory and index state On dev: temporily save changes in home page file

<!-- Create about page stage changes and stash the changes -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ touch about.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash save "Temporily save changes in the about page file"
Saved working directory and index state On dev: Temporily save changes in the about page file

<!-- Create team page stage changes and stash the changes -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ touch team.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash save "temporily save changes in team page file"
Saved working directory and index state On dev: temporily save changes in team page file

<!-- List all the stashed files -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash list
stash@{0}: On dev: temporily save changes in team page file
stash@{1}: On dev: Temporily save changes in the about page file
stash@{2}: On dev: temporily save changes in home page file

<!-- stash pop to restore changes in about page -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash pop stash@{1}
On branch dev
Your branch is up to date with 'origin/dev'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Dropped stash@{1} (7da920374bb642cdd4f35de4f18b3392204003fc)

<!-- List the remaining stashes -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash list
stash@{0}: On dev: temporily save changes in team page file
stash@{1}: On dev: temporily save changes in home page file

<!-- used stash apply but encountered a conflicting due to merge conflict in readme a-->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash apply stash@{1}
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch dev
Your branch is ahead of 'origin/dev' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   home.html

Unmerged paths:
  (use "git restore --staged <file>..." to unstage)
  (use "git add <file>..." to mark resolution)
        both modified:   README.md
<!-- Staged changes in home page file commited and pushed them  -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "make changes to readme file"
[dev 3c36d78] make changes to readme file
 2 files changed, 13 insertions(+), 1 deletion(-)
 create mode 100644 home.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch dev
Your branch is ahead of 'origin/dev' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push
Enumerating objects: 10, done.
Counting objects: 100% (10/10), done.
Delta compression using up to 8 threads
Compressing objects: 100% (8/8), done.
Writing objects: 100% (8/8), 1.34 KiB | 457.00 KiB/s, done.
Total 8 (delta 3), reused 0 (delta 0)
remote: Resolving deltas: 100% (3/3), completed with 1 local object.
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
   c49ac11..3c36d78  dev -> dev

<!-- Created an new file and used git stash pop --index to bring unstash worked successfully -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash list
stash@{0}: On dev: save new home page
stash@{1}: On dev: temporily save changes in team page file
stash@{2}: On dev: temporily save changes in home page file
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash pop --index stash@{0}
Removing home.thml
On branch dev
Your branch is up to date with 'origin/dev'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   home.html
        deleted:    home.thml

Dropped stash@{0} (0209a14f16c243293329822b4ba7b50957f42c2b)

<!-- Staged changes committed and pushed them -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "rename home page and stash pop"
[dev 1958d9f] rename home page and stash pop
 2 files changed, 12 insertions(+)
 create mode 100644 home.html
 delete mode 100644 home.thml
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 472 bytes | 472.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
   1560aa2..1958d9f  dev -> dev

<!-- Create an ft/bundle-2 branch and create a services page -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout -b ft/bundle-2
Switched to a new branch 'ft/bundle-2'
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ touch services.html

<!-- Stage the changes and commit them -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "Create a service page"
[ft/bundle-2 815d283] Create a service page
 2 files changed, 3 insertions(+), 1 deletion(-)
 create mode 100644 services.html


<!-- Push the chnages to the github repo -->
 ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push -u origin ft/bundle-2
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 463 bytes | 463.00 KiB/s, done.
Total 4 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: 
remote: Create a pull request for 'ft/bundle-2' on GitHub by visiting:
remote:      https://github.com/Murage-Ivy/Gym-Git-Exercise-Solutions/pull/new/ft/bundle-2
remote: 
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/bundle-2 -> ft/bundle-2
Branch 'ft/bundle-2' set up to track remote branch 'ft/bundle-2' from 'origin'.

```
## Checkout your main branch and pull the latest changes
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git fetch
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), 628 bytes | 628.00 KiB/s, done.
From github.com:Murage-Ivy/Gym-Git-Exercise-Solutions
   64c6f41..cd99c3d  main       -> origin/main
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git pull 
Updating 64c6f41..cd99c3d
Fast-forward
 README.md     | 207 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++--
 about.html    |  12 ++++++++
 home.html     |  12 ++++++++
 services.html |   0
 team.html     |  12 ++++++++
 5 files changed, 241 insertions(+), 2 deletions(-)
 create mode 100644 about.html
 create mode 100644 home.html
 create mode 100644 services.html
 create mode 100644 team.html


 ### Question 2 exercise 2
 ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout -b ft/service-redesign
Switched to a new branch 'ft/service-redesign'
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ touch services.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch ft/service-redesign
nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "Create service page"
[ft/service-redesign c95d71c] Create service page
 1 file changed, 14 insertions(+)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push u origin ft/service-redesign
error: src refspec origin does not match any
error: failed to push some refs to 'u'
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push -u origin ft/service-redesign
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 484 bytes | 484.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: 
remote: Create a pull request for 'ft/service-redesign' on GitHub by visiting:
remote:      https://github.com/Murage-Ivy/Gym-Git-Exercise-Solutions/pull/new/ft/service-redesign
remote: 
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/service-redesign -> ft/service-redesign
Branch 'ft/service-redesign' set up to track remote branch 'ft/service-redesign' from 'origin'.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "Add text to service page in main branch"
[main 7b4b436] Add text to service page in main branch
 1 file changed, 13 insertions(+)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 508 bytes | 508.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
   711334c..7b4b436  main -> main
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout ft/service-redesign
Switched to branch 'ft/service-redesign'
Your branch is up to date with 'origin/ft/service-redesign'.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git diff
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git diff
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ ls
about.html  home.html  README.md  services.html  team.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git diff --cached
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git diff --cached
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git diff 
diff --git a/services.html b/services.html
index 752dfbf..e388681 100644
--- a/services.html
+++ b/services.html
@@ -8,7 +8,8 @@
 </head>
 <body>
     <h2>Welcome everybody</h2>
-    <p>This is the service page</p>
+    <p>This is the service pages</p>
+
 
 </body>
 </html>
\ No newline at end of file
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git diff 
diff --git a/services.html b/services.html
index 752dfbf..96a317c 100644
--- a/services.html
+++ b/services.html
@@ -9,6 +9,5 @@
 <body>
     <h2>Welcome everybody</h2>
     <p>This is the service page</p>
-
 </body>
 </html>
\ No newline at end of file
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git diff 
diff --git a/services.html b/services.html
index 752dfbf..8fab5d2 100644
--- a/services.html
+++ b/services.html
@@ -9,6 +9,6 @@
 <body>
     <h2>Welcome everybody</h2>
     <p>This is the service page</p>
-
+    
 </body>
 </html>
\ No newline at end of file
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git diff 
diff --git a/services.html b/services.html
index 752dfbf..96a317c 100644
--- a/services.html
+++ b/services.html
@@ -9,6 +9,5 @@
 <body>
     <h2>Welcome everybody</h2>
     <p>This is the service page</p>
-
 </body>
 </html>
\ No newline at end of file
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch ft/service-redesign
Your branch is up to date with 'origin/ft/service-redesign'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   services.html

no changes added to commit (use "git add" and/or "git commit -a")
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git merge
Already up to date.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch ft/service-redesign
Your branch is up to date with 'origin/ft/service-redesign'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   services.html

no changes added to commit (use "git add" and/or "git commit -a")
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "Mkae changes"
[ft/service-redesign d48ff7e] Mkae changes
 1 file changed, 1 deletion(-)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 307 bytes | 307.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
   c95d71c..d48ff7e  ft/service-redesign -> ft/service-redesign
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git diff
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git diff
diff --git a/services.html b/services.html
index 96a317c..ffd795c 100644
--- a/services.html
+++ b/services.html
@@ -8,6 +8,6 @@
 </head>
 <body>
     <h2>Welcome everybody</h2>
-    <p>This is the service page</p>
+    <p>This is the service page and hapyy you are here</p>
 </body>
 </html>
\ No newline at end of file
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "Redesign service page"
[ft/service-redesign f39ce8c] Redesign service page
 1 file changed, 1 insertion(+), 1 deletion(-)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 325 bytes | 325.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
   d48ff7e..f39ce8c  ft/service-redesign -> ft/service-redesign
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git diff
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git merge ft/service-redesign
Auto-merging services.html
CONFLICT (content): Merge conflict in services.html
Automatic merge failed; fix conflicts and then commit the result.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git


ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout -b ft/team-page
Switched to a new branch 'ft/team-page'
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ touch team.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "Add changes to team file"
[ft/team-page cae4f98] Add changes to team file
 1 file changed, 1 insertion(+)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push -u ft/team-page
fatal: 'ft/team-page' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push -u origin ft/team-page
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 316 bytes | 316.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote: 
remote: Create a pull request for 'ft/team-page' on GitHub by visiting:
remote:      https://github.com/Murage-Ivy/Gym-Git-Exercise-Solutions/pull/new/ft/team-page
remote: 
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/team-page -> ft/team-page
Branch 'ft/team-page' set up to track remote branch 'ft/team-page' from 'origin'.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout -b ft/contact-page
Switched to a new branch 'ft/contact-page'
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git log 
commit cae4f989f8cab05b37c25d918a9e598d9a07303a (HEAD -> ft/team-page, origin/ft/team-page)
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 16:31:57 2023 +0300

    Add changes to team file

commit fad0de977c1397975dc5f13782fd03d93f79a221 (origin/main, main, ft/contact-page)
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 16:24:53 2023 +0300

    Add solution for exercise 2  bundle 2

commit c3052afbd366457a4816988e4c1ca3c368584417
Merge: 7b4b436 f39ce8c
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 13:44:37 2023 +0300

    Merge branch 'ft/service-redesign' into main

commit f39ce8c4f851a37769fffdd7560c38228dfdd7fb (origin/ft/service-redesign, ft/service-redesign)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git cherry-pick
usage: git cherry-pick [<options>] <commit-ish>...
   or: git cherry-pick <subcommand>

    --quit                end revert or cherry-pick sequence
    --continue            resume revert or cherry-pick sequence
    --abort               cancel revert or cherry-pick sequence
    --skip                skip current commit and continue
    --cleanup <mode>      how to strip spaces and #comments from message
    -n, --no-commit       don't automatically commit
    -e, --edit            edit the commit message
    -s, --signoff         add Signed-off-by:
    -m, --mainline <parent-number>
                          select mainline parent
    --rerere-autoupdate   update the index with reused conflict resolution if possible
    --strategy <strategy>
                          merge strategy
    -X, --strategy-option <option>
                          option for merge strategy
    -S, --gpg-sign[=<key-id>]
                          GPG sign commit
    -x                    append commit name
    --ff                  allow fast-forward
    --allow-empty         preserve initially empty commits
    --allow-empty-message
                          allow commits with empty messages
    --keep-redundant-commits
                          keep redundant, empty commits

ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git cherry-pick cae4f
[ft/contact-page 29ad0de] Add changes to team file
 Date: Mon May 15 16:31:57 2023 +0300
 1 file changed, 1 insertion(+)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "Create contact page and add text"
[ft/contact-page 904ed51] Create contact page and add text
 1 file changed, 12 insertions(+)
 create mode 100644 contact.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push ft/contact-page
fatal: 'ft/contact-page' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push -u origin ft/contact-page
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 8 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 798 bytes | 798.00 KiB/s, done.
Total 6 (delta 3), reused 0 (delta 0)
remote: Resolving deltas: 100% (3/3), completed with 2 local objects.
remote: 
remote: Create a pull request for 'ft/contact-page' on GitHub by visiting:
remote:      https://github.com/Murage-Ivy/Gym-Git-Exercise-Solutions/pull/new/ft/contact-page
remote: 
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/contact-page -> ft/contact-page
Branch 'ft/contact-page' set up to track remote branch 'ft/contact-page' from 'origin'.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout -b ft/faq-page
Switched to a new branch 'ft/faq-page'
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git  status
On branch ft/faq-page
nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ touch faq.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "Create faq page and added text"
[ft/faq-page e5d4cac] Create faq page and added text
 1 file changed, 13 insertions(+)
 create mode 100644 faq.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push -u origin ft/faq-page
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 516 bytes | 516.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: 
remote: Create a pull request for 'ft/faq-page' on GitHub by visiting:
remote:      https://github.com/Murage-Ivy/Gym-Git-Exercise-Solutions/pull/new/ft/faq-page
remote: 
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/faq-page -> ft/faq-page
Branch 'ft/faq-page' set up to track remote branch 'ft/faq-page' from 'origin'.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git revert cae4f
[ft/team-page 0772195] Revert "Add changes to team file"
 1 file changed, 1 deletion(-)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git revert cae4f
[ft/faq-page b350cbb] Revert "Add changes to team file"
 1 file changed, 1 deletion(-)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git revert cae4f
On branch ft/team-page
Your branch is ahead of 'origin/ft/team-page' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch ft/team-page
Your branch is ahead of 'origin/ft/team-page' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git revert cae4f
On branch ft/faq-page
Your branch is ahead of 'origin/ft/faq-page' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git revert cae4f
On branch ft/team-page
Your branch is ahead of 'origin/ft/team-page' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch ft/team-page
Your branch is ahead of 'origin/ft/team-page' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch ft/faq-page
Your branch is ahead of 'origin/ft/faq-page' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "Create faq page and added text"
[ft/faq-page 87d0864] Create faq page and added text
 1 file changed, 1 insertion(+)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push -u origin ft/faq-page
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 8 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 659 bytes | 659.00 KiB/s, done.
Total 6 (delta 4), reused 0 (delta 0)
remote: Resolving deltas: 100% (4/4), completed with 3 local objects.
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
   e5d4cac..87d0864  ft/faq-page -> ft/faq-page
Branch 'ft/faq-page' set up to track remote branch 'ft/faq-page' from 'origin'.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git revert cae4f
On branch ft/team-page
Your branch is ahead of 'origin/ft/team-page' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git revert cae4f
On branch ft/team-page
Your branch is ahead of 'origin/ft/team-page' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "Add header"
[ft/team-page 73ee6b0] Add header
 1 file changed, 1 insertion(+)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push -u origin ft/team-page
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 481 bytes | 481.00 KiB/s, done.
Total 4 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
   cae4f98..73ee6b0  ft/team-page -> ft/team-page
Branch 'ft/team-page' set up to track remote branch 'ft/team-page' from 'origin'.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git log
commit 73ee6b06ae20e7dc224d8a2830eff6594953e304 (HEAD -> ft/team-page, origin/ft/team-page)
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 17:19:34 2023 +0300

    Add header

commit 0772195b4218ae16e3d27e0c62b59e3a7b92079e
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 17:13:10 2023 +0300

    Revert "Add changes to team file"
    
    This reverts commit cae4f989f8cab05b37c25d918a9e598d9a07303a.

commit cae4f989f8cab05b37c25d918a9e598d9a07303a
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 16:31:57 2023 +0300

    Add changes to team file

ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git revert 73ee6
[ft/team-page 43ce8ad] Revert "Add header"
 1 file changed, 1 deletion(-)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 315 bytes | 315.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
   73ee6b0..43ce8ad  ft/team-page -> ft/team-page
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch ft/team-page
Your branch is up to date with 'origin/ft/team-page'.

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch ft/team-page
Your branch is up to date with 'origin/ft/team-page'.

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git revert 43ce8ad589c79add7321723bb1f65b7482291f45
[ft/team-page 8626491] Revert "Revert "Add header""
 1 file changed, 1 insertion(+)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git revert 43ce8ad589c79add7321723bb1f65b7482291f45
On branch ft/team-page
Your branch is ahead of 'origin/ft/team-page' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit
On branch ft/team-page
Your branch is ahead of 'origin/ft/team-page' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 340 bytes | 340.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
   43ce8ad..8626491  ft/team-page -> ft/team-page
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git revert 8626491f2f5ed93e29af77fad02c413667196b79
[ft/team-page 6569bdf] Revert "Revert "Revert "Add header"""
 1 file changed, 1 deletion(-)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch ft/team-page
Your branch is ahead of 'origin/ft/team-page' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 320 bytes | 320.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
   8626491..6569bdf  ft/team-page -> ft/team-page
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git remote add origin git@github.com:Murage-Ivy/git-copy.git
fatal: remote origin already exists.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git remote add git@github.com:Murage-Ivy/git-copy.git
usage: git remote add [<options>] <name> <url>

    -f, --fetch           fetch the remote branches
    --tags                import all tags and associated objects when fetching
                          or do not fetch any tag at all (--no-tags)
    -t, --track <branch>  branch(es) to track
    -m, --master <branch>
                          master branch
    --mirror[=(push|fetch)]
                          set up remote as a mirror to push to or fetch from

ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git remote add git-copy git@github.com:Murage-Ivy/git-copy.git
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git remote -v
git-copy        git@github.com:Murage-Ivy/git-copy.git (fetch)
git-copy        git@github.com:Murage-Ivy/git-copy.git (push)
origin  git@github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git (fetch)
origin  git@github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git (push)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "Add a header to the home page file"
[main e0ff839] Add a header to the home page file
 1 file changed, 1 insertion(+)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git log
commit e0ff839e56f52d00ee01e4329596efde2c5bfbed (HEAD -> main)
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 20:17:26 2023 +0300

    Add a header to the home page file

commit fad0de977c1397975dc5f13782fd03d93f79a221 (origin/main)
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 16:24:53 2023 +0300

    Add solution for exercise 2  bundle 2

commit c3052afbd366457a4816988e4c1ca3c368584417
Merge: 7b4b436 f39ce8c
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 13:44:37 2023 +0300

    Merge branch 'ft/service-redesign' into main

commit f39ce8c4f851a37769fffdd7560c38228dfdd7fb (origin/ft/service-redesign, ft/service-redesign)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push -u origin main
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'git@github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git fetch
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 1.83 KiB | 626.00 KiB/s, done.
From github.com:Murage-Ivy/Gym-Git-Exercise-Solutions
   fad0de9..c51e1c4  main       -> origin/main
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git pull
Merge made by the 'recursive' strategy.
 contact.html | 12 ++++++++++++
 faq.html     | 14 ++++++++++++++
 2 files changed, 26 insertions(+)
 create mode 100644 contact.html
 create mode 100644 faq.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git remote -v
git-copy        git@github.com:Murage-Ivy/git-copy.git (fetch)
git-copy        git@github.com:Murage-Ivy/git-copy.git (push)
origin  git@github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git (fetch)
origin  git@github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git (push)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push -u origin  && git-copy main
Enumerating objects: 9, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 8 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 598 bytes | 598.00 KiB/s, done.
Total 5 (delta 3), reused 0 (delta 0)
remote: Resolving deltas: 100% (3/3), completed with 2 local objects.
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
   c51e1c4..97e7b5f  main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
git-copy: command not found
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push git-copy main
Enumerating objects: 81, done.
Counting objects: 100% (81/81), done.
Delta compression using up to 8 threads
Compressing objects: 100% (78/78), done.
Writing objects: 100% (81/81), 12.83 KiB | 730.00 KiB/s, done.
Total 81 (delta 40), reused 0 (delta 0)
remote: Resolving deltas: 100% (40/40), done.
To github.com:Murage-Ivy/git-copy.git
 * [new branch]      main -> main
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout -b ft/footer
Switched to a new branch 'ft/footer'
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "Create footer file"
[ft/footer cb44419] Create footer file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 footer.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "Add html biler plate to footer page"
[ft/footer 1fda872] Add html biler plate to footer page
 1 file changed, 12 insertions(+)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push -u origin ft/footer
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 8 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (6/6), 737 bytes | 368.00 KiB/s, done.
Total 6 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
remote: 
remote: Create a pull request for 'ft/footer' on GitHub by visiting:
remote:      https://github.com/Murage-Ivy/Gym-Git-Exercise-Solutions/pull/new/ft/footer
remote: 
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/footer -> ft/footer
Branch 'ft/footer' set up to track remote branch 'ft/footer' from 'origin'.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git log
commit 1fda8727aad492719f8e0ccfb7d98b1522d85186 (HEAD -> ft/footer, origin/ft/footer)
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 20:43:23 2023 +0300

    Add html biler plate to footer page

commit cb4441958676fe59793db4fa6e24b997490604f1
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 20:42:33 2023 +0300

    Create footer file

commit 97e7b5fed83b96d8be953c26613ac2a0fab478ac (origin/main, git-copy/main, main)
Merge: e0ff839 c51e1c4
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 20:34:33 2023 +0300

    Merge branch 'main' of github.com:Murage-Ivy/Gym-Git-Exercise-Solutions into main

commit e0ff839e56f52d00ee01e4329596efde2c5bfbed
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch ft/footer
Your branch is up to date with 'origin/ft/footer'.

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git staus
git: 'staus' is not a git command. See 'git --help'.

The most similar command is
        status
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch ft/footer
Your branch is up to date with 'origin/ft/footer'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        footer-features/

nothing added to commit but untracked files present (use "git add" to track)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m 'Add contact footer feature"
> '
[ft/footer a5e93e3] Add contact footer feature"
 1 file changed, 12 insertions(+)
 create mode 100644 footer-features/index.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 549 bytes | 549.00 KiB/s, done.
Total 4 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
   1fda872..a5e93e3  ft/footer -> ft/footer
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git log
commit a5e93e319ec814255051c92d5dbb2eb8c97bd8ba (HEAD -> ft/footer, origin/ft/footer)
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 22:17:35 2023 +0300

    Add contact footer feature"

commit 1fda8727aad492719f8e0ccfb7d98b1522d85186
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 20:43:23 2023 +0300

    Add html biler plate to footer page

commit cb4441958676fe59793db4fa6e24b997490604f1
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 20:42:33 2023 +0300

    Create footer file

commit 97e7b5fed83b96d8be953c26613ac2a0fab478ac (origin/main, git-copy/main, main)
Merge: e0ff839 c51e1c4
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ 
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git revert a5e93
Removing footer-features/index.html
[ft/footer 6faf21b] Revert "Add contact footer feature""
 1 file changed, 12 deletions(-)
 delete mode 100644 footer-features/index.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git log
commit 6faf21b30fc58e357a338b6f6e7cd61e61113a79 (HEAD -> ft/footer)
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 22:18:43 2023 +0300

    Revert "Add contact footer feature""
    
    This reverts commit a5e93e319ec814255051c92d5dbb2eb8c97bd8ba.

commit a5e93e319ec814255051c92d5dbb2eb8c97bd8ba (origin/ft/footer)
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 22:17:35 2023 +0300

    Add contact footer feature"

commit 1fda8727aad492719f8e0ccfb7d98b1522d85186
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 20:43:23 2023 +0300

    Add html biler plate to footer page

ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 268 bytes | 268.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
   a5e93e3..6faf21b  ft/footer -> ft/footer
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git log
commit 6faf21b30fc58e357a338b6f6e7cd61e61113a79 (HEAD -> ft/footer, origin/ft/footer)
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 22:18:43 2023 +0300

    Revert "Add contact footer feature""
    
    This reverts commit a5e93e319ec814255051c92d5dbb2eb8c97bd8ba.

commit a5e93e319ec814255051c92d5dbb2eb8c97bd8ba
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 22:17:35 2023 +0300

    Add contact footer feature"

commit 1fda8727aad492719f8e0ccfb7d98b1522d85186
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 20:43:23 2023 +0300

    Add html biler plate to footer page

ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch ft/footer
Your branch is up to date with 'origin/ft/footer'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        footer features/

nothing added to commit but untracked files present (use "git add" to track)
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "Add new fetaure for footer"
[ft/footer 2bc2134] Add new fetaure for footer
 1 file changed, 12 insertions(+)
 create mode 100644 footer features/index.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git log
commit 2bc2134eabfa186549f26ba11ca87214d8cd7c71 (HEAD -> ft/footer)
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 22:22:27 2023 +0300

    Add new fetaure for footer

commit 6faf21b30fc58e357a338b6f6e7cd61e61113a79 (origin/ft/footer)
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 22:18:43 2023 +0300

    Revert "Add contact footer feature""
    
    This reverts commit a5e93e319ec814255051c92d5dbb2eb8c97bd8ba.

commit a5e93e319ec814255051c92d5dbb2eb8c97bd8ba
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 22:17:35 2023 +0300

    Add contact footer feature"

ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 548 bytes | 548.00 KiB/s, done.
Total 4 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
   6faf21b..2bc2134  ft/footer -> ft/footer
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout -b ft/squasing
Switched to a new branch 'ft/squasing'
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git merge --squash ft/footer 
Updating 97e7b5f..2bc2134
Fast-forward
Squash commit -- not updating HEAD
 footer features/index.html | 12 ++++++++++++
 footer.html                | 12 ++++++++++++
 2 files changed, 24 insertions(+)
 create mode 100644 footer features/index.html
 create mode 100644 footer.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch ft/squasing
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   footer features/index.html
        new file:   footer.html

ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "footer changes squashing"
[ft/squasing f60c88f] footer changes squashing
 2 files changed, 24 insertions(+)
 create mode 100644 footer features/index.html
 create mode 100644 footer.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push -u origin ft/sqaushing
error: src refspec ft/sqaushing does not match any
error: failed to push some refs to 'git@github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git'
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push -u origin ft/sqausing
error: src refspec ft/sqausing does not match any
error: failed to push some refs to 'git@github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git'
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push -u origin ft/squasing
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (5/5), 641 bytes | 320.00 KiB/s, done.
Total 5 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
remote: 
remote: Create a pull request for 'ft/squasing' on GitHub by visiting:
remote:      https://github.com/Murage-Ivy/Gym-Git-Exercise-Solutions/pull/new/ft/squasing
remote: 
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/squasing -> ft/squasing
Branch 'ft/squasing' set up to track remote branch 'ft/squasing' from 'origin'.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git log
commit f60c88f6a9707533c78689126ef09dac027e8ead (HEAD -> ft/squasing, origin/ft/squasing)
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 22:26:35 2023 +0300

    footer changes squashing

commit 97e7b5fed83b96d8be953c26613ac2a0fab478ac (origin/main, git-copy/main, main)
Merge: e0ff839 c51e1c4
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 20:34:33 2023 +0300

    Merge branch 'main' of github.com:Murage-Ivy/Gym-Git-Exercise-Solutions into main

commit e0ff839e56f52d00ee01e4329596efde2c5bfbed
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 20:17:26 2023 +0300

    Add a header to the home page file

commit c51e1c4d2181ec428613813bb90fe769fcb2defb
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git revert f60c8
Removing footer.html
Removing footer features/index.html
[ft/squasing e0e1078] Revert "footer changes squashing"
 2 files changed, 24 deletions(-)
 delete mode 100644 footer features/index.html
 delete mode 100644 footer.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git merge ft/footer
Merge made by the 'recursive' strategy.
 footer features/index.html | 12 ++++++++++++
 footer.html                | 12 ++++++++++++
 2 files changed, 24 insertions(+)
 create mode 100644 footer features/index.html
 create mode 100644 footer.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch ft/squasing
Your branch is ahead of 'origin/ft/squasing' by 7 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git log
commit 5f5b89ffe1a7b8852115b07cc9f9078276aea536 (HEAD -> ft/squasing)
Merge: e0e1078 2bc2134
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 22:28:51 2023 +0300

    Merge branch 'ft/footer' into ft/squasing

commit e0e107855bc0f5ac1c6568392e29afeb9f94ba77
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 22:28:17 2023 +0300

    Revert "footer changes squashing"
    
    This reverts commit f60c88f6a9707533c78689126ef09dac027e8ead.

commit f60c88f6a9707533c78689126ef09dac027e8ead (origin/ft/squasing)
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 22:26:35 2023 +0300

    footer changes squashing

commit 2bc2134eabfa186549f26ba11ca87214d8cd7c71 (origin/ft/footer, ft/footer)
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 22:22:27 2023 +0300

    Add new fetaure for footer

commit 6faf21b30fc58e357a338b6f6e7cd61e61113a79
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 22:18:43 2023 +0300

    Revert "Add contact footer feature""
    
    This reverts commit a5e93e319ec814255051c92d5dbb2eb8c97bd8ba.

commit a5e93e319ec814255051c92d5dbb2eb8c97bd8ba
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 22:17:35 2023 +0300

    Add contact footer feature"
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git revert 5f5b8
error: commit 5f5b89ffe1a7b8852115b07cc9f9078276aea536 is a merge but no -m option was given.
fatal: revert failed
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch ft/squasing
Your branch is ahead of 'origin/ft/squasing' by 7 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git reset --hard HEAD~
HEAD is now at e0e1078 Revert "footer changes squashing"
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch ft/squasing
Your branch is ahead of 'origin/ft/squasing' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git log
commit e0e107855bc0f5ac1c6568392e29afeb9f94ba77 (HEAD -> ft/squasing)
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 22:28:17 2023 +0300

    Revert "footer changes squashing"
    
    This reverts commit f60c88f6a9707533c78689126ef09dac027e8ead.

commit f60c88f6a9707533c78689126ef09dac027e8ead (origin/ft/squasing)
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 22:26:35 2023 +0300

    footer changes squashing

commit 97e7b5fed83b96d8be953c26613ac2a0fab478ac (origin/main, git-copy/main, main)
Merge: e0ff839 c51e1c4
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Mon May 15 20:34:33 2023 +0300

    Merge branch 'main' of github.com:Murage-Ivy/Gym-Git-Exercise-Solutions into main
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git merge --squash ft/footer
Squash commit -- not updating HEAD
Automatic merge went well; stopped before committing as requested
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "footer changes squashing"
[ft/squasing bcd49c8] footer changes squashing
 2 files changed, 24 insertions(+)
 create mode 100644 footer features/index.html
 create mode 100644 footer.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push 
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 433 bytes | 433.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
   f60c88f..bcd49c8  ft/squasing -> ft/squasing
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ 