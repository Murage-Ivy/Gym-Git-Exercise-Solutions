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

