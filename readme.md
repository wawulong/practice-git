# Git Practice

This repository is a practice of git operations and workflow.

# Practice Steps

1. Install git environmnet
1. Config your information - name and email
1. Clone this project
1. Check out develop branch
1. Local operations - create branch, stage and commit changes
1. Remote operations - push branch, merge request (co-worker notification)

## Install git environment
Download and install git from [official site](https://git-scm.com/downloads).

## Config your information - name and email
Open teminal from side-menu (right key). Then execute belows:
```
git config --global user.name "newbie_name"
git config --global user.email "newbie_name@bizlinktech.com"

# Use the notepad to be the commit editor, default is vim
git config --global core.editor "notepad"
# Check the config
git config --global --list
```

## Clone this project

On your workspace,
```
git clone http://10.11.15.10/ks-rd-fw/git-practice.git
```

## Check out develop branch
Checkout develop repository (local-link),
```
git checkout develop
```

## Local operations - create branch, stage and commit changes


![git local operations](https://git-scm.com/figures/18333fig0106-tn.png)

1. Create a branch and checkout

```
git branch add-newbie-info
git checkout add-newbie-info

# Alternatives
git checkout -b add-newbie-info
```

2. Modify file

(blah blah...)

3. Stage modified-file

```
git add members
```

4. Check the status

```
git status
```

5. Check the changes

```
git diff
```

6. Commit the chages

```
git commit
# Leave the details
```
Refer [如何寫一個 Git Commit Message](https://blog.louie.lu/2017/03/21/%E5%A6%82%E4%BD%95%E5%AF%AB%E4%B8%80%E5%80%8B-git-commit-message/)

## Remote operations - push branch, merge request (co-worker notification)

1. Push your branch and do Merge-Requests

```
git push origin add-newbie-info
```

2. Select Merge Requests on the left side menu, write the details, blah blah...

If conflict, you have to fix it first, like pull it (local side) and fix the members revision.

```
git pull origin develop
# Check status
git status
# Open editor with member file and fix
```

# References

- [How can I set up an editor to work with Git on Windows?](https://stackoverflow.com/questions/10564/how-can-i-set-up-an-editor-to-work-with-git-on-windows/1431003)

- [整理一下vim命令的基本用法](https://blog.csdn.net/AmberWu/article/details/72733351)
- [Clean up your local branches after merge and delete in GitHub](http://www.fizerkhan.com/blog/posts/Clean-up-your-local-branches-after-merge-and-delete-in-GitHub.html)
```
git remote prune origin
```
- [Introduction to GitLab Flow](https://docs.gitlab.com/ee/topics/gitlab_flow.html)

# KS Gitlab New Repository Configuration

After create a project, some settings have to change:
1. Disable Auto DevOps pipeline to avoid build failed, Settings > CI/CD > Auto DevOps.
