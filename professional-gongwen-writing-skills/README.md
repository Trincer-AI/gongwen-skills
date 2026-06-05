# professional-gongwen-writing-skills

公文写作技能包——整合公文摆渡（63专项技能）与陶然学姐（24技能含Facade+角色体系），共 **66+个技能**，覆盖场景化写作、框架搭建、亮点挖掘、虚实结合、格式规范、审题诊断等公文写作全链路。

## 技能包概览

| 指标 | 说明 |
|---|---|
| **总技能数** | 66+ |
| **来源** | 公文摆渡技能包（63技能）+ 陶然学姐技能包（24技能） |
| **架构** | Facade统一入口 + 三角色体系 + 专项技能 |
| **入口设计** | 1个Facade总入口 + 3个角色入口（秘书/顾问/角色扮演） |

## 能力列表

### 入口层（Entry）

- **gongwen-facade-hub** — 统一总入口，先做意图诊断再分流
- **gongwen-secretary-hub** — 秘书入口，直接交付写作结果
- **gongwen-advisor-hub** — 思维顾问入口，诊断卡点并给方法路径
- **gongwen-roleplay-hub** — 角色扮演入口，模拟领导/前辈批注与预演

### 概念层（Concept）

- **gongwen-active-vs-passive** — 主动思维 vs 等靠要
- **gongwen-subjective-activation** — 主观能动性激活
- **gongwen-quantity-to-quality** — 量变到质变
- **gongwen-writing-value** — 写作的价值创造
- **gongwen-virtual-real-combination** — 虚实结合

### 知识层（Knowledge）

- **gongwen-doc-types** — 15种法定文种判断
- **gongwen-format-basic** — 公文格式基础
- **gongwen-problem-analysis** — 四看审题法
- **gongwen-title-patterns** — 标题模式库
- **gongwen-word-usage** — 易错字词辨析
- **gongwen-guifan** — 公文规范性三避坑
- **zhici-geshi-guifan** — 致辞格式规范
- **shuliang-zhengque-shiyong** — 数量正确使用

### 方法层（Method）

- **gongwen-search-deep** — 深度检索法
- **gongwen-title-design** — 标题设计法
- **gongwen-sentence-write** — 句子撰写方法
- **gongwen-structure-build** — 结构构建法
- **gongwen-content-expand** — 内容扩充法
- **gongwen-edit-reduce** — 减法写作技巧
- **gongwen-proofread** — 复核技巧
- **gongwen-perspective-take** — 换位技巧
- **gongwen-material-transform** — 材料转化技巧
- **gongwen-speech-draft** — 领导讲话稿撰写

### 公牛摆渡专项技能（skills-gwbd）

63个专项技能，完整覆盖：
- **场景化写作**（changjing-xiezuo, yuti-xuanze, huibao-changjinghua）
- **结构框架**（tongxin-yuan-lunzheng, liti-hua-lunzheng, zongfen-pingxing-tuijin, jiaodian-qianzhi/houzhi）
- **亮点挖掘**（sigong-liangan-faxin, liangdian-chengxu, hexin-gongneng-qudong）
- **述职报告**（shuzhi-jiegouhua, shuzhi-gushihua, shuzhi-baogao-fenqu）
- **调研报告**（diaoyan-xinxin, xitong-fenxi）
- **马哲思维**（maxue-renshilun, maxue-shengchan-guanxi）
- **语言优化**（yinyv-zhuangzhonggan, xiaoci-dianjing, zhanwei-zhunque-yongci）
- **格式规范**（gongwen-guifan, zhici-geshi-guifan, shuliang-zhengque-shiyong）
- ...（共63个）

## 快速开始

### 触发词快速索引

| 场景 | 优先触发词 |
|---|---|
| 不知道怎么处理 | "这个材料怎么处理"、"先看看该怎么做" |
| 直接要成稿 | "帮我写一份通知"、"把这篇总结改一下" |
| 先问原因方法 | "为什么我总写不好"、"怎么提升站位" |
| 要领导视角 | "你扮演领导批一下"、"模拟汇报场景" |
| 太虚/不接地气 | "太虚了"、"不接地气"、"不知道用什么语气" |
| 述职报告 | "年终述职"、"述职报告怎么写" |
| 调研报告 | "调研报告不知道怎么写" |
| 不知道文种 | "该用什么文种"、"通知和通报差别" |

### 典型使用链路

**链路A：公文写作完整链路（从零开始）**
```
gongwen-facade-hub → secretary-hub → problem-analysis → doc-types → structure-build → changjing-xiezuo → sigong-liangan-faxin → proofread
```

**链路B：述职报告专项**
```
gongwen-facade-hub → shuzhi-baogao-fenqu → shuzhi-jiegouhua → shuzhi-gushihua → biaoti-sanduanashi
```

**链路C：站位提升**
```
gongwen-facade-hub → advisor-hub → virtual-real-combination → tuoxu-xiangshi → perspective-take → proofread
```

**链路D：角色扮演批材料**
```
gongwen-facade-hub → roleplay-hub → perspective-take → proofread → feedback
```

## 路由原则

1. **需求混杂/不明确** → `gongwen-facade-hub`（统一诊断与分流）
2. **直接要成稿/改稿** → `gongwen-secretary-hub`
3. **问方法/诊断** → `gongwen-advisor-hub`
4. **要领导视角批注** → `gongwen-roleplay-hub`
5. **gwbd专项场景**（述职/调研/马哲等）→ 直接路由到对应gwbd专项技能

## 与原技能的对应关系

| 原技能包 | 新技能包对应路径 |
|---|---|
| taoran entry/* | entry/ |
| taoran concept/* | concept/ |
| taoran knowledge/* | knowledge/ |
| taoran method/* | method/ |
| gwbd 所有63个技能 | skills-gwbd/ |

## 文件结构

```
professional-gongwen-writing-skills/
├── SKILL.md              # 根级总控文档
├── INDEX.md              # 技能索引总览
├── README.md             # 本文档
├── entry/                # 入口层（陶然学姐4技能）
├── concept/              # 概念层（陶然学姐5技能）
├── knowledge/            # 知识层（陶然5技能 + gwbd 3格式专项）
├── method/               # 方法层（陶然学姐10技能）
└── skills-gwbd/          # 公牛摆渡专项技能（63个）
```

## 审计信息

- **创建时间**: 2026-05-25
- **整合工具**: skill-group-merger
- **维护者**: Claude Code