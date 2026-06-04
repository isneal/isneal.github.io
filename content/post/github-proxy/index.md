---
title: Github Proxy | gh-proxy.com
description: Github 代理
slug: git-proxy
date: 2026-06-04 12:00:00+0800
image:
categories:
    - Tutorial
tags:
    - Github
weight:       # You can add weight to some posts to override the default sorting (date descending)
---

## 1) 配置指令

```bash
git config --global url."https://gh-proxy.com/https://github.com".insteadOf "https://github.com"
```

## 2) 验证配置成功与否

```bash
git config --global --get-regexp url.*
```

## 3) 撤销 恢复

```bash
git config --global --unset url."https://gh-proxy.com/https://github.com".insteadOf
```

## 4) 注意事项

1. SSH 链接：上述配置仅对 HTTPS 协议（`https://github.com/...`）生效。如果你使用 SSH 链接（`git@github.com:...`），该配置不会起作用。

2. 代理稳定性：gh-proxy.com 这类公共代理服务器的稳定性由第三方维护，如果下载速度未见提升或报错，可能是该代理服务器当前的负载过高。
