# gitflow

https://www.atlassian.com/git/tutorials/comparing-workflows

https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow

https://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows



https://www.toptal.com/git/git-workflows-for-pros-a-good-git-guide


rebase:

https://benmarshall.me/git-rebase/

Git Rebasing Examples

The example below combines git rebase with git merge to maintain a linear project history. This is a quick and easy way to ensure that your merges will be fast-forwarded.

# Start a new feature
git checkout -b new-feature master
# Edit files
git commit -a -m "Start developing a feature"

In the middle of our feature, we realize there’s a security hole in our project:

	
# Create a hotfix branch based off of master
git checkout -b hotfix master
# Edit files
git commit -a -m "Fix security hole"
# Merge back into master
git checkout master
git merge hotfix
git branch -d hotfix

After merging the hotfix into master, we have a forked project history. Instead of a plain git merge, we’ll integrate the feature branch with a rebase to maintain a linear history:

git checkout new-feature
git rebase master

This moves new-feature to the tip of master, which lets us do a standard fast-forward merge from master:

git checkout master
git merge new-feature

 
