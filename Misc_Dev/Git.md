# Git

## Assessment
* Why would I create a new branch?
* What do I do if I commit some private credentials?
* What happens if I type ‘git branch -D make-it-happen’ into the command line?

## Git Workflow
1. `git checkout -b [branch-name]`
1. Make changes to a bunch of files
1. `git status` (double check what's changed before adding changes to stage)
1. `git add [changed files]`
1. `git status` (double check what's staged before committing)
1. `git commit` just this file with a helpful message about what was changed `-m 'message'`

## Pull Request Workflow
1. `git checkout master`
1. `git pull`
1. `git checkout -b branch-name`
  1. When naming your branches, follow SfG convention that the branch consists of ...
    1. fix/more-specific-branch-name
    1. chore/more-specific-branch-name
    1. bug/more-specific-branch-name
1. Make a bunch of changes to the code
1. `git add [files worth saving]`
1. `git commit -m 'a helpful message'`
1. `git checkout master && git pull` (in case anyone else merged changes in the meantime)
1. `git checkout branch-name`
  1. if new changes came down when you ran `git pull` on master
  1. `git merge master`
    1. resolve conflicts and then `commit` changes with conflicts resolved
1. `git push [--set-upstream origin branch-name]`
1. Go to GitHub, open a pull request, double check your code for errors, and ask others to review your PR
1. Resolve all comments from review
1. Once your changes are approved, merge them into master

# Other Resources
[About Resolving Merge Conclicts](https://help.github.com/articles/resolving-a-merge-conflict-using-the-command-line/)
[About Branching](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)
