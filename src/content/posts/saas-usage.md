---
title: 正确使用 Cloudflare SaaS
published: 2026-06-06
description: '正确使用 Cloudflare SaaS 优选你的 cf 站点'
tags: [Cloudflare, 优选, 教程]
category: '教程'
draft: true
---

# 前言
最近用虚拟卡号薅了个r2存储桶，正好想尝试尝试从来没接触过的cf saas，但可谓道阻且跻  
看了二叉大佬的教程，不知道我是有阅读障碍吗，我看到眼睛花都没搞懂（好在最后还是搞懂了🥴）

## 简述 SaaS
SaaS初衷是让托管在非Cloudflare的域名也用上cf的cdn，当然它也是一种很不错的优选方案  

何时需要：
- **example.com** 托管在了Cloudflare，并且 `www.example.com` 使用了Cloudflare的CDN，
- **example.org** 托管在了**非Cloudflare**，且想让 `www.example.org` 用上Cloudflare的CDN，且站点内容与 `www.example.com` 相同
  > 即镜像 **www.example.org** 到 `www.example.com`
- Cloudflare 为 **www.example.com** 默认分配的代理IP访问速度不佳，想要通过 **www.example.org** 镜像它并做**优选**

# 开始

> [!IMPORTANT]
> 一切的一切都需要您首先拥有一张银行卡（Visa，万事达，银联…），并在 Cloudflare 中验证<br>
> 虚拟卡也行，因为启用SaaS**不需要任何开支**（免费）

1. 登录 [Cloudflare 仪表盘]，转到 **oxue.de**（**你的域名**）-- **SSL/TLS** -- **自定义主机名