# Wiki Schema

## 领域定位

本 Wiki 构建**社会科学的知识体系**——从经典范式到前沿方法，从理论脉络到现实应用，
从学术研究到职业发展。目标是形成一个结构化、可追溯的社会科学知识网络。

聚焦范围：
- **内部**：社会学、人类学、政治学、经济学、心理学等核心学科的范式演变、
  方法论体系、理论发展脉络、前沿学术动态、学科瓶颈与未来方向、
  社会应用价值、学生职业路径
- **边界**：纯自然科学方法论、与社会科学无关的时政评论、非学术性的社会杂谈

## 文件命名规范

- 文件名：中文或英文均可，用连字符（-）连接，不加空格
- 示例：`实证主义范式.md`、`田野调查方法论.md`、`布尔迪厄-场域理论.md`
- 每个页面以 YAML frontmatter 开头（见下方模板）

## Frontmatter 模板

```yaml
---
title: 页面标题
created: YYYY-MM-DD
updated: YYYY-MM-DD
type: paradigm | methodology | theory | discipline | concept | person | comparison | query
tags: [从下方标签分类中选择]
sources: [raw/articles/来源文件名.md]
confidence: high | medium | low
contested: false | true
---
```

- `type`：范式（paradigm）、方法论（methodology）、理论（theory）、
  学科（discipline）、概念（concept）、人物（person）、对比分析（comparison）、
  查询存档（query）
- `confidence`：多源交叉验证 → high；单一可信源 → medium；有争议 → low
- `contested`：存在学术争议时标记为 true

## 标签分类

使用标签前必须确认已在此列表中。新增标签须先添加到此文件。

### 范式
`positivism` `interpretivism` `critical-theory` `postmodernism` `post-positivism`
`constructivism` `pragmatism` `realism`

### 方法论
`quantitative` `qualitative` `mixed-methods` `ethnography` `survey` `experiment`
`case-study` `comparative` `longitudinal` `discourse-analysis` `grounded-theory`

### 理论传统
`classical-theory` `contemporary-theory` `grand-theory` `middle-range-theory`
`micro-theory` `macro-theory` `structuralism` `functionalism` `conflict-theory`
`symbolic-interactionism` `rational-choice` `phenomenology`

### 学科领域
`sociology` `anthropology` `political-science` `economics` `psychology`
`communication` `education` `demography` `criminology` `gender-studies`
`urban-studies` `organizational-studies`

### 学术前沿
`computational-social-science` `AI-social-science` `big-data` `network-analysis`
`digital-ethnography` `behavioral-economics` `neuro-sociology`

### 应用
`policy` `social-work` `market-research` `urban-planning` `public-health`
`organizational-dev` `evaluation` `consulting`

### 职业发展
`academia` `industry` `public-sector` `NGO` `career-path`

## 页面创建门槛

- **创建新页面**：一个范式/理论/方法论在 2+ 个来源中出现，或在某个来源中处于核心地位
- **补充现有页面**：新来源提到已有页面的内容，追加信息并刷新 updated 日期
- **不创建**：一笔带过的提及、无关紧要的细节、超出领域范围的内容
- **拆分页面**：当页面超过 ~200 行时，拆分为子主题并添加交叉链接
- **归档页面**：内容已完全过时 → 移入 `_archive/`，从 index 移除

## 范式页面结构

每个范式页面应包含：
- 核心主张（一句话概括）
- 哲学基础与渊源
- 对本学科研究实践的影响
- 代表人物与经典著作
- 批评与局限
- 与其他范式的关系（[[维基链接]]）

## 理论页面结构

每个理论页面应包含：
- 理论概述与核心命题
- 提出者、提出时间、学术背景
- 理论框架与关键概念
- 经验验证与应用案例
- 理论批评与发展演变
- 相关理论（[[维基链接]]）

## 方法论页面结构

每个方法论页面应包含：
- 方法概述与适用场景
- 操作步骤与核心工具
- 优势与局限
- 与其他方法的关系（[[维基链接]]）

## 更新策略

当新信息与已有内容矛盾时：
1. 检查信息来源的时效性——新研究通常优先
2. 如确实矛盾，同时记录两种观点，标注时间和来源
3. 在 frontmatter 中标记 `contested: true`
4. 在 lint 报告中标记供人工审核

## 来源追溯

- 每个 `raw/` 中的源文件须有 frontmatter：`source_url`、`ingested`、`sha256`
- 综合 3+ 来源的页面，在段落末尾加 `^[raw/articles/来源.md]` 标注
- 重新摄入同一 URL 时，对比 sha256：不变则跳过，变化则更新
