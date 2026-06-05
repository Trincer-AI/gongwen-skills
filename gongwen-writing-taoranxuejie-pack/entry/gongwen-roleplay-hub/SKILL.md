---
name: gongwen-roleplay-hub
description: |
  何时调用: facade或上游已确认用户需要角色扮演式批注、追问、预演和场景模拟时。
  何时不调用: 用户只想直接拿到成稿、不需要角色反馈的场景；纯理论方法讲解场景；只做知识解释的场景。
  关键trigger: "你扮演领导批一下"、"模拟办公室主任给我提意见"、"帮我预演汇报"、"从上级视角挑毛病"
source: 公文写作技能包·陶然学姐
tags: [角色扮演入口, 领导视角, 审稿, 预演, 技能编排]
related_skills:
  - slug: method/gongwen-perspective-take
    relation: depends-on
  - slug: method/gongwen-proofread
    relation: composes-with
  - slug: concept/gongwen-virtual-real-combination
    relation: composes-with
---

# 角色扮演总控入口

## 目标

把抽象的“领导会怎么看”“前辈会怎么批”“汇报现场会被问什么”转成具体的反馈、批注和预演流程。

默认前提：
- facade 或上游路由已经确认当前任务属于“演练模式”
- 当前入口只负责角色设定、批注、追问和预演
- 如发现任务其实更像直接代写或纯方法顾问，只把任务退回 facade，不在本入口内部改判角色

## 何时使用

当用户出现以下需求时优先激活：
- 想让你扮演领导或办公室主任看材料
- 想模拟会前汇报、面对面沟通、稿件退回场景
- 想得到更强势、更挑剔、更接近真实上级的反馈
- 想站在对方身份上预判问题点和发问点

## 显式触发词

### 强触发词

- “你扮演领导 / 办公室主任 / 老秘书”
- “模拟汇报 / 会前预演”
- “从上级视角挑毛病”
- “帮我批一下这份稿子”
- “预判领导会怎么问”
- “像主任一样给我提意见”

### 弱触发词

- “看看领导会不会满意”
- “从对方视角看”
- “帮我演练一下”
- “像前辈一样给我挑错”
- “我想知道会不会被打回”

### 排除触发词

- “帮我直接写一版”
- “为什么我总写不好”
- “这个文种怎么选”
- “怎么系统练公文写作”

### 路由备注

- 一旦命中“扮演、模拟、预演、批一下、从领导视角看”等表达，优先进入本入口
- 如果同时出现“先批一下再帮我改”，优先保留本入口做第一段反馈，后续交由 `entry/gongwen-facade-hub` 决定是否进入交付链

## 角色路由

| 扮演对象 | 关注重点 | 首选技能 |
|---|---|---|
| 领导 | 站位、轻重缓急、是否可讲 | `method/gongwen-perspective-take`, `concept/gongwen-virtual-real-combination` |
| 办公室主任/审稿人 | 格式、完整性、逻辑、错误率 | `method/gongwen-proofread`, `knowledge/gongwen-format-basic` |
| 老秘书/笔杆子 | 标题、框架、句子、节奏 | `method/gongwen-structure-build`, `method/gongwen-title-design`, `method/gongwen-sentence-write` |
| 会议汇报对象 | 讲话要点、追问点、时间控制 | `method/gongwen-speech-draft`, `method/gongwen-proofread` |

## 工作流程

### Step 1 - 明确角色和场景

至少确认：
- 你要我扮演谁
- 场景是什么
- 是看全文、提纲，还是口头汇报
- 你更想要挑错、压问，还是温和指导

### Step 2 - 选择反馈链

#### 链路 A：领导批稿

`method/gongwen-perspective-take` -> `concept/gongwen-virtual-real-combination` -> `method/gongwen-proofread`

#### 链路 B：办公室主任挑错

`knowledge/gongwen-format-basic` -> `method/gongwen-proofread`

#### 链路 C：老秘书带改

`method/gongwen-structure-build` -> `method/gongwen-title-design` -> `method/gongwen-sentence-write`

#### 链路 D：会议汇报预演

`method/gongwen-speech-draft` -> `method/gongwen-perspective-take` -> `method/gongwen-proofread`

### Step 3 - 输出角色反馈

默认输出应包含：
- 角色身份设定
- 该角色最在意的 3 到 5 个问题
- 针对原稿或场景的批注/追问
- 对应的修改建议

如用户要求“更像真实领导”，可以更聚焦：
- 站位是否越位或失位
- 内容是否空泛
- 是否抓住主线和重点
- 是否存在明显格式和细节错误

## 角色内路由原则

1. 先确认扮演对象，再进入对应反馈链，不把角色入口写成总分流器
2. 如果没有原稿，优先做“预演提纲”而不是虚构完整场景细节
3. 角色反馈以该角色最关心的问题排序，不主动扩展成完整代写任务
4. 如需补充长期方法解释，只作为结尾建议，不在本入口内改切其他角色

## 回退策略

1. 用户没说扮演谁  
先提供可选角色：领导 / 办公室主任 / 老秘书 / 汇报对象

2. 用户没有材料  
回退为“场景预演 + 关键发问点”模式

3. 进入后发现任务其实不是演练模式  
停止本入口处理，交回 `entry/gongwen-facade-hub` 重新分流

4. 用户既要批注又要改稿  
先完成角色反馈，再把后续交付需求交回 `entry/gongwen-facade-hub`

5. 用户给出的场景明显不是公文写作  
停止强行路由，说明本入口更适合材料批注与汇报预演

## 示例

### 示例 1

用户说：
"你扮演办公室主任，帮我看一下这份通知有什么硬伤。"

路由：
`knowledge/gongwen-format-basic` -> `method/gongwen-proofread`

### 示例 2

用户说：
"假设你是分管领导，看看我这篇总结哪里站位不够。"

路由：
`method/gongwen-perspective-take` -> `concept/gongwen-virtual-real-combination`

### 示例 3

用户说：
"模拟一下我向领导汇报这份讲话稿时，他可能会追问什么。"

路由：
`method/gongwen-speech-draft` -> `method/gongwen-perspective-take` -> `method/gongwen-proofread`
