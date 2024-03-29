---
title: 上海封城期间，我用Notion做家庭物资管理
date: 2022-5-20
tags:
- Notion
---

此文主要受众是没有使用过Notion的同学，用实际例子介绍Notion的database基本功能，阅读耗时约1分钟。

---

## 原因

众所周知，22年3月以来，上海全城已经静态管理2个多月了，对居民要求足不出户，吃的主要靠街道统一配送和社区自发团购。家里两个互联网农民工，本来都靠公司食堂和外卖解决吃饭问题，这下要自己手动做菜，同时因为居家办公明显增加的沟通成本导致工作时长不减反升，吃饭出现了诸多问题，例如

- 冰箱蔬菜物资疏于管理，存在过期浪费。
- 有的食材外表看着挺好，其实已经存放太久，里面都坏了。
- 想做个硬菜发现关键的辅料缺少。
- 两人都沉迷工作，过了饭点了发觉饿了还要临时想破脑洞。

## 腾讯文档
为了解决上述问题，我做了表格整理，第一个版本是在腾讯文档，像这样

{% asset_img Untitled.png %}

在线表格使用上主要有一个不便，就是筛选和排序功能要手动执行刷新。然后我就想到把他迁移到Notion的数据库中，在Notion里面是这样的

{% asset_img Untitled1.png %}

首先这里的 过期预计剩余 和 过期时间 列字段是利用公式计算得出的，其他用到的还有 时间、下拉单选、文本、纯数字等多种数据列功能，在Notion中可以方便的切换调整。

{% asset_img Notion_logo_2020.svg %}

## Notion
> Notion是一款集成了笔记、知识库、数据表格、看板、日历等多种能力于一体的应用程序，它支持个人用户单独使用，也可以与他人进行跨平台协作。Notion由Ivan Zhao、Simon Last于2016年在旧金山创立的。截至2021年10月，Notion估值103亿美元，在全球拥有超2000万用户，团队规模为180人左右。
> 

而相比传统文档，Notion主要特点是可以对同一份数据做多视图的管理，同时Notion的过滤和排序功能在当数据有变更时是实时刷新的，使用体验提升明显。对于其他的场景，例如添加数据或者查看某一大类的情况时，会需要定制的过滤和排序规则，这里可以添加多个视图，方便切换操作。如果平时对数据表格经常要改个筛选条件反复看的同学，可以试试看Notion。

为了解决临时不好规划的问题，我还新增了另一个表格，一日三餐规划，每天晚上我会先检查保质期表格，搭配食材，确定第二天的三餐搭配并记录，对应的菜谱也查好放在页面详情（Notion表格中的每一行数据都是一个独立页面，页面内还是可以继续嵌套其他块）内，做的时候直接看即可。

{% asset_img Untitled2.png %}

{% asset_img Untitled3.png %}

每天晚上我最多就花5分钟的时间，就规划好了，这样终于解决了开头提到的四个问题，每天吃的终于走上了正轨。附上昨晚的杏鲍菇炒肉，食材都是社区发的

{% asset_img Untitled4.png 昨天的成果%}

## 总结
其实Notion还有更多高级且实用的功能，有很多博主都出了教程，在个人任务管理、目标制订与拆解、读书笔记、网页摘抄等多个领域有很好的实践例子。如果你还没有用过Notion，推荐试试看。

和Notion非常类似的国产软件还有 我来 和 FlowUs，核心的基于块的编辑和数据库功能都有，但对程序员来说很重要的API功能却没开放，所以我依然选择了Notion。大家可以把三款都试用一下，根据自己需求决定。我把三家产品的官网链接都放在下面。

[Notion - One workspace. Every team.](https://www.notion.so/)

[我来 wolai - 不仅仅是未来的云端协作平台与个人笔记](https://www.wolai.com/)

[FlowUs 息流 - 新一代生产力工具](https://flowus.cn/)

最后期待早日解封。
