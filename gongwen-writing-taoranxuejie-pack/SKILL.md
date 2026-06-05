---
name: "gongwen-writing-taoranxuejie-pack"
description: "公文写作的技能包。适用于公文写作、思维顾问、角色扮演。 能力包括：直接起草和修改公文、诊断公文写作问题、模拟领导或前辈做批注与预演。用户提到通知、报告、讲话稿、总结、审题、格式、标题、站位、虚实结合、扮演领导批材料等需求时调用。"
---

# 公文写作技能包

## 目标

将《从零开始学公文写作》和《公文写作大手笔》中的核心方法整合成一个可路由、可串联、可回退的技能包。

本技能包优先解决四类任务：
- 作为 facade 统一入口，先做意图诊断与路由
- 直接完成公文写作任务
- 作为公文写作思维顾问做诊断和辅导
- 作为领导、前辈或审稿人做角色扮演式反馈

## 何时使用

当用户出现以下目标时，优先考虑本技能包：
- 需要写通知、报告、总结、讲话稿、述职、调研等公文或类公文材料
- 已经有材料初稿，希望优化结构、标题、句子、站位、篇幅或格式
- 不知道该用什么文种，不知道如何审题、搭框架、找素材或展开内容
- 想知道为什么自己写了很多却进步慢，或想建立公文写作训练路径
- 需要模拟领导、办公室主任、老秘书对材料做批注、提问或预演

不适合直接使用本技能包的场景：
- 文学创作、品牌文案、纯营销软文
- 明确要求违法违规、公文造假或虚构事实的写作任务
- 与组织写作无关的私人情绪宣泄

## 核心职责

本技能包负责：
- 作为技能包级 facade，在需求混杂或表述模糊时先做统一分流
- 识别用户当前更需要写作执行、方法辅导，还是角色扮演反馈
- 在 `concept`、`knowledge`、`method` 三类技能之间建立稳定路由
- 以“先判断任务，再选择文种和结构，再生成内容，最后复核”的链路组织写作
- 在需要时把概念类技能作为前置激活器，解决抗拒、站位、高度、练习路径等问题
- 在多技能都可处理时，优先选择更专用、更接近用户目标输出的技能

本技能包不负责：
- 替用户伪造事实、掩盖问题或生成违规材料
- 把体制内公文规范生硬套用到所有组织语境
- 在信息严重不足时强行输出看似完整但无法落地的成稿

## 显式触发词

为便于用户使用和提高路由准确性，优先识别以下语言信号。

### Facade 总入口触发词

强触发词：
- “这个材料怎么处理”
- “先帮我看看该怎么做”
- “我这个公文任务该怎么推进”
- “既想改又想学”
- “先帮我判断一下，再告诉我怎么写”

弱触发词：
- “看看这份稿子”
- “这个公文任务怎么弄”
- “我不知道先做什么”
- “这个材料卡住了”

适用说明：
- 当用户需求混杂、意图不完整、同时包含写作和咨询时，优先走 `entry/gongwen-facade-hub`

### 秘书入口触发词

强触发词：
- “帮我写一份通知 / 报告 / 总结 / 发言稿”
- “把这篇材料改一下”
- “帮我扩写 / 压缩 / 润色”
- “整理成正式公文”
- “出一版能直接交的稿子”

弱触发词：
- “给我个框架”
- “顺手改成正式一点”
- “帮我补齐内容”
- “帮我收口定稿”

排除触发词：
- “为什么我总写不好”
- “你扮演领导批一下”
- “值不值得学公文写作”

### 顾问入口触发词

强触发词：
- “为什么我总写不好”
- “这个材料问题出在哪”
- “怎么提升站位 / 高度 / 结构”
- “怎么系统练公文写作”
- “讲话稿和总结有什么区别”

弱触发词：
- “有没有更好的方法”
- “我总觉得不对劲”
- “怎么才能更像样”
- “审题总跑偏怎么办”

排除触发词：
- “帮我直接写”
- “你扮演领导”
- “给我一版能直接发的稿子”

### 角色扮演入口触发词

强触发词：
- “你扮演领导 / 办公室主任 / 老秘书”
- “模拟汇报 / 会前预演”
- “从上级视角挑毛病”
- “帮我批一下这份稿子”
- “预判领导会怎么问”

弱触发词：
- “看看领导会不会满意”
- “像主任一样给我提意见”
- “帮我演练一下”
- “从对方视角看”

排除触发词：
- “帮我直接写一版”
- “为什么我总写不好”
- “这个文种到底怎么选”

## 子技能分类

### Facade 入口

| 子技能 | 主要职责 | 适用问题 |
|---|---|---|
| `entry/gongwen-facade-hub` | 作为统一总入口先做意图诊断，再分流到秘书、顾问、角色扮演或专用技能 | “这个材料怎么处理”“先看看该怎么做”“既想改又想学” |

### 角色入口

| 子技能 | 主要职责 | 适用问题 |
|---|---|---|
| `entry/gongwen-secretary-hub` | 作为秘书直接完成起草、改写、扩写、压缩和定稿 | “帮我写一份通知”“把这份讲话稿改成熟一点” |
| `entry/gongwen-advisor-hub` | 作为思维顾问诊断写作卡点并给出方法路径 | “为什么我总写不好”“这个材料站位不够怎么办” |
| `entry/gongwen-roleplay-hub` | 作为领导、前辈、办公室主任等角色做批注、预演和沟通模拟 | “你当领导给我批一下”“模拟汇报场景” |

### Concept - 概念类

这些技能优先用于校正心态、提升站位、建立长期写作坐标。

| 子技能 | 主要职责 | 适用问题 |
|---|---|---|
| `concept/gongwen-active-vs-passive` | 识别抗拒思维，转向主动检索 | “我没写过，不知道怎么下手” |
| `concept/gongwen-subjective-activation` | 激活主观能动性，避免等靠要 | “领导没讲细，我就不会干” |
| `concept/gongwen-quantity-to-quality` | 把重复写作转成刻意练习 | “写了很多还是没进步” |
| `concept/gongwen-writing-value` | 建立写作价值感和长期投入意愿 | “学公文写作值不值得” |
| `concept/gongwen-virtual-real-combination` | 处理材料的高度、站位和虚实比例 | “文章太虚”“像流水账” |

### Knowledge - 知识类

这些技能优先用于确定规则、文种和基础判断标准。

| 子技能 | 主要职责 | 适用问题 |
|---|---|---|
| `knowledge/gongwen-doc-types` | 判断该用什么文种 | “到底该写通知还是通报” |
| `knowledge/gongwen-format-basic` | 检查格式、字体、标题、版式等规范 | “格式哪里不对” |
| `knowledge/gongwen-problem-analysis` | 做审题、拆题和需求诊断 | “领导到底想要什么” |
| `knowledge/gongwen-title-patterns` | 提供常见标题和小标题模式 | “小标题怎么排” |
| `knowledge/gongwen-word-usage` | 判断字词轻重、身份匹配和表达准确性 | “这个词能不能用” |

### Method - 方法类

这些技能直接落到写作动作，负责生成、优化和校验。

| 子技能 | 主要职责 | 适用问题 |
|---|---|---|
| `method/gongwen-search-deep` | 深度检索高质量参考素材 | “帮我找类似表述” |
| `method/gongwen-title-design` | 设计主标题和小标题 | “标题不好看也不稳” |
| `method/gongwen-sentence-write` | 把句子写得准确、简洁、利落 | “这句话太绕了” |
| `method/gongwen-structure-build` | 先搭框架再动笔 | “整篇结构乱了” |
| `method/gongwen-content-expand` | 在结构明确后扩句、补句、拔高 | “内容太空，字数不够” |
| `method/gongwen-edit-reduce` | 做删改和压缩，保留核心信息 | “太啰嗦，帮我精简” |
| `method/gongwen-proofread` | 做格式、逻辑、措辞、错漏复核 | “帮我做最后检查” |
| `method/gongwen-perspective-take` | 用领导/上级视角修正站位 | “这段站位不够高” |
| `method/gongwen-material-transform` | 把同一素材改写成不同写法 | “一个素材怎么换着用” |
| `method/gongwen-speech-draft` | 专门处理领导讲话稿 | “帮我起草会议讲话稿” |

## 路由原则

### 第一层路由：先过 facade 入口

当用户表述混杂、任务不完整或目标不明确时，优先走：
`entry/gongwen-facade-hub`

facade 负责判断是：
- 直接分流到三角色入口
- 直达某个高专用度子技能
- 先补齐任务信息，再决定后续链路

### 第二层路由：再选角色入口

按用户最想得到的输出结果选择总入口：

| 用户目标特征 | 首选入口 |
|---|---|
| 直接要成稿、改稿、扩稿、压稿、补稿 | `entry/gongwen-secretary-hub` |
| 想学方法、做诊断、找问题、建训练路径 | `entry/gongwen-advisor-hub` |
| 想让你扮演领导、前辈、办公室主任批注或预演 | `entry/gongwen-roleplay-hub` |

这三个角色入口默认只处理已分流完成的任务，不再承担 facade 的总分流职责。

### 第三层路由：再选三类子技能

在角色入口内部，按以下规则继续选择：

1. 先判断任务，再进入写法  
如果用户连文种、对象、目的都没讲清，先走 `knowledge`，再走 `method`。

2. 先概念，后方法  
如果用户的根本问题是抗拒、站位、价值感不足或长期停滞，先走 `concept`，再进入具体写法。

3. 专用技能优先  
讲话稿优先 `method/gongwen-speech-draft`，而不是泛化地只用 `method/gongwen-structure-build`。

4. 直接产出更接近目标的技能优先  
用户要“改短”，优先 `method/gongwen-edit-reduce`；用户要“检查”，优先 `method/gongwen-proofread`。

5. 输入材料更匹配的技能优先  
给的是原稿，优先优化和校验类技能；给的是模糊任务，优先文种和审题类技能。

## 多技能串联策略

### 链路 A：直接写一份公文

推荐顺序：
`entry/gongwen-facade-hub` -> `knowledge/gongwen-problem-analysis` -> `knowledge/gongwen-doc-types` -> `method/gongwen-search-deep` -> `method/gongwen-structure-build` -> `method/gongwen-content-expand` -> `method/gongwen-proofread`

适用情境：
- 从零起草通知、报告、总结、汇报材料
- 用户只给了任务，没有现成成稿

### 链路 B：把材料写得更像领导稿

推荐顺序：
`entry/gongwen-facade-hub` -> `method/gongwen-perspective-take` -> `concept/gongwen-virtual-real-combination` -> `method/gongwen-sentence-write` -> `method/gongwen-proofread`

适用情境：
- 站位不够
- 高度不足
- 语言过平、过实或过散

### 链路 C：讲话稿专项

推荐顺序：
`entry/gongwen-facade-hub` -> `knowledge/gongwen-problem-analysis` -> `method/gongwen-speech-draft` -> `method/gongwen-content-expand` -> `method/gongwen-proofread`

适用情境：
- 领导会议讲话稿
- 汇报发言提纲
- 需要区分讲话稿和普通材料的写法

### 链路 D：长期提升写作能力

推荐顺序：
`entry/gongwen-facade-hub` -> `concept/gongwen-active-vs-passive` -> `concept/gongwen-subjective-activation` -> `concept/gongwen-quantity-to-quality` -> `method/gongwen-search-deep` -> `method/gongwen-proofread`

适用情境：
- 经常不会下手
- 写得多但进步慢
- 想建立稳定训练机制

### 链路 E：角色扮演批材料

推荐顺序：
`entry/gongwen-facade-hub` -> `method/gongwen-perspective-take` -> `method/gongwen-proofread` -> `concept/gongwen-virtual-real-combination`

适用情境：
- 领导批注
- 模拟办公室主任挑错
- 会前预演和汇报 rehearsal

## 失败与回退策略

当无法稳定选择技能时，按以下方式回退：

1. 文种不明，回退到 `knowledge/gongwen-doc-types`  
先确定写什么，再谈怎么写。

2. 任务理解不清，回退到 `knowledge/gongwen-problem-analysis`  
先问清对象、目的、场景、时限，再进入写作。

3. 需求模糊混杂，先回退到 `entry/gongwen-facade-hub`  
先做统一诊断，再决定是秘书、顾问还是角色扮演。

4. 用户只说“写不好”，回退到 `entry/gongwen-advisor-hub`  
先诊断瓶颈是心态、格式、结构、标题还是站位。

5. 用户只要“领导视角”，回退到 `entry/gongwen-roleplay-hub`  
不要直接进入泛写作链，要先确定扮演对象和反馈标准。

6. 信息严重不足时，停止假装成稿  
明确说明缺少关键信息，并给出最小补充清单。

## 示例

### 示例 1

用户说：
"帮我写一份关于防汛值班的通知，下午就要发。"

路由：
`entry/gongwen-facade-hub` -> `entry/gongwen-secretary-hub`

追加链路：
`knowledge/gongwen-doc-types` -> `method/gongwen-structure-build` -> `method/gongwen-proofread`

### 示例 2

用户说：
"我每次写总结都像流水账，领导老说没高度。"

路由：
`entry/gongwen-facade-hub` -> `entry/gongwen-advisor-hub`

追加链路：
`concept/gongwen-virtual-real-combination` -> `method/gongwen-perspective-take` -> `method/gongwen-structure-build`

### 示例 3

用户说：
"你扮演办公室主任，帮我批一下这份讲话稿，看看哪里会被领导打回。"

路由：
`entry/gongwen-facade-hub` -> `entry/gongwen-roleplay-hub`

追加链路：
`method/gongwen-perspective-take` -> `method/gongwen-proofread` -> `method/gongwen-speech-draft`

## 需求拆解摘要

这个技能包围绕三项核心角色构建：
- 秘书：以交付成稿为目标，强调效率、完整性和规范性
- 思维顾问：以诊断卡点和提升能力为目标，强调框架、方法和训练路径
- 角色扮演：以领导视角、前辈视角和场景反馈为目标，强调站位、预演和批注

为了稳定覆盖这几类任务，技能包保留 `concept`、`knowledge`、`method` 三层结构，并新增一个 facade 级统一总入口和三个角色总控入口，用于完成“先总分流，再专用处理”的两层路由。
