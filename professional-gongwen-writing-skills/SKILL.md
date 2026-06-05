---
name: professional-gongwen-writing-skills
description: 公文写作技能包——整合公文摆渡（63专项技能）与陶然学姐（24技能含Facade+角色体系），共66个技能覆盖场景化写作、框架搭建、亮点挖掘、虚实结合、格式规范、审题诊断等公文写作全链路。触发词："公文怎么处理"、"写材料怎么推进"、"既想改又想学"
version: 1.0
created_at: 2026-05-25
source: gwbd-pack(63技能) + taoran-pack(24技能)
tags: [公文写作, 技能包合并, professional]
---

# professional-gongwen-writing-skills

## 目标

整合公文摆渡技能包（63专项技能）与陶然学姐技能包（Facade+角色体系），形成覆盖全面、路由清晰、能力互补的公文写作技能包。

核心解决以下问题：
- 不知道用什么语气写（场景化问题）
- 不知道如何组织结构（框架问题）
- 不知道如何挖掘亮点（深化问题）
- 不知道如何用词精准（语言问题）
- 不知道格式规范（合规问题）
- 不知道该选什么文种、怎么审题（认知问题）
- 需要领导视角批注或预演（角色扮演）
- 需要诊断写作卡点并规划训练路径（思维顾问）

## 何时使用

- "领导让我写个汇报，不知道怎么下笔"
- "写完了领导说太虚、不接地气"
- "工作做了很多但总结写不出来亮点"
- "不知道用口语还是书面语"
- "写材料时被说格式不规范"
- "需要写致辞、讲话稿、述职报告等特定文种"
- "这个材料怎么处理/先帮我看看该怎么做"
- "既想改又想学"
- "你扮演领导批一下这份稿子"
- "为什么我总写不好/怎么提升站位"

不适合直接使用本技能包的场景：
- 文学创作、品牌文案、纯营销软文
- 明确要求违法违规、公文造假或虚构事实的写作任务
- 与组织写作无关的私人情绪宣泄

## 核心职责

本技能包负责将用户的写作需求（模糊的、初步的、有线索的）转化为高质量的公文文本，涵盖：

1. **统一入口与分流**：通过 facade 统一入口先做意图诊断，再路由到最合适的处理模式
2. **秘书直写**：直接完成起草、改写、扩写、压缩和定稿
3. **思维顾问**：诊断写作卡点并给出方法路径
4. **角色扮演**：模拟领导、前辈或办公室主任做批注与反馈
5. **专项技能执行**：场景化写作、结构框架、亮点挖掘、语言优化、格式校验等

## 技能包结构

本技能包由两套技能体系整合而成，目录结构如下：

```
professional-gongwen-writing-skills/
├── entry/                    # 入口层（来自陶然学姐，4个技能）
│   ├── gongwen-facade-hub/   # 统一总入口
│   ├── gongwen-secretary-hub/ # 秘书入口
│   ├── gongwen-advisor-hub/   # 思维顾问入口
│   └── gongwen-roleplay-hub/  # 角色扮演入口
├── concept/                  # 概念层（来自陶然学姐，5个技能）
│   ├── gongwen-active-vs-passive/
│   ├── gongwen-subjective-activation/
│   ├── gongwen-quantity-to-quality/
│   ├── gongwen-writing-value/
│   └── gongwen-virtual-real-combination/
├── knowledge/                # 知识层（来自陶然学姐5个 + 公牛摆渡3个格式专项）
│   ├── gongwen-doc-types/
│   ├── gongwen-format-basic/
│   ├── gongwen-problem-analysis/
│   ├── gongwen-title-patterns/
│   ├── gongwen-word-usage/
│   ├── gongwen-guifan/           # 公牛摆渡格式专项
│   ├── zhici-geshi-guifan/       # 公牛摆渡格式专项
│   └── shuliang-zhengque-shiyong/ # 公牛摆渡格式专项
├── method/                   # 方法层（来自陶然学姐，10个技能）
│   ├── gongwen-search-deep/
│   ├── gongwen-title-design/
│   ├── gongwen-sentence-write/
│   ├── gongwen-structure-build/
│   ├── gongwen-content-expand/
│   ├── gongwen-edit-reduce/
│   ├── gongwen-proofread/
│   ├── gongwen-perspective-take/
│   ├── gongwen-material-transform/
│   └── gongwen-speech-draft/
└── skills-gwbd/              # 公牛摆渡专项技能（63个）
    ├── changjing-xiezuo/     # 场景化写作法
    ├── yuti-xuanze/          # 口语vs书面语体选择
    ├── huibao-changjinghua/   # 工作汇报场景化
    ├── sigong-liangan-faxin/   # 四角度挖掘工作亮点
    ├── shuzhi-jiegouhua/      # 述职结构化三化
    ├── shuzhi-gushihua/       # 述职故事化
    ├── diaoyan-xinxin/        # 调研报告结构性新信息
    ├── maxue-renshilun/       # 马哲认识论写作
    ├── tuoxu-xiangshi/        # 脱虚向实三步法
    ├── gongwen-sanyaoshi/     # 公文三钥匙
    └── ...（共63个专项技能）
```

## 路由原则

### 第一层：先过 facade 入口

当用户表述混杂、任务不完整或目标不明确时，优先走：
`entry/gongwen-facade-hub`

facade 负责判断是：
- 直接分流到三角色入口（秘书/顾问/角色扮演）
- 直达某个高专用度子技能
- 先补齐任务信息，再决定后续链路

### 第二层：按主目标选角色入口

| 用户目标特征 | 首选入口 |
|---|---|
| 直接要成稿、改稿、扩稿、压稿、补稿 | `entry/gongwen-secretary-hub` |
| 想学方法、做诊断、找问题、建训练路径 | `entry/gongwen-advisor-hub` |
| 想扮演领导、前辈、办公室主任批注或预演 | `entry/gongwen-roleplay-hub` |

### 第三层：gwbd 专项技能路由

当用户需求涉及以下特定场景时，直接路由到对应的 `skills-gwbd/` 技能：

| 场景 | 推荐技能 |
|---|---|
| "太虚"/"不接地气"/"不知道用什么语气" | `skills-gwbd/changjing-xiezuo` |
| "年终述职"/"述职报告怎么写" | `skills-gwbd/shuzhi-jiegouhua` + `skills-gwbd/shuzhi-gushihua` |
| "调研报告不知道怎么写" | `skills-gwbd/diaoyan-xinxin` |
| "马哲思维写材料"/"认识论怎么用" | `skills-gwbd/maxue-renshilun` |
| "太虚了"/"理念太多任务太少" | `skills-gwbd/tuoxu-xiangshi` |
| "做了很多但写不出亮点" | `skills-gwbd/sigong-liangan-faxin` |
| "不知道选什么文种" | `skills-gwbd/gongwen-sanyaoshi` |
| "信息报送不知道从哪里切入" | `skills-gwbd/xinxi-baosong-liu-tiaolu` |

## 多技能串联策略

### 链路A：公文写作完整链路（从零开始）

```
gongwen-facade-hub → secretary-hub → gongwen-problem-analysis → gongwen-doc-types → gongwen-search-deep → gongwen-structure-build → changjing-xiezuo → sigong-liangan-faxin → proofread
```

适用：从零起草通知、报告、总结、汇报材料

### 链路B：述职报告专项

```
gongwen-facade-hub → shuzhi-baogao-fenqu → shuzhi-jiegouhua → shuzhi-gushihua → biaoti-sanduanashi
```

适用：年终述职、干部述职

### 链路C：调研报告专项

```
gongwen-facade-hub → xitong-fenxi → diaoyan-xinxin → tongxin-yuan-lunzheng → proofread
```

适用：调研报告、工作调研

### 链路D：讲话稿专项

```
gongwen-facade-hub → gongwen-problem-analysis → gongwen-speech-draft → dairu-shixiang-siwei → yinyv-zhuangzhonggan → proofread
```

适用：领导会议讲话稿、汇报发言提纲

### 链路E：站位提升（虚实结合）

```
gongwen-facade-hub → advisor-hub → gongwen-virtual-real-combination → tuoxu-xiangshi → gongwen-perspective-take → proofread
```

适用：站位不够、高度不足、语言过平

### 链路F：角色扮演批材料

```
gongwen-facade-hub → roleplay-hub → gongwen-perspective-take → proofread → feedback
```

适用：领导批注、模拟办公室主任挑错、会前预演

## 失败与回退策略

| 失败节点 | 回退策略 |
|---|---|
| facade 后不知如何选择 | 回退到 secretary-hub（默认交付模式） |
| 框架搭好后内容空洞 | 回退到 sigong-liangan-faxin 重新挖掘亮点 |
| 语言写出后不够庄重 | 回退到 yinyv-zhuangzhonggan 重新调整音律 |
| 格式校验发现问题 | 回退到对应文种的生成类技能重新起草 |
| 文种不明 | 回退到 `knowledge/gongwen-doc-types` 先确定文种 |
| 任务理解不清 | 回退到 `knowledge/gongwen-problem-analysis` 先问清对象、目的、场景 |
| 信息严重不足时 | 停止假装成稿，明确说明缺少关键信息 |

## 示例

### 示例1：用户说"领导让我写个工作汇报，不知道怎么下笔"

1. **激活**：`gongwen-facade-hub` → 路由到 `gongwen-secretary-hub`
2. **判断**：`yuti-xuanze`（口语书面语选择）
3. **框架**：`gongwen-structure-build` 或 `jiaodian-qianzhi`
4. **场景化**：`changjing-xiezuo`（场景化写作）
5. **亮点**：`sigong-liangan-faxin`
6. **优化**：`xiaoci-dianjing` + `yinyv-zhuangzhonggan`
7. **校验**：`gongwen-proofread`

### 示例2：用户说"年终总结被领导说太平淡"

1. **激活**：`shuzhi-jiegouhua`（述职结构化）或 `sigong-liangan-faxin`（亮点挖掘）
2. **深化**：`liangdian-chengxu`（亮点深化三模型）
3. **语言**：`yinyv-zhuangzhonggan`（音律庄重）
4. **标题**：`biaoti-sanduanashi`（标题三段式）

### 示例3：用户说"你扮演领导批一下这份讲话稿"

1. **激活**：`gongwen-facade-hub` → `gongwen-roleplay-hub`
2. **批注**：`gongwen-perspective-take`
3. **校验**：`gongwen-proofread`
4. **反馈**：给出领导视角的批注和改进建议

### 示例4：用户说"为什么我写总结总是没高度？"

1. **激活**：`gongwen-facade-hub` → `gongwen-advisor-hub`
2. **诊断**：`gongwen-virtual-real-combination`（虚实结合）
3. **换位**：`gongwen-perspective-take`（站位提升）
4. **框架**：`gongwen-structure-build`

## 审计信息

- **技能包构建时间**: 2026-05-25
- **来源**: 公牛摆渡技能包（63技能）+ 陶然学姐技能包（24技能）
- **整合后技能总数**: 66+
- **入口设计**: facade统一总入口 + 3角色入口（秘书/顾问/角色扮演）
- **维护者**: Claude Code + skill-group-merger