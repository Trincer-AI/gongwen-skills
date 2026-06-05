---
name: gongwen-secretary-hub
description: |
  何时调用: facade或上游已确认用户需要直接交付公文结果时，包括起草、改写、扩写、压缩、润色和定稿。
  何时不调用: 纯方法教学、单纯讨论职业意义、需要角色扮演反馈、没有任何事实基础却要求虚构正式材料的场景。
  关键trigger: "帮我写一份通知"、"把这篇总结改成熟一点"、"出一版讲话稿"、"帮我压缩成800字"、"整理成正式材料"
source: 公文写作技能包·陶然学姐
tags: [秘书入口, 公文起草, 改稿, 定稿, 技能编排]
related_skills:
  - slug: knowledge/gongwen-problem-analysis
    relation: depends-on
  - slug: knowledge/gongwen-doc-types
    relation: depends-on
  - slug: method/gongwen-proofread
    relation: composes-with
---

# 秘书总控入口

## 目标

把用户的写作任务转成一条稳定的执行链，直接交付可用的公文结果。

默认前提：
- facade 或上游路由已经确认当前任务属于“交付模式”
- 当前入口不负责再判断是否应该切去顾问或角色扮演
- 如发现任务并非交付模式，只把任务退回 facade，不在本入口内部改判角色

这个入口优先处理：
- 从零起草一篇公文
- 根据初稿做修改、扩写、压缩、提炼和定稿
- 根据会议、活动、汇报、总结等任务生成正式材料

## 何时使用

当用户出现以下语言信号时优先激活：
- “帮我写一份通知/报告/总结/发言稿”
- “把这篇材料改一下，下午就要交”
- “这段太空了，帮我扩到 1500 字”
- “把这份讲话稿压缩到 5 分钟口径”
- “帮我按正式公文风格重写”

不适合使用的场景：
- 用户只是问“为什么写不好”而不是要你代写
- 用户只想让你扮演领导批注，而不是直接产出成稿
- 缺少事实基础且要求编造情况、数据、成效

## 显式触发词

### 强触发词

- “帮我写一份通知 / 报告 / 总结 / 讲话稿”
- “把这篇材料改成熟一点 / 正式一点”
- “帮我压缩到 800 字 / 5 分钟口径”
- “帮我扩写这段内容”
- “给我一版能直接交的稿子”
- “整理成正式公文格式”

### 弱触发词

- “给我个提纲”
- “先出个框架”
- “顺手润色一下”
- “帮我收口”
- “把这段改顺一点”

### 排除触发词

- “为什么我总写不好”
- “你扮演领导 / 办公室主任看一下”
- “值不值得学公文写作”
- “这个词该不该用”

### 路由备注

- 一旦命中“直接写、直接改、直接交付、压缩、扩写、润色成稿”等表达，优先进入本入口
- 如果同时出现“先批一下再改”“先告诉我问题再写”，优先交回 `entry/gongwen-facade-hub` 由 facade 拆主次链

## 角色内路由

### 先判断交付任务状态

| 任务特征 | 首选技能 |
|---|---|
| 连文种都不明确 | `knowledge/gongwen-doc-types` |
| 题目和要求含糊 | `knowledge/gongwen-problem-analysis` |
| 需要讲话稿 | `method/gongwen-speech-draft` |
| 需要普通材料框架 | `method/gongwen-structure-build` |
| 需要找素材和参考 | `method/gongwen-search-deep` |
| 需要补内容 | `method/gongwen-content-expand` |
| 需要压缩精简 | `method/gongwen-edit-reduce` |
| 需要调整站位 | `method/gongwen-perspective-take` |
| 需要终稿检查 | `method/gongwen-proofread` |

### 专用技能优先级

1. 讲话稿优先 `method/gongwen-speech-draft`
2. 站位问题优先 `method/gongwen-perspective-take`
3. 标题问题优先 `method/gongwen-title-design`
4. 句子问题优先 `method/gongwen-sentence-write`
5. 终稿检查优先 `method/gongwen-proofread`

## 工作流程

### Step 1 - 补齐最小任务信息

至少确认：
- 写给谁看
- 用在什么场合
- 属于什么文种
- 重点要表达什么
- 截止时间和篇幅要求

如果以上信息缺失，先调用：
`knowledge/gongwen-problem-analysis` -> `knowledge/gongwen-doc-types`

### Step 2 - 选择主链路

#### 链路 A：从零起草

`knowledge/gongwen-problem-analysis` -> `knowledge/gongwen-doc-types` -> `method/gongwen-search-deep` -> `method/gongwen-structure-build` -> `method/gongwen-content-expand` -> `method/gongwen-proofread`

#### 链路 B：已有初稿要改

`method/gongwen-structure-build` -> `method/gongwen-sentence-write` -> `method/gongwen-edit-reduce` -> `method/gongwen-proofread`

#### 链路 C：讲话稿专项

`knowledge/gongwen-problem-analysis` -> `method/gongwen-speech-draft` -> `method/gongwen-perspective-take` -> `method/gongwen-proofread`

#### 链路 D：标题和用词专项

`knowledge/gongwen-title-patterns` -> `method/gongwen-title-design` -> `knowledge/gongwen-word-usage`

### Step 3 - 成稿输出规范

默认输出应包含：
- 对文种或场景的简短确认
- 可直接使用的正文或提纲
- 如信息不足，列出最小补充清单
- 如为改稿，说明主要修改方向

### Step 4 - 终稿复核

定稿前优先检查：
- 文种是否匹配
- 标题和层次是否规范
- 句子是否简洁
- 虚实比例和站位是否合适
- 是否存在错字、漏项、逻辑断裂

## 回退策略

1. 交付信息缺失  
回退到 `knowledge/gongwen-problem-analysis`

2. 用户只给主题，没有素材  
回退到 `method/gongwen-search-deep`

3. 用户说“像领导讲话一点”  
追加 `method/gongwen-perspective-take` 和 `concept/gongwen-virtual-real-combination`

4. 用户说“先不要写全文，只给框架”  
只走到 `method/gongwen-structure-build`

5. 进入后发现任务其实不是交付模式  
停止本入口处理，交回 `entry/gongwen-facade-hub` 重新分流

6. 用户要求不合规内容  
停止执行，转为提示不能编造或违规处理

## 示例

### 示例 1

用户说：
"帮我起草一份端午节期间值班通知。"

路由：
`knowledge/gongwen-doc-types` -> `method/gongwen-structure-build` -> `method/gongwen-proofread`

### 示例 2

用户说：
"这篇半年总结太像流水账，帮我改得正式一点。"

路由：
`method/gongwen-structure-build` -> `method/gongwen-perspective-take` -> `method/gongwen-sentence-write` -> `method/gongwen-proofread`

### 示例 3

用户说：
"领导下午要在安全生产会上讲话，先给我出个提纲。"

路由：
`method/gongwen-speech-draft`
