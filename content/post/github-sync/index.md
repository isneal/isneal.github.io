---
title: Github Sync | ROS2 Workspace
description: Github 同步
slug: git
date: 2025-10-29 12:00:00+0800
image:
categories:
    - Tutorial
tags:
    - Github
weight:       # You can add weight to some posts to override the default sorting (date descending)
---

## 1) 准备：确认Git身份

```bash
git --version
git config --global user.name "Your Name"
git config --global user.email "you@example.com"   # 用 GitHub 绑定过的邮箱
```

## 2) github建立空仓库

建立空白仓库，不需要加入任何readme，license

## 3) 本地初始化仓库

```bash
cd ~/ros2_ws/src
git init
git branch -M main   # 直接把默认分支命名为 main（推荐）
```

## 4) 首次commit

```bash
git add .
git status      # 确认没有把 build/install/log 混进来
git commit -m "feat: initialize ROS2 workspace (ignore build/install/log)"
```

## 5) 绑定远程并推送

```bash
git remote add origin <REMOTE_URL>
git push -u origin main
```

## （可选）先拉取后推送

```bash
git remote add origin <REMOTE_URL>
git pull --rebase origin main   # 把远端 README 合并到本地提交之前
git push -u origin main
```

## （后续更新）

```bash
# 1. 查看状态
git status
# 2. 选择要提交的改动
git add -A              # 或者：git add <path/to/file>
# 3. 写清楚提交信息（建议英文动词开头）
git commit -m "fix: correct TF broadcaster for NED<->base_link"
# 4. 推送
git push
```
