# Wiki Schema

## 领域定位

本 Wiki 构建**社会科学的知识百科全书**——不是分类目录，不是理论摘要卡片，
而是一条**流动的思想长河**。

### 核心愿景

> 像站在一条河流面前：你可以在任何一个时间点扎进去，
> 顺着脉络向上追溯思想的源头，向下追踪理论的演变与对话。
> 每一个概念都不是孤岛——你能看到它从哪里来、回应了谁、被谁修正、
> 又如何影响了后来的思潮。

### 三层深度

| 层级 | 内容 | 页面类型 |
|------|------|----------|
| **地表** | 理论/范式的核心主张、代表人物、历史定位 | paradigm, theory, discipline |
| **地质** | 理论产生的历史情境、回应的时代问题、与其他理论的对话与冲突 | genealogy, debate |
| **化石** | 具体的方法论细节、研究工具的操作逻辑、经典研究的案例拆解 | methodology, case-study |

### 涵盖范围

- **时间跨度**：从古希腊社会思想到当代前沿（不限于"现代"）
- **空间跨度**：西方主流 + 非西方传统（中国社会思想、拉美依附理论、非洲后殖民思想等）
- **学派跨度**：不限于法兰克福学派/芝加哥学派，覆盖全球主要学术传统
- **学科跨度**：社会学、人类学、政治学、经济学、心理学、传播学、教育学、人口学、犯罪学等

### 非核心但必备

- **应用场景**：社会科学在社会生活中的实际应用（政策制定、社会评估、市场研究、组织发展）
- **前沿动态**：计算社会科学、AI+社科、数字民族志、行为经济学等交叉领域
- **职业发展**：社科学生的学术路径、业界去向、核心能力培养

## 文件命名规范

- 中文或英文均可，连字符连接，不加空格
- 示例：`实证主义范式.md`、`田野调查方法论.md`、`马克思-韦伯-涂尔干对话.md`
- YAML frontmatter 开头

## Frontmatter 模板

```yaml
---
title: 页面标题
created: YYYY-MM-DD
updated: YYYY-MM-DD
type: paradigm | theory | methodology | genealogy | discipline | person | debate | case-study | application | career | timeline
era: 古典 | 现代早期 | 现代 | 当代  # 所属时代
tags: [从下方标签分类中选择]
sources: [raw/...]
confidence: high | medium | low
contested: false | true
preceded_by: [前一阶段页面]   # 河流上游
followed_by: [后一阶段页面]    # 河流下游
responds_to: [回应的理论/问题]  # 对话关系
---
```

- `era`：帮助读者在历史长河中定位
- `preceded_by / followed_by`：构建时间流（非强制，有则填）
- `responds_to`：标注理论对话关系——这是"河流"感的关键

## 页面类型详解

### paradigm（范式）
不只是"是什么"，而是：
- 产生的历史情境——为什么在那个时代、那个地方出现？
- 与之前范式的断裂在哪里？
- 内部的分化与张力
- 对后续研究的实际影响（而非只是哲学主张）

### theory（理论）
- 核心命题 + 概念工具箱
- 提出者/提出时刻的学术与社会背景
- 经验研究中的验证/应用/修正
- 与其他理论的对话、融合、冲突
- 理论的演变——不是"某人在某年提出了 X"就完了

### methodology（方法论）
- 方法的核心逻辑（不只是操作步骤）
- 产生的学科与传统
- 演变历程（如：田野调查从马林诺夫斯基到数字民族志）
- 与特定理论/范式的亲和性
- 具体操作细节、经典案例拆解
- 局限与应对策略

### genealogy（谱系）
这是本 Wiki 的**特色页面类型**——描绘一条思想流变的主线：
- 如"从结构功能主义到冲突论到批判理论"的演变逻辑
- 如"实证主义方法论在过去 150 年的分化"
- 每个节点标注关键人物、著作、转折事件
- 用 `preceded_by → followed_by` 链接串联

### debate（争论）
- 争论的核心问题
- 各方立场与论证
- 争论的历史演变
- 当下的共识与分歧

### case-study（经典案例）
- 研究背景与问题
- 方法论细节
- 发现与理论贡献
- 后续引发的讨论与修正

### discipline（学科）
- 学科界定与边界
- 核心问题意识
- 历史演变
- 与邻近学科的关系
- 当代热点与瓶颈

### person（人物）
- 生平与学术轨迹
- 核心贡献
- 所属传统与对话对象
- 后世影响与批评

### application（应用）
- 应用领域与场景
- 所用的理论/方法论基础
- 典型案例
- 效果与局限

### career（职业）
- 职业路径与去向
- 所需核心能力
- 发展趋势

## 标签分类

### 时代
`ancient` `early-modern` `modern` `contemporary`

### 范式
`positivism` `interpretivism` `critical-theory` `postmodernism` `post-positivism`
`constructivism` `pragmatism` `realism` `feminism` `postcolonial`

### 方法论
`quantitative` `qualitative` `mixed-methods` `ethnography` `survey` `experiment`
`case-study` `comparative` `longitudinal` `discourse-analysis` `grounded-theory`
`historical-analysis` `action-research` `digital-methods`

### 理论传统
`functionalism` `conflict-theory` `symbolic-interactionism` `rational-choice`
`structuralism` `post-structuralism` `phenomenology` `systems-theory`
`marxism` `neo-marxism` `feminist-theory` `postcolonial-theory`
`critical-race-theory` `queer-theory`

### 学科领域
`sociology` `anthropology` `political-science` `economics` `psychology`
`communication` `education` `demography` `criminology` `gender-studies`
`urban-studies` `organizational-studies` `social-work`

### 学术前沿
`computational-social-science` `AI-social-science` `big-data` `network-analysis`
`digital-ethnography` `behavioral-economics` `environmental-sociology`

### 应用领域
`policy` `social-work` `market-research` `urban-planning` `public-health`
`organizational-dev` `evaluation` `consulting` `education-practice`

### 职业
`academia` `industry` `public-sector` `NGO` `career-path`

## 页面创建门槛与深度要求

### 创建门槛
- 在 2+ 来源中出现，或在某个来源中处于核心地位
- 有足够的材料支撑「不只是摘要」的深度写作

### 深度要求（关键！）
每个页面必须回答的不只是"是什么"，还有：
- **为什么在这个时候出现？**（历史情境）
- **它在回应谁/什么？**（对话关系）
- **它被谁修正/挑战了？**（后续演变）
- **它的实际影响是什么？**（不只是思想史，还有研究实践）

### 不创建
- 一笔带过、无法展开深度写作的
- 与已有页面高度重复、无独特价值的
- 来源不足以支撑深度写作的

## 更新策略

同原有规则：矛盾时保留双方说法并标注，标记 contested。

## 来源追溯

同原有规则：raw/ 文件必须标注 source_url、ingested、sha256。
综合 3+ 来源的页面加 `^[raw/...]` 标注。
