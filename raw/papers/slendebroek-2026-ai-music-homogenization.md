---
source_url: https://arxiv.org/abs/2608.06106
ingested: 2026-08-07
sha256: b3c86cd5452b91ba992bc7028cb7c9922a1c8fb29e90088f0e75ee2f2c8c7802
---

# The Algorithmic Flattening of Sound: Computational Evidence and Justice Implications of AI Music Homogenization（声音的算法扁平化：AI 音乐同质化的计算证据与正义意涵）

**Authors:** Zoe Slendebroek, Danaë Metaxa (University of Pennsylvania)

**Venue:** arXiv:2608.06106 [cs.CY], to be published in AAAI/ACM AIES 2026

## Abstract

This paper audits whether large-scale generative music systems exhibit measurable musical homogenization relative to human-produced music, and develops a justice-centered account of why this matters. We audit two commercially deployed systems (Suno and Lyria 3) across four genres (Afrobeats, K-pop, Dance Pop, and Heavy Metal). For each system and genre, we generate 100 tracks and compare them against human corpora of equal size, using 72 music information retrieval (MIR) features and multiple diagnostics of dispersion, redundancy, and separability. We define homogenization as reduced acoustic variation in standard computational audio features including rhythm and timing, timbre/spectral shape, and dynamics, both within genres and across genre boundaries. We also generate tracks using only a genre name as the prompt, with no additional instructions, to reveal each system's default musical tendencies. The results show two structurally distinct homogenizing tendencies.

Lyria reduces within-genre acoustic diversity, while Suno collapses the acoustic distinctions between genres without compressing within-genre spread. Neither system follows user prompts faithfully, indicating that the observed patterns reflect learned priors rather than prompt constraints. The two systems do not converge on a common acoustic profile and are more acoustically distant from each other than two random human subsamples would typically be. Nevertheless, a standard classifier distinguishes AI from human tracks near-perfectly on MIR features alone. We argue that these patterns matter not as an aesthetic curiosity but as a justice-relevant condition, shaping which musical styles become legible, valued, and economically rewarded as generated outputs increasingly circulate at scale.

## Key Concepts / 关键要点（中文）

### 审计设计
- 两个商用文本生成音乐系统：**Suno** 与 **Lyria 3**（Google）；四个类型：Afrobeats、K-pop、Dance Pop、Heavy Metal
- 每系统每类型生成 100 首，对照等量人类语料；72 个 MIR（音乐信息检索）声学特征 + 多重诊断：全局离散度、特征方差、熵（冗余度）、PCA 几何覆盖、可分性（分类器）
- **Null-prompt 基线**：只用类型名作 prompt（无额外指令）——隔离「系统默认倾向」与「提示工程效应」；结果：系统不忠实遵循用户提示 → 观察到的同质化模式来自**学习先验**而非提示约束

### 核心发现
1. **两种结构性同质化**：Lyria 压缩**类型内**声学多样性（多数类型比值 <1，如 Heavy Metal 0.773、Afrobeats 0.832）；Suno **塌缩类型间**差异——类型分离比 −36%（0.442 vs 人类 0.662），类型内保持
2. **系统不收敛**：两系统彼此声学距离比随机人类子样本更远——同质化不是「趋同于同一声音」，而是各自有自己的默认声学档案
3. **AI 与人类可近乎完美区分**：标准分类器仅凭 MIR 特征即可判别——生成音乐存在「声学指纹」式的系统性差异
4. **标题多样性极低**：Suno null-prompt 100 首中唯一标题仅 13–16 个（"Anvil Breaker" 出现 18 次）——词汇跨类型泄漏（"Anvil"/"Pulse" 在多类型高频出现）

### 历史脉络：同质化压力的「下游 → 上游」迁移
- 同质化不是新现象：Adorno (1941) 文化工业、Peterson & Berger (1975) 产业集中、广播合并后风格多样性下降（Prindle 2003）、流媒体推荐窄化曝光（Chen & Huang 2024）——此前机制主要作用于**流通与选择（下游）**：奖励熟悉、惩罚偏离，生产逐渐对齐分发系统
- 经验证据：Serra et al.（西方大语料数十年：音高/音色多样性下降、响度上升、重复增加）；Mauch et al.（风格趋同）；Interiano et al. (2018)（更慢节奏、小调增多、结构重复）
- **GenAI 的转变**：同质化从「过滤现有曲目的选择结果」变成「生成新音乐的生产属性」——系统从训练语料的统计规律中采样，优化逻辑被植入**生产本身**。这才是真正的新颖之处

### 正义意涵（justice-centered account）
- 不只是美学奇观：当生成输出大规模流通时，哪些音乐风格**可被读取（legible）、被重视（valued）、被经济回报（economically rewarded）**——塑造文化权威、经济价值与认识论合法性
- 对公平/问责研究的拓展：算法审计（algorithmic audit）从信息域（搜索结果、推荐）扩展到创意生产域
