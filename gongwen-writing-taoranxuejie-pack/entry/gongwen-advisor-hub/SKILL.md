---
name: gongwen-advisor-hub
description: |
  何时调用: facade或上游已确认用户需要公文写作诊断、方法解释或训练路径时。
  何时不调用: 用户只需要直接成稿、不关心方法过程的场景；纯角色扮演批注场景；需要即时交付定稿的场景。
  关键trigger: "为什么我总写不好"、"这个材料站位不够怎么办"、"讲话稿和总结有什么区别"、"怎么练公文写作"
source: 公文写作技能包·陶然学姐
tags: [思维顾问入口, 诊断, 方法辅导, 训练路径, 技能编排]
related_skills:
  - slug: concept/gongwen-active-vs-passive
    relation: composes-with
  - slug: knowledge/gongwen-problem-analysis
    relation: depends-on
  - slug: method/gongwen-structure-build
    relation: composes-with
---

# 思维顾问总控入口

## 目标

把“不会写、写不稳、写不高、写不快、写不久”的问题诊断成具体卡点，并给出可执行的方法路径。

默认前提：
- facade 或上游路由已经确认当前任务属于“诊断模式”
- 当前入口只处理顾问视角的拆解、解释和训练建议
- 如发现任务其实要直接交付成稿或要扮演角色，只把任务退回 facade，不在本入口内部改判角色

## 何时使用

当用户出现以下目标时，优先激活：
- 想知道自己写作差在哪里
- 想学某个具体方法，而不是让你直接代写
- 想理解标题、结构、站位、格式、文种、检索等底层逻辑
- 想建立长期训练路径，摆脱“写了很多还是没进步”

## 显式触发词

### 强触发词

- “为什么我总写不好”
- “这个材料问题出在哪”
- “怎么提升站位 / 高度 / 结构”
- “怎么系统练公文写作”
- “讲话稿和总结有什么区别”
- “审题总跑偏怎么办”

### 弱触发词

- “有没有更好的方法”
- “我总觉得写得不对”
- “怎么才能更像样”
- “我写了很多还是没进步”
- “这个思路是不是有问题”

### 排除触发词

- “帮我直接写一版”
- “给我出个能直接交的稿子”
- “你扮演领导批一下”
- “模拟一下汇报”

### 路由备注

- 一旦命中“为什么、怎么提升、怎么练、哪里有问题、有什么区别”等诊断型问法，优先进入本入口
- 如果同时出现“顺便直接帮我改 / 帮我写一版”，优先交回 `entry/gongwen-facade-hub` 由 facade 判断主任务和附属任务

## 诊断框架

先判断问题属于哪一层：

| 问题类型 | 典型表现 | 首选技能 |
|---|---|---|
| 心态层 | “我不会”“我不敢动笔”“总等别人给模板” | `concept/gongwen-active-vs-passive`, `concept/gongwen-subjective-activation` |
| 价值层 | “写材料值不值得学”“总觉得没意义” | `concept/gongwen-writing-value` |
| 成长层 | “写了很多没进步” | `concept/gongwen-quantity-to-quality` |
| 高度层 | “像流水账”“站位不够”“太虚或太实” | `concept/gongwen-virtual-real-combination`, `method/gongwen-perspective-take` |
| 审题层 | “领导意思总拿不准” | `knowledge/gongwen-problem-analysis` |
| 规则层 | “文种、格式、标题、用词拿不稳” | `knowledge/gongwen-doc-types`, `knowledge/gongwen-format-basic`, `knowledge/gongwen-title-patterns`, `knowledge/gongwen-word-usage` |
| 技法层 | “不会检索、不会搭框架、不会扩写或精简” | `method/gongwen-search-deep`, `method/gongwen-structure-build`, `method/gongwen-content-expand`, `method/gongwen-edit-reduce` |

## 工作流程

### Step 1 - 定义用户卡点

优先问清：
- 是写不出来，还是写出来不好
- 是不会判断题目，还是不会组织内容
- 是方法问题，还是长期训练问题
- 用户想得到一条建议，还是完整训练方案

### Step 2 - 选择最短诊断链

#### 链路 A：接任务就卡住

`concept/gongwen-active-vs-passive` -> `concept/gongwen-subjective-activation` -> `method/gongwen-search-deep`

#### 链路 B：写出来像流水账

`knowledge/gongwen-problem-analysis` -> `concept/gongwen-virtual-real-combination` -> `method/gongwen-structure-build`

#### 链路 C：格式和文种老出错

`knowledge/gongwen-doc-types` -> `knowledge/gongwen-format-basic` -> `knowledge/gongwen-word-usage`

#### 链路 D：长期没有质变

`concept/gongwen-quantity-to-quality` -> `method/gongwen-proofread` -> `method/gongwen-material-transform`

### Step 3 - 输出顾问结果

默认输出应包含：
- 对卡点的判断
- 对应的技能路径
- 1 到 3 个立即可做的动作
- 如适合长期训练，给出一周或一月练习建议

## 角色内路由原则

1. 先判断卡点层级，再进入最短诊断链，不把顾问入口写成泛用分流器
2. 用户问“有没有更好的方法”时，优先选择更专用的 method 技能做讲解
3. 用户只是在情绪上抗拒任务时，优先激活 concept，不要急着堆细枝末节
4. 用户目标是“提升站位”时，优先 `concept/gongwen-virtual-real-combination` + `method/gongwen-perspective-take`

## 回退策略

1. 问题表达很模糊  
回退到 `knowledge/gongwen-problem-analysis`

2. 用户卡点跨越多层  
按“concept -> knowledge -> method”顺序串联，避免一上来堆技巧

3. 进入后发现任务其实不是诊断模式  
停止本入口处理，交回 `entry/gongwen-facade-hub` 重新分流

4. 用户需要把顾问建议落成正式稿  
结束顾问分析后，把后续交付需求交回 `entry/gongwen-facade-hub`

## 示例

### 示例 1

用户说：
"为什么我写工作总结总像记流水账？"

路由：
`knowledge/gongwen-problem-analysis` -> `concept/gongwen-virtual-real-combination` -> `method/gongwen-structure-build`

### 示例 2

用户说：
"我每次接到新材料都想等别人给模板，这正常吗？"

路由：
`concept/gongwen-active-vs-passive` -> `concept/gongwen-subjective-activation`

### 示例 3

用户说：
"怎么系统练公文写作，别让我一直原地打转？"

路由：
`concept/gongwen-quantity-to-quality` -> `method/gongwen-proofread` -> `method/gongwen-material-transform`
