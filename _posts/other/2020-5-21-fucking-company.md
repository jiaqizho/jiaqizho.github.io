---
layout: post
title: 公司的内鬼
category: other
keywords: other
---

## 1. 公司的内鬼

5月21，阴，突然发现公司很多同事都他妈是内鬼。

想起了#NINEONE歌词：
```
那确实没有几个家伙
花了心思对着镜子排练
为了 永远堵不上那些人的嘴
为了 人前做人在鬼前做个鬼

.....

Someone's killing me
Someone's killing me
Someone's killing me
Someone's killing me
Someone's killing me
Someone's killing me
Someone's killing me
Someone's killing me
```

## 2. 内鬼们

### 1. 一号内鬼们：fpga硬件团队

公司有两个fpag环境，一个英国环境，一个印度环境
当你发现硬件团队给你的fpga版本不对的时候，你发送了邮件然后：

1. 星期一发送了相关Bug邮件
2. 星期二，对接印度团队的RD A把邮件转给对接英国团队的BOSS B
3. 星期三，BOSS B转给他的小弟RD C
4. 星期四上午，小弟C告诉B需要和我们开个会
5. 星期四下午，小弟C和B拉着我开个了会，这个时候觉得得确认fpga版本，就把A给拉了进来。终于确定了fpga版本不对
6. 星期五，A说要给我们重新刷个fpga环境
7. 下一周一，我已经在对的fpga环境完成了开发。
8. 这周，A没给我刷环境，小弟C说他没测试过英国环境，不断地问我这么环境怎么测试。
9. 又过了一周，A终于给我刷好了环境，但是我早已完成了开发，小弟C也骚扰了我一周
10. 这一周某一天的下午，A突然问我linux代理怎么设置，内核如何更新....

被内鬼们折腾了这么长时间，我对这个项目也做得差不多了，换到了波兰人项目上。
一周的沟通成本就为了确认一个fpga版本，假如fpga固件有bug，我不敢想象....

### 2. 二号内鬼们：波兰兄弟

波兰团队(搞硬件的)需要合作项目，我理所应当的被老板卖了过去。
一周开了两次会，波兰胖子对着文档说了一堆架构，一行代码，一句话环境都没提。
拉了一个小弟A帮我搭环境

1. 当天开完会，我一直在等他邮件，他在会上说会给我一个simics的镜像和脚本。结果一直没等到
2. 第二天，我自己在看文档，看了半天，整了"一半"环境
    1. "一半"只的是，文档只告诉你申请了哪些权限，下载了哪些东西
    2. 我拉了项目和simics的环境(包括镜像，脚本，一大堆依赖)
    3. 文档未提及，当你拉simics的环境，如何使用
    4. 文档未提及，项目编译好，该怎么放到simics去跑
    5. 傻逼的内网repo，一个垃圾脚本进行一万次auth。我真是服了，还不能root去跑，你妈卖批的一个做硬件的，都是内核或者用户态的驱动，你让我普通用户拉取。最离谱的是，拉取下来得用root来编译。
3. 我感到了不对，call了波兰小弟，波兰小弟发了我邮件，但是邮件里面也是乱七八糟
4. 我按邮件的步骤跑，还是不对，又call了波兰小弟，波兰小弟很大气的说帮我弄好，给了他机器的权限
5. 波兰小弟进了机器，装了一下午，终于simics跑起来了。我表示很开心，并very thanks for him 
6. 第三天，我开开心的启动了simics，看了半天他的邮件，还是一大堆不理解的。终于弄到了晚上，simics成功跑起了test
7. 晚上，test全是错的，一个名为xxx_init的组件起不了nvme的admin queue.赶紧联系波兰小弟
    1. 波兰小弟明显不耐烦
    2. 波兰小弟告诉我，我下载的simics老了
    3. 我他妈的更新了一个晚上，没人告诉那个目录底下有个脚本设置环境，也没人告诉我需要提前缓存image
    4. 我是怎么发现的呢？我他妈的对着他的history，一行行去猜，然后才自己整理了步骤
    5. 更新了最新的simics，发现test还是不对
    6. 我他妈的又更新repo。才跑通了test，当然只有一些。因为波兰小弟告诉我只跑一些。

wdnmd 不知道后面还有多少坑，我觉得不会少。
内鬼答应我帮我搭建好，最后还是靠自己去猜。


## 3. 对内鬼们

我求求你们了，不要装逼了。

我求求你们了，不会写文档，就你妈的别写了。

我求求你们了，要写邮件，就你妈的好好写完整。

我求求你们了，要当ppt工程师，就你妈的不要给老子拉会了。

我求求你们了，不要当内鬼了。
  
最后再送几句#NINEONE的歌词给内鬼们

```
like brand new me
I got a grand new shit
drop that mother fuck beat
```
 