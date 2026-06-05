# professional-gongwen-writing-skills - 技能索引

> **技能包名称**: professional-gongwen-writing-skills
> **来源**: 公文摆渡技能包（63技能）+ 陶然学姐技能包（24技能）
> **用途**: 公文写作全场景覆盖，包含统一Facade入口、三角色体系、66+专项技能
> **创建时间**: 2026-05-25

---

## 总览

本技能包包含 **66+ 个技能**，整合自两个技能包：

| 来源 | 数量 | 说明 |
|---|---|---|
| **陶然学姐技能包** | 24 | 提供Facade统一入口、三角色体系、concept/knowledge/method分层 |
| **公文摆渡技能包** | 63 | 提供丰富的专项技能（述职/调研/马哲/亮点挖掘等） |
| **合计** | **87** | 陶然学姐24个 + 公文摆渡63个 |

### 整合架构说明

```
professional-gongwen-writing-skills/
├── entry/          # 入口层（陶然学姐4技能）：Facade + 秘书 + 顾问 + 角色扮演
├── concept/        # 概念层（陶然学姐5技能）：心态/站位/价值感
├── knowledge/      # 知识层（陶然5技能 + 公文摆渡3格式专项 = 8技能）
├── method/         # 方法层（陶然学姐10技能）：写作执行方法
└── skills-gwbd/    # 公牛摆渡专项（63技能）：场景化/框架/亮点/语言等专项
```

---

## 入口层（Entry）

### Facade 总入口

| 技能名 | 入口定位 | 关键 trigger |
|---|---|---|
| [gongwen-facade-hub](entry/gongwen-facade-hub/SKILL.md) | 统一总入口，先做意图诊断，再路由到角色入口或专用技能 | "这个材料怎么处理"、"先看看该怎么做"、"既想改又想学" |

### 角色入口

| 技能名 | 入口定位 | 关键 trigger |
|---|---|---|
| [gongwen-secretary-hub](entry/gongwen-secretary-hub/SKILL.md) | 秘书总控入口，直接交付写作结果 | "帮我写一份通知"、"把这篇总结改一下"、"给我出版讲话稿" |
| [gongwen-advisor-hub](entry/gongwen-advisor-hub/SKILL.md) | 思维顾问总控入口，诊断卡点并给方法路径 | "为什么我总写不好"、"这个材料怎么提升站位"、"怎么练公文写作" |
| [gongwen-roleplay-hub](entry/gongwen-roleplay-hub/SKILL.md) | 角色扮演总控入口，模拟领导/前辈/办公室主任反馈 | "你扮演领导批一下"、"模拟汇报场景"、"从上级视角提意见" |

### 快速选择口诀

- 不知道先找谁：先用 `gongwen-facade-hub`
- 直接要成稿：优先 `gongwen-secretary-hub`
- 先问原因和方法：优先 `gongwen-advisor-hub`
- 先要领导或前辈视角：优先 `gongwen-roleplay-hub`

---

## 概念层（Concept）

| 技能名 | 一句话描述 | 关键 trigger |
|---|---|---|
| [gongwen-active-vs-passive](concept/gongwen-active-vs-passive/SKILL.md) | 主动思维 vs 等靠要，处理接任务时的抗拒 | "我不会写"、"等别人给模板" |
| [gongwen-subjective-activation](concept/gongwen-subjective-activation/SKILL.md) | 主观能动性激活，推动自己先动起来 | "我没写过所以做不了"、"不知道该从哪查" |
| [gongwen-quantity-to-quality](concept/gongwen-quantity-to-quality/SKILL.md) | 量变到质变，建立刻意练习机制 | "写了很多还是没进步"、"怎么提升" |
| [gongwen-writing-value](concept/gongwen-writing-value/SKILL.md) | 写作的价值创造，建立长期投入感 | "写材料有什么用"、"值不值得学" |
| [gongwen-virtual-real-combination](concept/gongwen-virtual-real-combination/SKILL.md) | 虚实结合，解决高度不足或流水账 | "太虚了"、"太实了没高度" |

---

## 知识层（Knowledge）

| 技能名 | 一句话描述 | 关键 trigger |
|---|---|---|
| [gongwen-doc-types](knowledge/gongwen-doc-types/SKILL.md) | 判断文种及其适用场景 | "该用什么文种"、"通知和通报差别是什么" |
| [gongwen-format-basic](knowledge/gongwen-format-basic/SKILL.md) | 提供格式、字体、版式基础知识 | "格式怎么设"、"字号有要求吗" |
| [gongwen-problem-analysis](knowledge/gongwen-problem-analysis/SKILL.md) | 四看审题法，识别领导真实需求 | "这题怎么审"、"领导想要什么" |
| [gongwen-title-patterns](knowledge/gongwen-title-patterns/SKILL.md) | 标题模式库和小标题排布参考 | "标题格式有哪些套路"、"这组小标题怎么排" |
| [gongwen-word-usage](knowledge/gongwen-word-usage/SKILL.md) | 易错字词与身份匹配表达 | "这个词能不能用"、"措辞准不准" |
| [gongwen-guifan](skills-gwbd/gongwen-guifan/SKILL.md) | 公文规范性三避坑：附体行文/标题回行/主送机关 | "格式哪里不对"、"规范性问题" |
| [zhici-geshi-guifan](skills-gwbd/zhici-geshi-guifan/SKILL.md) | 致辞格式规范：标题/时间/讲话人/称谓 | "致辞格式怎么写" |
| [shuliang-zhengque-shiyong](skills-gwbd/shuliang-zhengque-shiyong/SKILL.md) | 数量正确使用：量词/数字/连接号/时间分隔符 | "数字用法有没有问题" |

---

## 方法层（Method）

| 技能名 | 一句话描述 | 关键 trigger |
|---|---|---|
| [gongwen-search-deep](method/gongwen-search-deep/SKILL.md) | 深度检索法，帮用户找高质量参考素材 | "帮我找参考"、"怎么检索类似表述" |
| [gongwen-title-design](method/gongwen-title-design/SKILL.md) | 标题设计法，解决主标题和小标题问题 | "标题怎么写"、"这个小标题别扭" |
| [gongwen-sentence-write](method/gongwen-sentence-write/SKILL.md) | 句子撰写方法，解决绕、散、空的问题 | "这句话太拗口"、"怎么写得利落" |
| [gongwen-structure-build](method/gongwen-structure-build/SKILL.md) | 结构构建法，先搭框架再写正文 | "结构怎么搭"、"框架乱了" |
| [gongwen-content-expand](method/gongwen-content-expand/SKILL.md) | 内容扩充法，补句、扩句、拔高 | "字数不够"、"内容太空" |
| [gongwen-edit-reduce](method/gongwen-edit-reduce/SKILL.md) | 减法写作技巧，删掉啰嗦和重复 | "帮我压缩一下"、"太长了" |
| [gongwen-proofread](method/gongwen-proofread/SKILL.md) | 复核技巧，做终稿前检查 | "帮我看看有没有问题"、"做一遍终审" |
| [gongwen-perspective-take](method/gongwen-perspective-take/SKILL.md) | 换位技巧，从领导或上级视角修站位 | "站位不够"、"不像领导稿" |
| [gongwen-material-transform](method/gongwen-material-transform/SKILL.md) | 材料转化技巧，一个素材多种写法 | "这段还能怎么写"、"换个表述方式" |
| [gongwen-speech-draft](method/gongwen-speech-draft/SKILL.md) | 讲话稿专项技能，处理会议发言和领导讲话 | "写讲话稿"、"领导发言提纲怎么搭" |

---

## 公牛摆渡专项技能（skills-gwbd）

### T1-T5：场景化写作与语言风格

| 技能名 | 一句话描述 | 来源视频 |
|---|---|---|
| [changjing-xiezuo](skills-gwbd/changjing-xiezuo/SKILL.md) | 场景化写作法：忘记特殊文体，用正常人逻辑说话 | 视频55 |
| [yuti-xuanze](skills-gwbd/yuti-xuanze/SKILL.md) | 口语vs书面语体选择：政策文件用书面，讲话稿用口语 | 视频37 |
| [huibao-changjinghua](skills-gwbd/huibao-changjinghua/SKILL.md) | 工作汇报场景化：让领导听得懂、能决策 | 视频17 |

### T6-T10：工作汇报与信息报送

| 技能名 | 一句话描述 | 来源视频 |
|---|---|---|
| [xinxi-baosong-liu-tiaolu](skills-gwbd/xinxi-baosong-liu-tiaolu/SKILL.md) | 信息报送六条路径：从领导讲话解锁选题方向 | 视频20 |
| [mubiao-daoxiang-yu-jieguo-daoxiang](skills-gwbd/mubiao-daoxiang-yu-jieguo-daoxiang/SKILL.md) | 目标导向与结果导向：规划用目标导向，总结用结果导向 | 视频24 |
| [gongzuo-zongjie-kuangjia](skills-gwbd/gongzuo-zongjie-kuangjia/SKILL.md) | 工作总结框架搭建：索引性+完整性 | 视频39、41 |
| [zhongdian-gongzuo-huohua](skills-gwbd/zhongdian-gongzuo-huohua/SKILL.md) | 重点工作谋划四方面：上级考核/落实/试点/国家战略 | 视频23 |
| [wuzheng-xinxi-xuanti](skills-gwbd/wuzheng-xinxi-xuanti/SKILL.md) | 政务信息选题六类：六类交叉选题生成 | 视频40 |

### T11-T15：论证与结构

| 技能名 | 一句话描述 | 来源视频 |
|---|---|---|
| [tongxin-yuan-lunzheng](skills-gwbd/tongxin-yuan-lunzheng/SKILL.md) | 同心圆论证法：普遍性→特殊性层层聚焦 | 视频11 |
| [liti-hua-lunzheng](skills-gwbd/liti-hua-lunzheng/SKILL.md) | 立体化论证法：引入第三对象使论证更立体 | 视频11 |
| [zongfen-pingxing-tuijin](skills-gwbd/zongfen-pingxing-tuijin/SKILL.md) | 总分平行递进结构法：总分抓点+平行抓线+递进抓面 | 视频47 |
| [xiao-qiedao-da-changjing](skills-gwbd/xiao-qiedao-da-changjing/SKILL.md) | 小切口大场景法：从小事件写出大文章 | 视频16 |
| [dianxianmian-goujian](skills-gwbd/dianxianmian-goujian/SKILL.md) | 点线面构建法：三种类型让结构清晰 | 视频29 |
| [jiaodian-qianzhi](skills-gwbd/jiaodian-qianzhi/SKILL.md) | 焦点前置框架：五维度拆解出发点/主线/手段/成效/保障 | 视频41 |
| [jiaodian-houzhi](skills-gwbd/jiaodian-houzhi/SKILL.md) | 焦点后置框架：以成效为焦点，按影响对象分类 | 视频41 |
| [erji-biaoti](skills-gwbd/erji-biaoti/SKILL.md) | 二级标题六种逻辑维度：时序/事项/主体/区域/对象/成效 | 视频78 |
| [wenti-daoxiang-siwei](skills-gwbd/wenti-daoxiang-siwei/SKILL.md) | 问题导向式思维：把问题写成工作的着力点 | 视频44 |
| [hongguan-weiguan-fenxi](skills-gwbd/hongguan-weiguan-fenxi/SKILL.md) | 宏观微观分析法：供给侧+人民获得双维度 | 视频35 |
| [changduan-qihua-fenceng](skills-gwbd/changduan-qihua-fenceng/SKILL.md) | 长短期谋划分层：战略层与执行层的架构分层 | 视频92、93 |

### T16-T20：亮点挖掘与句式

| 技能名 | 一句话描述 | 来源视频 |
|---|---|---|
| [sigong-liangan-faxin](skills-gwbd/sigong-liangan-faxin/SKILL.md) | 四角度挖掘工作亮点：问题/创新/要素/战略四角度 | 视频60 |
| [chengqi-ju-xiezuo](skills-gwbd/chengqi-ju-xiezuo/SKILL.md) | 承启句写作：标题→承启句→细分点三级闭环 | 视频61 |
| [wuchou-dagui](skills-gwbd/wuchou-dagui/SKILL.md) | 五抽屉归纳法：用五套框架合并同类项 | 视频62 |
| [juxiang-daodian-jushi](skills-gwbd/juxiang-daodian-jushi/SKILL.md) | 句式模板运用：问题导向/持续推进/全链条 | 视频25 |
| [yixiaojianda-jushi](skills-gwbd/yixiaojianda-jushi/SKILL.md) | 以小见大句式：三个模板让文章有深度 | 视频27 |
| [xiaoci-dianjing](skills-gwbd/xiaoci-dianjing/SKILL.md) | 小词点睛：三组小词让语言亮眼 | 视频28 |
| [yinyv-zhuangzhonggan](skills-gwbd/yinyv-zhuangzhonggan/SKILL.md) | 音律庄重感：四个音节为主的庄重语言 | 视频43 |
| [zhanwei-zhunque-yongci](skills-gwbd/zhanwei-zhunque-yongci/SKILL.md) | 站位准确用词：不同层级用词匹配 | 视频14 |
| [zerenxing-gongwen](skills-gwbd/zerenxing-gongwen/SKILL.md) | 责任型公文金三角：主体明确/价值共生/突破担当 | 视频70 |
| [houban-juhua-luoji](skills-gwbd/houban-juhua-luoji/SKILL.md) | 后半句话六种逻辑：六种逻辑路径延展句子 | 视频72、73 |
| [chengqi-jualiangbian](skills-gwbd/chengqi-jualiangbian/SKILL.md) | 承启句量变质变：主导量变+关键机制+直接产物 | 视频102 |

### T21-T25：述职报告与调研

| 技能名 | 一句话描述 | 来源视频 |
|---|---|---|
| [shuzhi-jiegouhua](skills-gwbd/shuzhi-jiegouhua/SKILL.md) | 述职结构化三化：标签化/数据化/框架化 | 视频94 |
| [shuzhi-gushihua](skills-gwbd/shuzhi-gushihua/SKILL.md) | 述职故事化：以我为主独立负责/问题重构/价值创造 | 视频95 |
| [shuzhi-baogao-fenqu](skills-gwbd/shuzhi-baogao-fenqu/SKILL.md) | 述职报告与工作总结区分：述职写"我"，总结写"事" | 视频88 |
| [hexin-gongneng-qudong](skills-gwbd/hexin-gongneng-qudong/SKILL.md) | 核心功能驱动框架：战略→功能→举措→成效 | 视频90 |
| [wunian-niandu-chayi](skills-gwbd/wunian-niandu-chayi/SKILL.md) | 五年vs年度差异化：四维区分战略/架构/侧重/呈现 | 视频91 |
| [diaoyan-xinxin](skills-gwbd/diaoyan-xinxin/SKILL.md) | 调研报告结构性新信息：重新定义单元/提炼原理/建立刻度 | 视频111 |
| [tuoxu-xiangshi](skills-gwbd/tuoxu-xiangshi/SKILL.md) | 脱虚向实三步：理念动词→任务动词 | 视频81、82 |
| [liangdian-chengxu](skills-gwbd/liangdian-chengxu/SKILL.md) | 亮点深化三模型：辩证呈现/系统集成/时空纵深 | 视频83、84 |

### T26-T30：思维框架与战略

| 技能名 | 一句话描述 | 来源视频 |
|---|---|---|
| [maxue-renshilun](skills-gwbd/maxue-renshilun/SKILL.md) | 马哲认识论写作：获得→检验→应用认识 | 视频96 |
| [maxue-shengchan-guanxi](skills-gwbd/maxue-shengchan-guanxi/SKILL.md) | 马哲生产力生产关系：建规则理利益优组织固关系 | 视频97、98 |
| [biaoti-sanduanashi](skills-gwbd/biaoti-sanduanashi/SKILL.md) | 标题三段式：感性具体→理性本质→实践变革 | 视频99 |
| [yanshu-sanqiao](skills-gwbd/yanshu-sanqiao/SKILL.md) | 演讲时空表达：时空交织/宏微结合/虚实递进 | 视频100 |
| [dongbin-qunji](skills-gwbd/dongbin-qunji/SKILL.md) | 动宾集群写作：主客二分，六层客体化 | 视频101 |
| [shiti-biaoshu](skills-gwbd/shiti-biaoshu/SKILL.md) | 实质性表述追问：操作→功能→目的→战略层面 | 视频103 |
| [tuogao-siwei](skills-gwbd/tuogao-siwei/SKILL.md) | 脱稿思维汇报：直截了当/领导逻辑/一针见血 | 视频105 |
| [ansuofu-juzhi](skills-gwbd/ansuofu-juzhi/SKILL.md) | 安索夫矩阵举措：深耕/拓展/创新/开新局 | 视频106 |
| [gongzuo-duxiang](skills-gwbd/gongzuo-duxiang/SKILL.md) | 工作分类矩阵：高成长×高掌控=代表作 | 视频107 |
| [san-ji-lingdao-jianghua-luoji](skills-gwbd/san-ji-lingdao-jianghua-luoji/SKILL.md) | 三级领导讲话逻辑：是什么/为什么/怎样做降维 | 视频33 |
| [dairu-shixiang-siwei](skills-gwbd/dairu-shixiang-siwei/SKILL.md) | 代入式写作：让讲话像领导本人讲的 | 视频38 |
| [wuzhong-siwei-zonghe-yunyong](skills-gwbd/wuzhong-siwei-zonghe-yunyong/SKILL.md) | 五种思维综合运用：代入+沉浸+延伸+链条+层级 | 视频38 |

### T31-T35：格式与转换

| 技能名 | 一句话描述 | 来源视频 |
|---|---|---|
| [sanwei-cailiao-xiefa](skills-gwbd/sanwei-cailiao-xiefa/SKILL.md) | 三维材料写法：通讯稿/简报/信息的格式选择与转换 | 视频68 |
| [gongzuo-xinxi-gai](skills-gwbd/gongzuo-xinxi-gai/SKILL.md) | 工作信息改写：工作总结→工作信息的格式改写 | 视频80 |
| [cailiao-pingmian](skills-gwbd/cailiao-pingmian/SKILL.md) | 材料修改平面化：垂直结构→平面清单的转换 | 视频108 |
| [gongwen-sanyaoshi](skills-gwbd/gongwen-sanyaoshi/SKILL.md) | 公文三钥匙：文种定调/个性点睛/底线守稳 | 视频74 |
| [zuotan-hui-fayan](skills-gwbd/zuotan-hui-fayan/SKILL.md) | 座谈会发言四方法：根据领导类型选择方法 | 视频75、76 |
| [luoji-zazong-zhenduan](skills-gwbd/luoji-zazong-zhenduan/SKILL.md) | 逻辑杂糅诊断：检查因果与条件混用 | 视频32 |
| [lilun-wenzhang](skills-gwbd/lilun-wenzhang/SKILL.md) | 理论文章写作方向区分：学者向vs领导向 | 视频42 |
| [xitong-fenxi](skills-gwbd/xitong-fenxi/SKILL.md) | 系统分析法：走进决策者关注的问题 | 视频19 |
| [jiaoliu-xuexi](skills-gwbd/jiaoliu-xuexi/SKILL.md) | 交流研讨学习思维：材料完整性检查 | 视频109 |
| [cuoshi-chengxiao-ju](skills-gwbd/cuoshi-chengxiao-ju/SKILL.md) | 举措成效句边界：定系统→划边界→问成效 | 视频104 |

---

## 推荐路径

### 新人入门路径

1. `gongwen-facade-hub` - 统一诊断与总分流
2. `gongwen-format-basic` - 掌握格式规范
3. `changjing-xiezuo` - 场景化写作入门
4. `gongwen-structure-build` - 结构构建
5. `gongwen-proofread` - 学会检查和收口

### 进阶提升路径

1. `gongwen-search-deep` - 深度检索
2. `sigong-liangan-faxin` - 亮点挖掘
3. `gongwen-perspective-take` - 换位技巧
4. `gongwen-virtual-real-combination` - 虚实结合
5. `gongwen-speech-draft` - 讲话稿专项

### 高手突破路径

1. `maxue-renshilun` - 马哲认识论
2. `gongwen-quantity-to-quality` - 量变到质变
3. `gongwen-roleplay-hub` - 角色扮演做高强度复盘
4. `hexin-gongneng-qudong` - 核心功能驱动框架
5. `shuzhi-jiegouhua` + `shuzhi-gushihua` - 述职系统

---

## 与原技能的对应关系（迁移指南）

| 原技能包 | 新技能包对应路径 | 说明 |
|---|---|---|
| taoran entry/* | entry/ | 保持原名和结构 |
| taoran concept/* | concept/ | 保持原名和结构 |
| taoran knowledge/* | knowledge/ | 保持原名 + gwbd格式类3个 |
| taoran method/* | method/ | 保持原名和结构 |
| gwbd 所有63个技能 | skills-gwbd/ | 保持原名和结构 |

---

## 审计信息

- **创建时间**: 2026-05-25
- **来源技能包**: 公牛摆渡技能包（63技能）+ 陶然学姐技能包（24技能）
- **整合后技能总数**: 66+
- **入口设计**: facade统一总入口 + 3角色入口（秘书/顾问/角色扮演）
- **维护者**: Claude Code + skill-group-merger