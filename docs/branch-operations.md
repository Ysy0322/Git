# Git 分支操作指南

## 将远程分支合并到本地分支

### 场景：将远程 master 分支合并到本地的 branchLocal 分支

**步骤：**

1. **设置本地分支跟踪远程分支**
   ```bash
   git branch --set-upstream-to=origin/master branchLocal
   ```

2. **拉取并合并**
   ```bash
   git pull
   ```
   如果没有冲突，远程分支会自动合并到本地分支。

---

## Pull 和 Push 操作

### Pull：从远程拉取代码

**语法：**
```bash
git pull <远程主机名> <远程分支名>:<本地分支名>
```

**示例：** 取回 origin 主机的 master 分支，与本地的 xf 分支合并
```bash
git pull origin master:xf
```

### Push：推送代码到远程

**语法：**
```bash
git push <远程主机名> <本地分支名>:<远程分支名>
```

**示例：** 把本地的 xf 分支推送到 origin 主机的 master 分支
```bash
git push origin xf:master
```

**注意：** 
> 分支推送顺序的写法是 `<来源地>:<目的地>`
> - `git pull` 是 `<远程分支>:<本地分支>`
> - `git push` 是 `<本地分支>:<远程分支>`

---

## Clone 指定分支

**语法：**
```bash
git clone -b <分支名> <仓库地址>
```

**示例：**
```bash
git clone -b cloud-master https://github.wdf.sap.corp/MaCo-Application-Processing-Engine/v4.period.git
```

---

## 参考资料
- [Git 官方文档](https://git-scm.com/doc)
- [原文链接](https://blog.csdn.net/ymmccc/article/details/84111500)
