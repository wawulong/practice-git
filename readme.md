# Git practice

Please add your name and email to members file.

Practice steps:

1. Install git environmnet.
2. Config your information.
3. Clone this project.
4. Fix conflict if there is.
5. Create a feature branch base on develop one.
6. Add your name and email to members file in new line.
7. Create pull request assigning to me (Wen) on gitlab site.
8. Let us check the work flow for future.

# Git simple tutorial

[git - 简易指南](https://www.bootcss.com/p/git-guide/)

# Git local

1. Create branch and checkout to new branch
```
git branch new-branch-name
git checkout new-branch-name
```
2. Modify file

3. Add modified-file to stage
```
git add members
```
4. Commit it to repository
```
git commit
(write clarity title and brief for other people)
```

Refer to this flow ![git local operations](https://git-scm.com/figures/18333fig0106-tn.png)

# Git remote

After you finish, push this new-branch to remote.
```
git remote add origin http://gitlab-project-path
git remote push origin new-branch-name
```
Then create merge-request for this branch, and give it assignee and target
branch (these operations on gitlab site).

Refer to this flow ![git local and remote](https://blog.techbridge.cc/img/kdchang/cs101/git-workflow.png)
