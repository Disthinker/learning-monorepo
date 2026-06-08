# Git Workflow Notes

日期：2026-06-08  
阶段：Phase 1 / Day 3  
主题：Git 基础工作流训练

## 1. 今日练习目标

今天练习 Git 的最小日常工作流：

1. 查看状态
2. 查看修改
3. 暂存文件
4. 提交修改
5. 查看提交历史
6. 创建分支
7. 合并分支
8. 撤销未暂存修改

## 2. 常用命令记录

| 命令 | 作用 | 今天是否练习 |
|---|---|---|
| `git status` | 查看工作区和暂存区状态 | 是 |
| `git diff` | 查看未暂存修改 | 是 |
| `git add` | 把修改加入暂存区 | 是 |
| `git commit` | 创建一次本地提交 | 是 |
| `git log --oneline -5` | 查看最近提交 | 是 |
| `git switch -c <branch>` | 创建并切换分支 | 是 |
| `git switch main` | 切回 main 分支 | 是 |
| `git merge <branch>` | 合并分支 | 是 |
| `git restore <file>` | 恢复未暂存修改 | 是 |

## 3. 今日理解

### 工作区

工作区是我正在编辑的文件状态。

### 暂存区

暂存区是下一次 commit 准备提交的内容。

### 本地仓库

本地仓库保存已经 commit 的历史。

### 远程仓库

远程仓库是 GitHub 上的版本，用于备份和同步。

## 4. 今日练习结论

Git 的基本闭环不是只会 `add` 和 `commit`，而是要能在每一步知道文件处于什么状态。

以后每天提交前必须至少执行：

```powershell
git status
git diff
git log --oneline -5
```



TEMP LINE FOR RESTORE PRACTICE
