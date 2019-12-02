# FW work instructions

### Document and Templates

- Google drive: KS RD FW
    1. Project checklist, **SW/FW Project Checklist**
    2. SW/FW test case, **SW/FW Test Case**
    3. Daily report, **Daily Report - Wen Wu**
    4. Weekly report, **Weekly Report - Wen Wu**
    5. Work completion list, **Work Completion**
    6. Property list, **Property Management**

- Performance Evaluation
    1. Members performance evaluation *in private*, **Members Performance**

### Gitlab Configuration

After create a project, some settings have to change:
1. ~~Default Branch, Settings > Repository > Default Branch~~
2. ~~Protected Branches, Settings > Repository > Protected Branches~~
3. Disable Auto DevOps pipeline to avoid build failed, Settings > CI/CD > Auto DevOps.

### Gitlab Workflow

Please refer to:
1. [GitLab Workflow: An Overview](https://about.gitlab.com/blog/2016/10/25/gitlab-workflow-an-overview/)
2. [Introduction to GitLab Flow](https://docs.gitlab.com/ee/topics/gitlab_flow.html)

### Git Practice

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

### Git Simple Tutorial

[git - 简易指南](https://www.bootcss.com/p/git-guide/)

- [浅谈命令行（一）：命令行基本操作（包括vim在终端的基本操作）](https://zhuanlan.zhihu.com/p/34522441)
    - [整理一下vim命令的基本用法](https://blog.csdn.net/AmberWu/article/details/72733351)

- [Git可视化极简易教程 — Git  GUI使用方法](https://www.runoob.com/w3cnote/git-gui-window.html)

### Git GUI tool - TortoiseGit

[TortoiseGit日常工作中的基本操作(clone、pull、commit、push、merge)](http://blog.leanote.com/post/qian_c/TortoiseGit%E6%97%A5%E5%B8%B8%E5%B7%A5%E4%BD%9C%E4%B8%AD%E7%9A%84%E5%9F%BA%E6%9C%AC%E6%93%8D%E4%BD%9C-clone%E3%80%81pull%E3%80%81commit%E3%80%81push%E3%80%81merge)

### Git Local Operations

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

Before step 4, you can change git default editor to notepad (windows).
Refer to
[How can I set up an editor to work with Git on Windows?](https://stackoverflow.com/questions/10564/how-can-i-set-up-an-editor-to-work-with-git-on-windows/1431003)
```
git config core.editor notepad (to be verify)
```
or you can learn bash and vim [整理一下vim命令的基本用法](https://blog.csdn.net/AmberWu/article/details/72733351)

4. Commit it to repository
```
git commit
(write clarity title and brief for other people)
```

Refer to this flow ![git local operations](https://git-scm.com/figures/18333fig0106-tn.png)

### Git Remote Operations

After you finish, push this new-branch to remote.
```
git remote add origin http://gitlab-project-path
git push origin new-branch-name
```
Then create merge-request for this branch, and give it assignee and target
branch (these operations on gitlab site).

Refer to this flow ![git local and remote](https://blog.techbridge.cc/img/kdchang/cs101/git-workflow.png)

### Prune Local Branch with Remote

```
git remote prune origin
```

Example:

```
Wen@DESKTOP-UIEVQIG MINGW64 /c/workspace/Project/git-practice (local-sync)
$ git br -a
  develop
* local-sync
  master
  principle
  template
  remotes/origin/HEAD -> origin/develop
  remotes/origin/develop
  remotes/origin/longfei
  remotes/origin/master
  remotes/origin/patch-1
  remotes/origin/patch-2
  remotes/origin/tutorial

Wen@DESKTOP-UIEVQIG MINGW64 /c/workspace/Project/git-practice (local-sync)
$ git remote prune origin
Pruning origin
URL: git@10.11.15.10:rd_fw/git-practice.git
 * [pruned] origin/longfei
 * [pruned] origin/patch-1
 * [pruned] origin/patch-2
 * [pruned] origin/tutorial

Wen@DESKTOP-UIEVQIG MINGW64 /c/workspace/Project/git-practice (local-sync)
$ git br -a
  develop
* local-sync
  master
  principle
  template
  remotes/origin/HEAD -> origin/develop
  remotes/origin/develop
  remotes/origin/master
```
