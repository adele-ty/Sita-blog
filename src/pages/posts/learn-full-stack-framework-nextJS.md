---
layout: "../../layouts/MarkdownPost.astro"
title: "Next.js: The React Framework for the Web"
pubDate: 2023-06-25
description: "基于 React.js 扩展而来的全栈框架，可以快速搭建一个全栈应用程序"
author: "Sita Tan"
cover:
  url: "https://raw.githubusercontent.com/adele-ty/Sita-blog/5b3ef9b02759ea24f2823536fa330130dc1cfe80/public/Tianjin/IMG_1164.JPG"
  square: "https://raw.githubusercontent.com/adele-ty/Sita-blog/5b3ef9b02759ea24f2823536fa330130dc1cfe80/public/Tianjin/IMG_1164.JPG"
  alt: "cover"
tags: ["技术", "全栈", "Next.js"]
theme: "light"
featured: true
---

前前后后花了将近 3 周的时间，看完了这套 Next.js 的课程 [【Udemy 高分付费课程】Next.js 和 React - 完整指南 学习并使用 Next.js 搭建全栈应用程序（中英文字幕）上](https://www.bilibili.com/video/BV1G54y1o7RP/?vd_source=5b1a2d002407b526d14691e59aa59da6) [【Udemy 高分付费课程】Next.js 和 React - 完整指南 学习并使用 Next.js 搭建全栈应用程序（中英文字幕）下](https://www.bilibili.com/video/BV1v5411X7RG/?vd_source=5b1a2d002407b526d14691e59aa59da6)，课程老师是 Maximilian Schwarzmüller，个人认为讲的非常好，非常透彻且通俗易懂，打算下次把他的 React Native 也看完。

武装自己的大脑，在任何时候，都是人生中最具价值的投资。

以下主要是 Next.js 的一些优点，包括但不限于 🤠

## 路由

在 Next.js 中，一个 page（页面） 就是一个从 .js、jsx、.ts 或 .tsx 文件导出（export）的 React 组件 ，这些文件存放在 pages 目录下。每个 page（页面）都使用其文件名作为路由（route）。

### 静态路由

示例： 如果你创建了一个命名为 pages/about.js 的文件并导出（export）一个 React 组件，则可以通过 /about 路径进行访问。

### 动态路由

动态路由使用中括号 [variable].js 作为文件名，其中 variable 会映射成  URL query 的变量名称，在 React 中可以通过  useRouter 获取路由信息。

## 预渲染

传统 React 应用返回的 HTML 文件中，不包含应用的信息，因为页面是在客户端进行渲染的，所以服务端返回的源码通常只有一个 id 为 root 的 div 标签，不利于做 SEO（搜索引擎优化）。

而页面预渲染就可以解决这个问题，浏览器收到的 HTML 文件源码是包含了页面信息的代码。

Next.js 提供了两种页面预渲染方案，SSG 与 SSR。这两种方式的不同之处在于为 page 生成 HTML 页面的时机。Next.js 默认会预渲染所有没有动态数据的页面，而动态的数据还是像 React 一样在客户端渲染的。

### SSG(静态站点生成)

在构建时生成 HTML，并在每次页面请求时重用

### SSR(服务端渲染)

在每次页面请求时重新生成 HTML,适用于数据变化比较频繁的页面

## 优化图像

Next.js 提供了优化图片的方案——Image  组件， 它是对 &gt;img&lt; 元素的扩展。

使用 Image 组件有四点好处：

- 对各个设备使用合适的尺寸与格式（使用 Chrome 访问页面时，图片会转换成 webp 格式）
- 防止 Cumulative Layout Shift（累计布局偏移）
- 图片在视图中才会被加载
- 可以自定义图片尺寸，Next.js 会根据  Image  的  width  与  height  值，在页面请求服务端时，转换并缓存相应大小的图片。

## API 路由

API 路由为使用 Next.js 构建你自己的 API 提供了一种解决方案。

pages/api 目录下的任何文件都将作为 API 端点映射到 /api/\*，而不是 page。这些文件只会增加服务端文件包的体积，而不会增加客户端文件包的大小。

API 路由的出现也使得 React 不再只是单纯的作为一个前端框架，依靠 Next.js 完全就可以打造出一个前后端一体的应用程序
