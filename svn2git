#!/bin/bash

GIT_REPO_NAME=git_repo
GIT_REPO=https://user@bitbucket.org/user/$GIT_REPO_NAME.git
SVN_REPO=http://svn.repo.com/repo/ %under trunk

rm -rf $GIT_REPO_NAME
mkdir $GIT_REPO_NAME
cd $GIT_REPO_NAME
git init
git remote add origin $GIT_REPO

cd ..

git svn clone $SVN_REPO --no-metadata -s $GIT_REPO

cd $GIT_REPO_NAME

cp -Rf .git/refs/remotes/origin/tags/* .git/refs/tags/
rm -Rf .git/refs/remotes/origin/tags
cp -Rf .git/refs/remotes/origin/* .git/refs/heads/
rm -Rf .git/refs/remotes/origin

git branch -d trunk

# IT SHOULD REST SOME BRANCHES AS trunk@number 
# YOU SOULD USE
#    git branch
# TO SEE THEM, THEN YOU CAN USE
#    git brand -d trunk@number
# TO DROP IT BEFORE SEND IT TO ORIGIN

#git push origin --all
#git push origin --tags
