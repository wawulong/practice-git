# FW work instructions

# Document and templates
## 工作文件範本/線上文件

- Google drive: KS_RD_FW
- [新項目/專案檢查表](https://docs.google.com/spreadsheets/d/1b95Q5ky9YXmZh5hNtW3IkPgrY2tPiAGlUnjyGGa3yJs/edit#gid=1429060716) (收到新專案SW/FW需要執行的工作檢查表)
- [工作日報](https://docs.google.com/spreadsheets/d/1MMgnXeBbXcZQlSFji4i4CvEL3s2ZK4d92m83klq44Hk/edit#gid=0) (每月由負責人確認內容後郵寄, 考慮用谷歌文件線上統一修改)
- [工作周報](https://docs.google.com/spreadsheets/d/1nf-0e-CyoqaZkCk1hBNIYWVgMheHJPDt6JUjH1xVzbg/edit#gid=901739152) (每月由負責人確認內容後郵寄, 考慮用谷歌文件線上統一修改)
- [FW財產表與工作總結](https://docs.google.com/spreadsheets/d/19900ndwEAJzICcl2nVzJPEKaE-Vh1MTsGP-F25Iik40/edit#gid=549601375)

## 績效相關文件
- [績效評分表](https://docs.google.com/spreadsheets/d/1QlYCfw7t8cuHq0v3qnGy_DJgJEJXGdNuq9MRJifJkX4/edit#gid=1033936910) (文件分享權限給領導,不公開評量)

## 技能
- [Git版本追蹤練習](http://10.11.15.10/rd_fw/git-practice)及[Git相關內容範本](http://10.11.15.10/rd_fw/git-practice/tree/develop/template)

# Gitlab new a project note

After create a project, some settings have to change:
1. Default Branch, for good workflow, it uses **develop** branch to be default one, Settings > Repository > Default Branch (push first).
2. Protected Branches, for miss merge, it has to protect develop and master (for release) branches, Settings > Repository > Protected Branches (push first)
3. Disable Auto DevOps pipeline to avoid build failed, Settings > CI/CD > Auto DevOps.

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

## Git simple tutorial

[git - 简易指南](https://www.bootcss.com/p/git-guide/)

- [浅谈命令行（一）：命令行基本操作（包括vim在终端的基本操作）](https://zhuanlan.zhihu.com/p/34522441)
    - [整理一下vim命令的基本用法](https://blog.csdn.net/AmberWu/article/details/72733351)

## Git GUI tool - TortoiseGit

[TortoiseGit日常工作中的基本操作(clone、pull、commit、push、merge)](http://blog.leanote.com/post/qian_c/TortoiseGit%E6%97%A5%E5%B8%B8%E5%B7%A5%E4%BD%9C%E4%B8%AD%E7%9A%84%E5%9F%BA%E6%9C%AC%E6%93%8D%E4%BD%9C-clone%E3%80%81pull%E3%80%81commit%E3%80%81push%E3%80%81merge)

## Git local

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

## Git remote

After you finish, push this new-branch to remote.
```
git remote add origin http://gitlab-project-path
git push origin new-branch-name
```
Then create merge-request for this branch, and give it assignee and target
branch (these operations on gitlab site).

Refer to this flow ![git local and remote](https://blog.techbridge.cc/img/kdchang/cs101/git-workflow.png)

# Prune local branchs

```
git remote prune origin
```

## Example, prune unnecessary branchs
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
