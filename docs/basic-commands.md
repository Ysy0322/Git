# Git 基础操作

## 初始化和配置仓库

### 1. 初始化 Git 仓库
```bash
git init
```
在当前目录创建一个新的 Git 仓库。

### 2. 添加文件到暂存区
```bash
git add .
```
- `git add .` - 添加当前目录所有文件
- `git add <文件名>` - 添加指定文件

### 3. 提交更改
```bash
git commit -m "提交信息"
```
将暂存区的文件提交到本地仓库。

### 4. 关联远程仓库
```bash
git remote add origin <仓库地址>
```

**示例：**
```bash
git remote add origin https://github.com/username/repo.git
```

---

## 完整的初始化流程

### 场景一：从零开始创建仓库

```bash
# 1. 初始化仓库
git init

# 2. 添加文件
git add .

# 3. 提交
git commit -m "Initial commit"

# 4. 关联远程仓库
git remote add origin https://github.com/username/repo.git

# 5. 推送到远程
git push -u origin master
```

### 场景二：克隆现有仓库

```bash
# 克隆整个仓库
git clone https://github.com/username/repo.git

# 克隆指定分支
git clone -b <分支名> https://github.com/username/repo.git
```

---

## 常用基础命令

| 命令 | 说明 |
|------|------|
| `git status` | 查看仓库状态 |
| `git log` | 查看提交历史 |
| `git log --oneline` | 简洁显示提交历史 |
| `git diff` | 查看未暂存的修改 |
| `git diff --staged` | 查看已暂存的修改 |
| `git remote -v` | 查看远程仓库信息 |
| `git branch` | 查看本地分支 |
| `git branch -a` | 查看所有分支（包括远程） |

---

## 工作流程图

```
工作区 (Working Directory)
    ↓ git add
暂存区 (Staging Area)
    ↓ git commit
本地仓库 (Local Repository)
    ↓ git push
远程仓库 (Remote Repository)
```

---

## 配置 Git

### 设置用户信息
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### 查看配置
```bash
git config --list
```

### 设置默认编辑器
```bash
git config --global core.editor "code"  # VS Code
git config --global core.editor "vim"   # Vim
```

---

## 常见问题

### 修改最后一次提交
```bash
git commit --amend -m "新的提交信息"
```

### 撤销工作区修改
```bash
git checkout -- <文件名>
```

### 撤销暂存区文件
```bash
git reset HEAD <文件名>
```

### 查看远程仓库地址
```bash
git remote get-url origin
```

### 修改远程仓库地址
```bash
git remote set-url origin <新地址>
```
