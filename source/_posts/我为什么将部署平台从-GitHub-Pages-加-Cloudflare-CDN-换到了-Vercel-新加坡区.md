---
title: 我为什么将部署平台从 GitHub Pages 加 Cloudflare CDN 换到了 Vercel 新加坡区
tags:
  - 折腾
  - 网络
  - 部署
  - 博客
  - Vercel
  - 运维
  - 站长
  - GitHub
  - Cloudflare
  - GitHub Pages
categories:
  - 经验总结
abbrlink: 3361145490
date: 2026-03-03 22:50:38
---

从去年 6 月份折腾博客开始，平时我一直在网上冲浪，学习前辈们的各种搭建博客经验。

## 部署博客的开始

刚开始折腾 [Hexo](https://hexo.io/) 加 [Butterfly 主题](https://butterfly.js.org/) 的时候，我还是用的 GitHub Pages 默认的 `username.github.io` 域名。众所周知，GitHub 和 GitHub Pages 的服务器位于美国，在国内访问速度并不理想。

## 添加自定义域名和加速访问

在去年 11 月份的时候，为了配合 Cloudflare CDN 加速访问，我购买了 `dorahonor.me` 这个域名。不得不说这个域名很符合我口味，既有我网名，结尾的 `.me` 顶级域名不仅价格实惠，也凸显了个人站点性质。

虽然说加 CDN 的过程还算顺利，速度感觉也还行，就先用了。而且测下来在国内也没被墙，挺好。

然而，有段时间我闲得无聊使用 [炸了么](https://zhale.me/) 进行测速，发现国内速度并不是特别理想……

而使用 Vercel 搭建且部署在新加坡的评论系统，速度要比 Cloudflare CDN 加 GitHub Pages 理想不少。

### 开始换到 Vercel 新加坡区部署

考虑到根域名要换成个人引导页，于是在 Vercel 部署的博客域名则使用 `blog.dorahonor.me` 子域名，这样能凸显博客页。

在一通部署和换部署地区到新加坡后，访问速度终于提升！在 [炸了么](https://zhale.me/) 的速度表现也符合预期。

虽然说 Vercel 免费的 Hobby 计划有一定的限制，但是给的用量对于访问量不多的博客站点来说，非常合适。因此，以后就只在 Vercel 新加坡区部署了！

## 为什么用 Vercel 新加坡区？

国内访问速度比 Cloudflare CDN 和 GitHub Pages 快许多，而且新加坡属东南亚，距离国内不远，加上新加坡华人不少和用华文，就选择了新加坡区。
