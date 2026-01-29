# Git 推送指南 (GitHub Push Guide)

本文档将指导你如何将整个项目或特定的文件/文件夹推送到 GitHub。

## 1. 基础准备

在开始之前，请确保：
- 你已经安装了 Git。
- 你已经拥有一个 GitHub 账号。
- 你已经创建了一个远程仓库（Remote Repository）。

## 2. 推送整个项目

如果你是第一次推送整个项目，请按照以下步骤操作：

### 步骤 A：初始化本地仓库 (如果尚未初始化)
```bash
git init
```

### 步骤 B：添加或更新远程仓库地址
如果你还没有添加远程仓库，或者想修改仓库地址：

**添加新地址：**
```bash
git remote add origin https://github.com/hanguang9527/drum
```

**如果已经存在 `origin` 但地址不对，更新它：**
```bash
git remote set-url origin https://github.com/hanguang9527/drum
```

### 步骤 C：推送所有更改
1. **添加所有文件到暂存区：**
   ```bash
   git add .
   ```
2. **提交更改：**
   ```bash
   git commit -m "提交信息 (例如: Initial commit)"
   ```
3. **推送到远程仓库：**
   ```bash
   git push -u origin main
   ```
   *(注意：如果你的主分支名为 `master`，请将 `main` 替换为 `master`)*

---

## 3. 推送特定的文件或文件夹

如果你只想推送项目中的一部分内容，可以使用以下命令：

### 推送特定文件
```bash
# 1. 添加特定文件
git add 路径/到/你的文件.txt

# 2. 提交
git commit -m "更新了特定文件"

# 3. 推送
git push origin main
```

### 推送特定文件夹
```bash
# 1. 添加特定文件夹
git add 路径/到/你的文件夹/

# 2. 提交
git commit -m "添加了新文件夹"

# 3. 推送
git push origin main
```

---

## 4. 常用 Git 命令速查

| 命令 | 说明 |
| :--- | :--- |
| `git status` | 查看当前仓库状态 (哪些文件被修改或未追踪) |
| `git log` | 查看提交历史 |
| `git pull origin main` | 从远程仓库拉取最新代码并合并 |
| `git checkout -b 分支名` | 创建并切换到新分支 |
| `git remote -v` | 查看当前配置的远程仓库地址 |

---

## 5. 常见问题处理

### 如果遇到推送失败 (Push rejected)
通常是因为远程仓库有你本地没有的更新。
**解决方法：** 先拉取远程代码。
```bash
git pull origin main --rebase
git push origin main
```

### 如果想忽略某些文件 (不推送到 GitHub)
编辑项目根目录下的 `.gitignore` 文件，将不需要推送的文件名或文件夹名写在里面。
