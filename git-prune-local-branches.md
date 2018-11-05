# Remove Local Branches Merged into Remote
## tags
#git #prune #remote #merge

## explanation
`git fetch -p` (`--prune`) makes your tracking branches equivalent to those on the remote repository. After that, `git branch -r` (`--remote`) will list your tracking branches, freshly pruned. 

### Tracking Branches
> Tracking branches are local branches that have a direct relationship to a remote branch.
> Checking out a local branch from a remote branch automatically creates what is called a tracking branch. 

The egrep & grep command uses `git branch -vv` to determine if a local branch has a corresponding tracking branch for origin. Finally, the `git branch -d` command will delete the branch. If the branch is not equivalent to the copy on master, the branch will not be deleted.  

## examples
```bash
git fetch -p

git branch -r | awk '{print $1}' | egrep -v -f /dev/fd/0 <(git branch -vv | grep origin) | awk '{print $1}' | xargs git branch -d
```

## sources
https://stackoverflow.com/questions/13064613/how-to-prune-local-tracking-branches-that-do-not-exist-on-remote-anymore
https://stackoverflow.com/questions/4693588/git-what-is-a-tracking-branch
