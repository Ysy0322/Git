# 解决合并冲突

## 问题：Pull/Push 时远程分支与本地分支出现冲突

### 使用 Git Stash 解决冲突

Git Stash 可以暂存本地修改，避免直接冲突。

**步骤：**

### 1. 暂存本地修改
```bash
git stash
```
- 将本地修改暂时存储起来
- 使用 `git stash list` 查看保存的信息

### 2. 拉取远程更新
```bash
git pull --rebase
```
- 暂存了本地修改之后使用 pull 拉取远程代码

### 3. 还原暂存的内容
```bash
git stash pop stash@{0}
```
- 还原暂存的内容
- 如果只有一次 git stash 操作，直接使用 `git stash pop` 即可

### 4. 解决文件冲突
- 如果有文件冲突，冲突地方会自动标明具体冲突代码
- 手动编辑文件，解决冲突部分

### 5. 提交更改
```bash
git add .
git commit -m "解决冲突"
git push
```

---

## 问题：fatal: refusing to merge unrelated histories

### 原因
Git 拒绝合并没有共同历史的分支。

### 解决方法
使用 `--allow-unrelated-histories` 参数强制合并：

```bash
git pull origin master --allow-unrelated-histories
```

**使用场景：**
- 本地仓库和远程仓库是独立创建的
- 需要将两个独立的仓库合并

---

## 常用 Stash 命令

| 命令 | 说明 |
|------|------|
| `git stash` | 暂存当前修改 |
| `git stash list` | 查看所有暂存 |
| `git stash pop` | 恢复最近一次暂存并删除 |
| `git stash apply stash@{n}` | 恢复指定暂存但不删除 |
| `git stash drop stash@{n}` | 删除指定暂存 |
| `git stash clear` | 清空所有暂存 |

---

## 最佳实践

1. **提交前先 Pull**
   ```bash
   git pull origin master
   git add .
   git commit -m "message"
   git push origin master
   ```

2. **频繁提交本地代码**
   - 减少大规模冲突的可能性

3. **使用分支开发**
   - 在功能分支上开发，避免直接在 master 上操作
