# Git

## Assessment
* Why would I create a new branch?
* What do I do if I commit some private credentials?
* What happens if I type ‘git branch -D make-it-happen’ into the command line?

## Git Workflow
* `git checkout -b [branch-name]`
* Make changes to a bunch of files
* `git status` (double check what's changed before adding changes to stage)
* `git add [changed files]`
* `git status` (double check what's staged before committing)
* `git commit` just this file with a helpful message about what was changed `-m 'message'`

## Pull Request Workflow
* `git checkout master`
* `git pull`
* `git checkout -b branch-name`
  * When naming your branches, follow SfG convention that the branch consists of ...
    * fix/more-specific-branch-name
    * chore/more-specific-branch-name
    * bug/more-specific-branch-name
* Make a bunch of changes to the code
* `git add [files worth saving]`
* `git commit -m 'a helpful message'`
* `git checkout master && git pull` (in case anyone else merged changes in the meantime)
* `git checkout branch-name`
  * if new changes came down when you ran `git pull` on master
  * `git merge master`
    * resolve conflicts and then `commit` changes with conflicts resolved
* `git push [--set-upstream origin branch-name]`
* Go to GitHub, open a pull request, double check your code for errors, and ask others to review your PR
* Resolve all comments from review
* Once your changes are approved, merge them into master

# Other Resources
[About Resolving Merge Conclicts](https://help.github.com/articles/resolving-a-merge-conflict-using-the-command-line/)
[About Branching](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)
