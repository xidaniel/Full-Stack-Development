## Git 

### Why?

Distributed version control system

跟踪项目中所有文件的变化

协调多个开发者之间的工作

回到任何时间的版本

本地快照和远程仓库

只能管理脚本文件

---

### **git config**

git congif  --system --> /etc/gitconfig

git config  --global --> .gitconfig   (recommend this)

- git config --global user.name "your name"
- git config --global user.email "your email"

git config  --local  --> ..git/config

git config --list

git config --global --list

//remove repository configuration
git config --unset[key]

git remote add origin https://github.com/xidaniel/XiPPMTool.git

git remote -v

---

### Git workflow

git status //查看当前文件状态

git init  //运行后会在当前目录下生成一个.git📁的隐藏文件夹

git add . //都放到staging的区域

git commit -m "first" //

git push

---

获取别人的repo进行修改

git clone

git pull

---

**回到从前**

git log //查看整个提交的历史

- git log --oneline --graph

git reset --hard~n 回到前n个版本号  //可以回溯到自己想要的版本

git reset --hard  版本号码 //回到指定的版本号

**去到未来**

git reflog //查看所有的HEAD记录

---

## checkout

- 针对单个文件操作

git checkout 版本号 --文件名  //选一个文件

进行workflow

---

## branch

- 通过用分支开发,可以得到不同版本

 git branch  分支名字      //建立分支

git branch  -a //查看现在分支情况

git checkout 分支名字  //切换到当前分支

git branch -d 分支名字  //删除分支

git merge --no--ff -m “” 分支名字 // 把分支merger到main里面,    no--ff (no fast forward)

---

merge 分支冲突

- 冲突: 当自己在branch操作时,别人同时也在main进行了更新.
- 手动合并成冲突

---

## rebase 来解决分支冲突

```markdown
在开发branchB的时候,branchA也同时被人修改了, 解决合并的问题

情况:
v1---------v3----- branchA
  \----v2---------v4---- branchB

step1, 把v3单独拿出来
          v3
v1-------------- branchA
  \----v2---------v4---- branchB

step2, 合并branchA和branchB
          v3
v1----v2-----v4----- branchA, branchB

step3, 再把v3加到后面
v1----v2----v4----v3-- branchA, branchB
```

合并

```shell
git rebase branch name
/confilt is here/
//手动修改一下
git rebase --continue
```

git merge branchx

git pull --rebase

git push

