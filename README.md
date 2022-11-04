# alpro-tugas1
Tugas
Feature / Release

git checkout -b develop
git checkout -b feature_branch

# a bunch of work is done on the features
git checkout -b develop
git merge feature_branch
git branch -D feature_branch

# ready for a release branch
git checkout -b develop
git checkout -b release/0.1.0

# assuming that the release branch is done
git tag -a 0.1.0 -m "Release 0.1.0"

# merge release back into master
git checkout master
git merge release/0.1.0
git push
git push --tags

# merge release back into develop
git checkout develop
git merge release/0.1.0
git push

git branch -D release/0.1.0

===

Hotfix

git checkout master
git checkout -b hotfix_branch

# close/reference the related issue
git commit -m "Fixes #1"
git tag -a 0.1.1 -m "Release 0.1.1"

# finished hotfix_branch
git checkout master
git merge hotfix_branch
git push
git checkout develop
git merge hotfix_branch
git push
git branch -D hotfix_branch

===

Amend Commit

git commit --amend
