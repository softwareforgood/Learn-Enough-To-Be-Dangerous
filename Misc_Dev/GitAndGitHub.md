# Git and GitHub
## Basics
These are some basic resources, but there are additional ones at the bottom of this page. Those are optional, but recommended. Make sure you are able to answer the questions in the Assessment section.
* [Quick walkthrough](https://guides.github.com/activities/hello-world/)
* [More in-depth interactive tutorial if you want to learn more!](https://learngitbranching.js.org/)

## Assessment
* Why would I create a new branch?
* What do I do if I commit some private credentials?
* What happens if I type ‘git branch -D make-it-happen’ into the command line?
  
## Git
- Software that helps keep track of changes within any set of files
- We can use git by executing it's specific commands in a terminal 
```
git <command> <arguments if needed>
```

## GitHub
- A website that helps programmers create and collaborate on projects
- Contains many features dedicated to help programmers collaborate
  
Programmers are able to create repositories on GitHub, which is like a folder that will contain all the files and code for a project.
- Remote Repository: repositories stored on the internet or network
- Local Repository: repositories stored on your local computer
  
### How are Git and GitHub connected?
GitHub uses Git and its commands to do many important things related to working on a project together. These things include:
- Cloning a remote repository from GitHub onto your local computer
- Pulling updates from the remote repository onto your local computer
- Pushing updates from your local repository to the remote repository
- Creating new branches

## Git Workflow

1. `git checkout -b [branch-name]`
1. Make changes to a bunch of files
1. `git status` (double check what's changed before adding changes to stage)
1. `git add [changed files]`
1. `git status` (double check what's staged before committing)
1. `git commit -m 'message'` (add a helpful message about what was changed, so that others can understand what you did)

## Pull Request Workflow

1. `git checkout main`
1. `git pull`
1. `git checkout -b branch-name`
1. When naming your branches, follow SfG convention that the branch consists of ...
1. fix/more-specific-branch-name
1. chore/more-specific-branch-name
1. feature/more-specific-branch-name
1. Make a bunch of changes to the code
1. `git add [files worth saving]`
1. `git commit -m 'a helpful message'`
1. `git checkout main && git pull` (in case anyone else merged changes in the meantime)
1. `git checkout branch-name`
1. if new changes came down when you ran `git pull` on main
1. `git merge main`
1. resolve conflicts and then `commit` changes with conflicts resolved
1. `git push [--set-upstream origin branch-name]`
1. Go to GitHub, open a pull request, double check your code for errors, and ask others to review your PR
1. Resolve all comments from review
1. Once your changes are approved, merge them into main

## Other Notes
You may see the primary or default branch on a Git repository referred to as `master` instead of `main`. In the past, many default branches on GitHub were named `master`, but recently, there has been an effort to use more neutral/inclusive language and move away from the use of `master`. Most of the repositories at SfG have been reconfigured to use `main` instead, but there may be some older repositories or repositories from other organizations have not been updated to use the new naming conventions, likely due to time constraints and/or limitations related to how the application is set up.

# Other Resources

- [About Resolving Merge Conflicts](https://help.github.com/articles/resolving-a-merge-conflict-using-the-command-line/)
- [About Branching](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)
- [Git Commands Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)