---
name: gongwen-facade-hub
description: |
  何时调用: 用户需求混合、表述模糊、既想写又想学又想演练，或只抛出公文相关问题时优先调用。
  何时不调用: 用户已明确说"扮演领导批一下"、"帮我直接写一份通知"、"为什么我总写不好"。
  关键trigger: "这个材料怎么处理"、"先帮我看看该怎么做"、"既想改又想学"、"先判断再告诉我怎么写"
source: 公文写作技能包·陶然学姐
tags: [facade入口, 统一路由, 意图诊断, 技能编排, 总控]
related_skills:
  - slug: entry/gongwen-secretary-hub
    relation: composes-with
  - slug: entry/gongwen-advisor-hub
    relation: composes-with
  - slug: entry/gongwen-roleplay-hub
    relation: composes-with
---

# 公文写作统一总入口

## 目标

把用户一句自然语言里的真实目标快速诊断成最合适的处理模式，并路由到最专用的入口或子技能。

这个 facade 入口解决的问题不是“代替所有技能”，而是：
- 在用户表达混杂时先做稳定分流
- 在用户表述不完整时先补齐任务关键信息
- 在需求已经非常明确时直接命中专用技能，减少绕路

## 何时使用

以下情境优先激活本入口：
- 用户只说“帮我弄个公文”“这个材料怎么处理”“看看这份稿子”
- 用户同时混合了写作、咨询、批注、预演等多个目标
- 用户没有明确说自己要秘书、顾问还是角色扮演
- 用户只抛出一个局部问题，如标题、格式、站位、讲话稿、字数、措辞，但你还不确定是否要走总链路

以下情境不必优先使用本入口：
- 用户已经明确说“扮演领导批一下”
- 用户已经明确说“帮我直接写一份通知”
- 用户已经明确说“为什么我总写不好”

这些情况可以直接进入对应角色入口或专用技能。

## 显式触发词

### 强触发词

- “这个材料怎么处理”
- “先帮我看看该怎么做”
- “我这个公文任务该怎么推进”
- “既想改又想学”
- “先帮我判断一下，再告诉我怎么写”
- “我不知道先走哪一步”

### 弱触发词

- “看看这份稿子”
- “这个公文任务怎么弄”
- “我不知道先做什么”
- “这个材料卡住了”
- “先帮我理一下思路”

### 排除触发词

- “帮我直接写一份通知 / 报告 / 总结”
- “为什么我总写不好”
- “你扮演领导 / 办公室主任批一下”
- “这个词能不能用”

### 路由备注

- 一旦命中“怎么处理、怎么推进、先看看怎么做、既想改又想学、先判断再写”等混合表达，优先进入本入口
- 如果用户目标已经非常明确，facade 应尽量直达专用技能或单一角色入口，不要额外绕路

## Facade 诊断模型

本入口先判断用户需求属于哪一类：

| 模式 | 典型信号 | 首选去向 |
|---|---|---|
| 交付模式 | 写、改、润色、扩写、压缩、定稿 | `entry/gongwen-secretary-hub` |
| 诊断模式 | 为什么、怎么提升、怎么练、哪里有问题 | `entry/gongwen-advisor-hub` |
| 演练模式 | 扮演、模拟、预演、领导怎么看 | `entry/gongwen-roleplay-hub` |
| 规则模式 | 文种、格式、标题、用词、审题 | 对应 `knowledge` 或 `method` 专用技能 |
| 混合模式 | 既要判断又要改，既要批注又要代写 | 先主目标，后追加子链 |

## 路由原则

### 第一层：先定主目标

按用户最想先得到的结果排序：

1. 先要结果，再要解释  
优先 `entry/gongwen-secretary-hub`

2. 先要判断，再要方法  
优先 `entry/gongwen-advisor-hub`

3. 先要上级视角，再要修改  
优先 `entry/gongwen-roleplay-hub`

4. 只问一个明确小问题  
直达专用技能，不必强行走三角色入口

### 第二层：高专用度直达

如果用户问题已经极其明确，直接命中最专用技能：

| 用户问题特征 | 直达技能 |
|---|---|
| “该用通知还是通报” | `knowledge/gongwen-doc-types` |
| “标题怎么起 / 小标题怎么排” | `method/gongwen-title-design` 或 `knowledge/gongwen-title-patterns` |
| “这个词能不能用” | `knowledge/gongwen-word-usage` |
| “格式哪里不对” | `knowledge/gongwen-format-basic` |
| “领导讲话稿怎么写” | `method/gongwen-speech-draft` |
| “怎么搭结构” | `method/gongwen-structure-build` |
| “帮我找参考素材” | `method/gongwen-search-deep` |
| “帮我精简到 800 字” | `method/gongwen-edit-reduce` |
| “这段站位不够” | `method/gongwen-perspective-take` |
| “文章太虚 / 太实 / 像流水账” | `concept/gongwen-virtual-real-combination` |

### 第三层：混合需求拆链

如果用户一次说了两个以上目标，按以下顺序拆链：

1. 先定主任务  
判断是“写”为主，还是“学”为主，还是“演”为主。

2. 再定附属任务  
把另一个目标作为追加链，而不是并列启动多个入口。

3. 专用技能优先于泛用入口  
例如“讲话稿 + 领导视角”优先 `method/gongwen-speech-draft`，再追加 `entry/gongwen-roleplay-hub`。

## 工作流程

### Step 1 - 识别输入形态

先判断用户给的是哪类输入：
- 只有一句目标
- 有原稿但没说怎么处理
- 只有场景，没有文种
- 同时包含写作和反馈要求

### Step 2 - 快速判别五种模式

#### A. 交付模式

信号：
- “帮我写”
- “改一下”
- “润色一下”
- “压缩一下”

路由：
`entry/gongwen-secretary-hub`

#### B. 诊断模式

信号：
- “为什么总写不好”
- “怎么才能提高”
- “这个问题出在哪”

路由：
`entry/gongwen-advisor-hub`

#### C. 演练模式

信号：
- “扮演领导”
- “模拟汇报”
- “从上级视角看”

路由：
`entry/gongwen-roleplay-hub`

#### D. 规则模式

信号：
- “该用什么文种”
- “格式怎么设”
- “这个词准不准”
- “标题怎么写”

路由：
直达相关 `knowledge` / `method` 技能

#### E. 混合模式

信号：
- “先帮我判断文种，再直接起草”
- “先扮演领导批一下，再帮我改”
- “先告诉我问题，再给我一版改写”

路由：
先主链，后追加链

## 推荐混合链

### 链路 A：先诊断再改稿

`entry/gongwen-advisor-hub` -> `entry/gongwen-secretary-hub`

适用：
- 用户既想知道问题在哪里，又希望顺手改成更好的版本

### 链路 B：先批注再代写

`entry/gongwen-roleplay-hub` -> `entry/gongwen-secretary-hub`

适用：
- 用户先要领导视角，再要你按反馈改稿

### 链路 C：先定规则再起草

`knowledge/gongwen-doc-types` -> `knowledge/gongwen-problem-analysis` -> `entry/gongwen-secretary-hub`

适用：
- 用户只给工作场景，还没定文种

### 链路 D：先直达专用技能，再补顾问解释

`method/gongwen-speech-draft` -> `entry/gongwen-advisor-hub`

适用：
- 用户先解决眼前任务，再想理解这类材料怎么写

## 回退策略

1. 无法判断主目标  
回退到 `knowledge/gongwen-problem-analysis`，先问清对象、场景、目的、时限。

2. 用户一句话既像写作又像咨询  
优先看动词：写/改/压/润色 -> 交付；为什么/怎么提升 -> 诊断。

3. 用户只说“看看这份材料”  
优先判断是否更像审稿反馈；默认先走 `entry/gongwen-roleplay-hub` 或 `method/gongwen-proofread`。

4. 用户明确局部问题但又含糊  
优先专用技能，再视情况补角色入口。

5. 信息不足无法安全成稿  
不要硬写，转为最小补充清单。

## 示例

### 示例 1

用户说：
"这个材料怎么处理，你帮我看看。"

路由：
先用 facade 判断输入不清，再优先看是否是审稿场景。

默认去向：
`entry/gongwen-roleplay-hub` 或 `method/gongwen-proofread`

### 示例 2

用户说：
"先帮我判断这该用什么文种，再给我起个框架。"

路由：
`knowledge/gongwen-doc-types` -> `method/gongwen-structure-build`

### 示例 3

用户说：
"你先扮演领导批一下，然后直接帮我改成能交的版本。"

路由：
`entry/gongwen-roleplay-hub` -> `entry/gongwen-secretary-hub`

### 示例 4

用户说：
"为什么我写总结总是没高度？顺便告诉我怎么改。"

路由：
`entry/gongwen-advisor-hub` -> `entry/gongwen-secretary-hub`
