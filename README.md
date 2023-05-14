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

ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash list
stash@{0}: On dev: temporily save changes in team page file
stash@{1}: On dev: temporily save changes in home page file
