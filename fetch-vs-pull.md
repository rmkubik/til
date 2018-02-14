# Git Pull vs Fetch
## tags
#git #bash #pull #fetch

## explanation
Branches in git are just a pointer to the most recent commit on their branch. `git fetch` updates the remote tracking branches and downloads any new file changes into our local repository (but not into our local branch). These changes are not pulled into your current working local branch until you run `git merge` and bring that remote branch's new changes into your branch. 

`git pull` is a "magic" operation that performs more than one task at once, updating your git remote tracking branches (like `git fetch`) but also merging that remote tracking branch into your current local branch (like `git merge`). 

## sources
https://stackoverflow.com/questions/292357/what-is-the-difference-between-git-pull-and-git-fetch
https://longair.net/blog/2009/04/16/git-fetch-and-merge/
