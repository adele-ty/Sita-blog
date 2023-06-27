---
layout: "../../layouts/MarkdownPost.astro"
title: "一次面试经历记录"
pubDate: 2023-06-27
description: "一名艰难找工的前端打工人"
author: "Sita Tan"
cover:
  url: "https://raw.githubusercontent.com/adele-ty/Sita-blog/605a122836c71c900ca24ac47491226cfa186b3f/src/images/interview/JavaScript-logo.png"
  square: "https://raw.githubusercontent.com/adele-ty/Sita-blog/605a122836c71c900ca24ac47491226cfa186b3f/src/images/interview/JavaScript-logo.png"
  alt: "cover"
tags: ["技术", "面试", "前端"]
theme: "light"
featured: true
---

昨天刚刚经历一场前端面试，技术官很温和，问的问题也比较常见，几道 js 和 react 的问题，还有几道与项目有关的问题，最后手撕了一道算法题。

但是大脑习惯性面试宕机 🤪，让我对此次面试表现并不满意，但还是要夸夸自己，至少没有被面试官吊打，可以感觉到面试官对某些问题的回答感到比较满意。接下来对此次面试做一个复盘。

# js

1. 解释一下原型和原型链  
   请移步[原型与原型链](https://github.com/adele-ty/JavaScript/blob/main/%E5%8E%9F%E5%9E%8B%E5%92%8C%E5%8E%9F%E5%9E%8B%E9%93%BE.md)

老生常谈了，虽然已经理解的很透彻了，但是面试的时候总是很难回答的漂亮，我这该死的表达能力 😐

2. call、apply、bind 的差别以及性能
   请移步[改变 this 指向](https://github.com/adele-ty/JavaScript/blob/main/this.md)

很简单的问题，但是性能方面，我倒是没了解过，结果面试官说性能差别就在传参上，apply 的第二个参数是一个数组，需要解构，而 call 则不用，我对此表示半信半疑 🤔

# react

1. setState 是同步还是异步，怎么实现的
   请移步[setState](https://github.com/adele-ty/React.js/blob/main/useState.md)

2. diff 算法怎么实现的
   请移步[diff 算法](https://github.com/adele-ty/React.js/blob/main/virtual-dom%E5%92%8Cdiff%E7%AE%97%E6%B3%95.md)

# 算法题

翻转链表的后半部分  
面试的时候，写出来了，但是有点小问题，不过整体思路是对的，下面附上题解

```js
// 反转链表
const reverse = function (list) {
  let pre = null,
    temp = null,
    cur = list;
  while (cur) {
    temp = cur.next;
    cur.next = pre;
    pre = cur;
    cur = temp;
  }
  return pre;
};

// 找到链表的中间位置
const findMedium = function (list) {
  let fast = list,
    slow = list;
  while (fast.next && fast.next.next) {
    fast = fast.next.next;
    slow = slow.next;
  }
  return slow;
};

// 反转链表的后半部分
const finallyList = function (list) {
  if (!list && !list.next) return list;
  const mid = findMedium(list);
  const right = reverse(mid.next);
  mid.next = right;
  return list;
};
```

# 项目

1. 讲一下你觉得最难的项目，难点在哪

我自然而然想到的就是之前参与的一个后端项目，毕竟我还只是一个前端，难点：  
a. 对 nest.js 不熟悉  
b. 数据库设计
c. 安全

2. 知道对称加密和非对称加密的区别吗
   对称加密明文密文可以互相推导出来，非对称加密只能从明文推导出密文，而无法逆向推导出明文。以上回答是错误的。  
   正确的应该是对称加密只使用一把密钥来对数据进行加解密，而非对称加密使用两把密钥来进行加密，分别为公钥和私钥。

3. 在项目中是怎么对密码进行加密的
   使用 bcrypt 对密码加密，再存入到数据库中。面试官说在正常后端项目中这样就可以了吗，言外之意，似乎这不是标准的做法，但是我看了之前参与的后端项目，确实是这么做的，后续有去请教我 mentor 这个问题，他的回答是，这就是大多数的做法。

4. 为什么要对密码加密
   如果存储明文密码，黑客在攻破数据库之后，就可以直接看到明文密码，而许多用户的多个 app 使用的都是相同的账号和密码，因此，用户的多个 app 信息都会被窃取。面试官又反问我，那就算加密了，拿到密文不照样可以窃取用户信息嘛，一时语塞，现在一想，既然数据库都攻破了，那不直接各种自动化跑脚本干坏事，为啥还要纠结密码加没加密呢 😶
