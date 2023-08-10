---
layout: "../../layouts/MarkdownPost.astro"
title: "React-Native 仿 ONE一个 App"
pubDate: 2023-08-10
description: "Create native apps for Android, iOS, and more using React"
author: "Sita Tan"
cover:
  url: "https://github.com/adele-ty/Sita-blog/blob/1f9a18bc47d02f9b31565f3a881485aa95714ea1/public/Hangzhou/IMG_1155.JPG?raw=true"
  square: "https://github.com/adele-ty/Sita-blog/blob/1f9a18bc47d02f9b31565f3a881485aa95714ea1/public/Hangzhou/IMG_1155.JPG?raw=true"
  alt: "cover"
tags: ["技术", "React-Native"]
theme: "light"
featured: true
---

这个项目源于一场面试 😇，这场面试作为此项目的背景，就一起写在这篇博客里，不另开一篇了。

## 背景

前不久给多抓鱼投了简历，很快就收到了多抓鱼的笔试邀请，非常简单的笔试题，一道设计组件，考虑组件的复用性就 ok, 第二道是一道算法题，类似于力扣的螺旋矩阵，只不过这不是一个矩阵而是一个三角形的阵，总体来说简单，笔试后的第二天就收到了面试邀请，很遗憾面试挂了，不过面试的质量非常高，没有虚头巴脑的八股，至于挂掉的原因，大概率是技术栈不匹配，在这之前我还没有接触移动端开发，而多抓鱼的业务却主要是手机 App 和微信小程序，但是多抓鱼从接触到之后我就非常喜欢，因为我非常认同他们对于二手物品的认真态度，所以对于这次的拒信非常能理解却也心有不甘。内心 os：好，我这就开发一个 App 出来 😏。

## 过程

首先选择 React-Native 作为技术栈(本人 React/Vue 都可以，但是偏爱 React)，在 b 站找了一套视频教程，[Udemy 付费课程 -- React Native - 实用指南【2021 版】](https://www.bilibili.com/video/BV1FP4y1M7j2/?spm_id_from=333.999.0.0&vd_source=5b1a2d002407b526d14691e59aa59da6)，依旧是熟悉的 Maximilian Schwarzmüller，一共 200 个视频，看了 40 个左右，我就觉得不用继续看了，直接动手做吧。

## 实施

那么做一个什么 App 呢，最后在 github 一通搜索，决定仿 ONE 一个 这个 App，这个 app 我在高中时就使用过，那个时候我还是一个文艺青年，对这个文艺生活 App 简直爱不释手，再加上它简洁的设计，最终敲定就做这个了，到目前为止，已有的功能大概花了 2 个礼拜的时间，界面几乎完全按照 ONE 来开发，一路都很顺畅丝滑，没有遭遇很大的困难，时不时出现的小问题，都使用 Google+ChatGPT 解决了，从一开始的完全没有接触过 React-Native 到现在的非常熟练地使用基本组件，学到了很多，同时成功地引起了我对客户端开发的兴趣，后续可能会关注安卓开发，但是没有完整的后端接口是这个项目最大的痛点，基本只能展示内容，而无法与数据进行交互，而且展示的内容数据许多都是不符合需要的，我必须在调用后端接口之后，再处理成我需要的样子才能使用，因为这些接口是 ONE 3.5 版本之前的接口，现在早已经迭代了很多个版本了，不过学习 React-Native 的目的已经达到了。

## 成品

至于这个项目的成品展示，请移步我的 Repo [TWO is more](https://github.com/adele-ty/TWO)

README.md 有详细地介绍这个项目，包括目录结构、如何运行、效果图和后续的工作都一一列出来了
