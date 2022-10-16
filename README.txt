SITE: [Git Site]: https://git-cmd.netlify.app/

TITLE: CMD in git

~git config --global user.name "anyname"
~git config --global user.email "email@email.com"
~git config --global color.ui auto

To view some couple of options in config
-git config

ctr-l to clear screen in bash
-git config -l = to view git configuration
Pres q after this.

This is only for new project
to make a folder a working directory for git just do:

-git init .

-To view list item in directory:
ls -a

-To remove files:
rm -rf .git

-To create new, empty files used
touch index.html

-To add a files on staging
git add

-To check the status of current directory and staging area:
git status

-To unstage a file
git rm --cached <file>

-To add all files in current directory to staging area
git add .

-To remove all files on staging area
git rm r --cached

If we are inside of another folder we can't git add the outside file if
we use the "git add ." previous directory file is not added to staging

Now to add all of the files of project in staging area we do
git add -A

-To commit a staged file
git commit -m "bootstrap project"

Now if we check the git status we created our own first 
save point in git.

-To check all our commit status:
git log

Now the hash here is the uniquely commit
commit 12e888fc5948e4e5c71e73e9dc5737ed971b98ee (HEAD -> master)

-To view all the files in commit
git show <hash>

Now to edit file in cli:
-vi index.js
-press i
-input anything
-press esc
-type :wq

To run or view file content:
-cat index.js

To view the changes in file:
-git diff

To discard the changes on file:
-git restore index.js

To change the message or ammend in git just do:
git commit --ammend -m "added body{} in main.css"

Repositories in GIT contain a collection of files of various
different versions of a project

commit - save only on local machine
push - save on online repo

NOTE: ammend - to change for the better: improve he tried to ammed

TITLE: Github

A platform for hosting and collaborating on Git repositories.

To push an existing repository from remote this is from github:
-git remote add origin <url>
-git branch -M main
-git push -u origin main

To view all branch in git:
-git branch

To change branch from master to main in git:
-git branch -M main

👉 Although in github master is now called main

To push a repository on remote:
-git push -u origin <branch>

👉 This will fail at first and our request is denied
 if our account is fresh and new so  we have to setup 
 our SSH key on the github.

Now to fix this problem we have to do:

1. Go to profile account settings in Github
2. Navigate to SSH and GPG keys

Check this documentation for all the steps:
https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

------------------------------
Now since we already push before on the remote branch all we have to do:
-git push

-----------------------------
To get a latest file on remote repo we need to use
-git pull

--------------------------
TITLE: Branches
main branch or master branch is the same and they are the default branch

1. A branch represents an independent line of development
2. When we create another branch for example we want to add a feature 
on our app we will work on another branch which is the feature branch
then when we are done with feature merging back to main will gonna happen

TITLE: Pull request

1. Create a branch
2. Making some changes
3. Pushing branch to remote
4. Raise a pull request so that someone can review changes
5. Then merge if everything is correct

TITLE: References
-git tag
-git checkout - same idea to switch
-git stash
-git switch <branch-name>
-cherry picking

TITLE: Mergin (Pull Request)

Merging directly is not a good idea and it is always best to
create a pull request

1. once push a branch and file into remote
2. Create a pull request
3. then if the merge pull request is success we can safelty delete the branch immediately or restore it

TITLE: Git workflow

1. Working with workflow always do is if you're working on a new
feature the first thing that you should do is "pull the latest changes"
from master/main "pull the changes" from the remote repo to local repo
from that point create a new branch "git checkout -b <branch-name>"
to create a new branch since we want to add on a feature.

2. Now it is advisable for us to "rebase" our changes against
master/main branch especially if we are working on this feature
for days or weeks. because master/main will move on.
so what we should do is to bring the latest changes from master
into our local machine. when we rebase we might or may not have conflicts
if we do have conflicts that is absolutely fine.

NOTE: This is applicable only on git cmd it is much more easier to use github desktop
3. If we have 10 commits then we have to resolve the conflicts for
each commit so what is advisable to do is to "squash" all of our
local commits first and then rebase master. 

so it is something like this
we squash first the current branch that we are working and then what
will happen is we only have one single commit. and then when we rebase.
we switch branch but before that we need to stash our current working branch
to switch and then in main we bring the changes from remote to local repo
and then after that we need to bring our current working feature commit on top of
updated main into our current working branch

TITLE: Dealing with conflicts

Conflicts happen when a file is updated in remote repo but we are not
aware that we push an updated file from our local into remote repo

TITLE: Merging Conflicts

Now when we pull there is a merge conflict that will be going to show.
there is a Head and Tail in order to fix that we have to deal with it
either deleting the conflict, keeping both changes or selecting only one

TITLE: Rebase

What is rebase?
If we are working on a branch, but let say that the main branch move on
and we don't have the commits from the main or master branch.

So what rebase does it says right i'm going to bring all the changes
from whatever branch that we want i'm going to bring the changes and
the changes will be underneath with our new branch.

To simplify:
1. Im gonna take all your commits away, 
2. im going to bring all commits from master into our current working branch
3. and then im gonna try and apply your changes on top of it.

TITLE: Git Rebase

So the idea of rebase again is:
What if we have update some files on main branch
But our current working branch is still not updated and left behind?
That is when the rebase needs to happen

----------------------------------------------------------------
---------------------------------------
On github desktop branch:
-Update from main makes current branch and the main branch merge
-compare to branch - compare the current branch to any branch then we can merge
-squash and merge into current


SUBNOTE: https://learn.microsoft.com/en-us/azure/devops/repos/git/merging-with-squash?view=azure-devops
NOTE: A simple way to think about this is that squash merge gives you just the file changes, 
NOTE: and a regular merge gives you the file changes and the commit history.


NOTE: git checkout vs git switch
https://linuxhandbook.com/git-switch-checkout/#:~:text=Difference%20between%20git%20checkout%20and%20git%20switch,-Here's%20the%20thing&text=It%20can%20also%20be%20used,working%20tree%20without%20switching%20branches.

NOTE: merging vs rebase
https://www.atlassian.com/git/tutorials/merging-vs-rebasing

NOTE: Squashing makes the commit into one

NOTE: Rebase
https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase#:~:text=What%20is%20git%20rebase%3F,of%20a%20feature%20branching%20workflow.

TITLE: Reminder

NOTE: IF there is a merge conflict in github pull request it is always best to pull first the merging problem
Check the image pull-request-conflict.png

Rebase rewrites the commit history
Merge let us know completely what happen on commit history

NOTE: Never use rebase when working with public repository

Useful site
https://learngitbranching.js.org/
https://medium.datadriveninvestor.com/git-rebase-vs-merge-cc5199edd77c

NOTE: How to undo commit in git bash
https://stackoverflow.com/questions/927358/how-do-i-undo-the-most-recent-local-commits-in-git?page=2&tab=scoredesc#tab-top

NOTE: Remove and Restore to what is current stage of commit
https://www.git-tower.com/learn/git/faq/git-discard-changes#:~:text=If%20you%20want%20to%20undo,%24%20git%20restore%20.&text=Again%3A%20please%20be%20careful%20with,able%20to%20get%20them%20back!

NOTE: git pull vs git merge origin/main (are just the samegit l)
https://stackoverflow.com/questions/21756614/difference-between-git-merge-origin-master-and-git-pull
