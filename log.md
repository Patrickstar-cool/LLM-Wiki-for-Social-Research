# Wiki 日志

> 所有 Wiki 操作的按时间记录。仅追加，不修改历史条目。
> 格式：`## [YYYY-MM-DD] 操作类型 | 主题`
> 操作类型：ingest, update, query, lint, create, archive, delete
> 超过 500 条时轮转：重命名为 log-YYYY.md，重新开始。

## [2026-08-07] ingest | 生成式AI与教育差距 + 城市与政治暴力 + AI音乐与文化同质化（3篇前沿论文）

- 摄入 raw/papers/cruces-2026-genai-education-gap.md — Cruces, Fernández Meijide, Galiani, Gálvez & Lombardi (2026, arXiv:2608.04198, econ.GN, AEA-RCT 0016607)：1,174 名阿根廷成年人预注册随机在线实验（企业外，保留教育异质性）——AI 使低教育组 +1.242 SD、高教育组 +0.834 SD；无 AI 时教育差距 0.548 SD → 有 AI 时 0.139 SD（关闭 75%）；无 AI 后续模块排除纯委托解释（低教育保留 +0.171 SD，但 0.200 SD 差距重现）；高强度 AI × 高投入才产生后续保留
- 摄入 raw/papers/radil-walther-2026-cities-violence.md — Radil & Walther (2026, arXiv:2608.03570, econ.GN/stat.AP)：ACLED + Africapolis，17 国 2012–2025 中——85% 暴力在城市聚集区 30km 内（40% 城内 + 44% 城郊）；大城市境内暴力最多、近边境小城镇外围暴力更多（边境 40km 效应）；2012 以来城市内份额下降 = 冲突乡村化；挑战「城市化冲突」叙事（Kaldor & Sassen），叛乱策略性交替使用城乡资源；空间冲突生命周期
- 摄入 raw/papers/slendebroek-2026-ai-music-homogenization.md — Slendebroek & Metaxa (2026, AAAI/ACM AIES 2026, arXiv:2608.06106, cs.CY)：审计 Suno 与 Lyria 3 × 4 类型 × 各 100 首 vs 人类语料（72 MIR 特征 + 多重诊断）——Lyria 压缩类型内多样性、Suno 塌缩类型间界限（−36%）、两系统不趋同、分类器近乎完美区分 AI/人类、null-prompt 揭示学习先验；同质化从流通端迁入生产端
- 创建 concepts/生成式AI与教育差距.md — 技能民主化 vs 技能偏向之争的实验证据：差距关闭 75% 但不消失、非纯委托、AI×努力交互；与性别工资差距（差距生命周期）、劳动过程理论（概念/执行分离）、AI行为科学对话
- 创建 concepts/城市与政治暴力.md — 城市/乡村双重暴力逻辑、规模等级与边境邻近效应、空间冲突生命周期、乡村化可逆性；与边境地带政治暴力（姊妹篇双重镜像）、数字国家能力（能力赤字）、冲突论对话
- 创建 concepts/AI音乐与文化同质化.md — 两种结构性同质化、下游→上游迁移论、正义意涵（可读性/价值/认识论合法性）；与批判理论（文化工业的算法完成）、布尔迪厄（区隔的算法化）、AI行为科学（审计方法论扩展）对话
- 更新 concepts/边境地带政治暴力.md — 新增交叉引用 [[城市与政治暴力]]（姊妹篇双重极点）
- 更新 concepts/AI行为科学.md — 新增交叉引用 [[生成式AI与教育差距]] [[AI音乐与文化同质化]]
- 更新 paradigms/批判理论.md — 新增交叉引用 [[AI音乐与文化同质化]]（文化工业的算法完成）
- 更新 index.md（总页数：63 → 66，学术前沿新增 3 页）
- 更新 log.md

## [2026-08-05] ingest | 数字国家能力 + 政策知识生产 + 性别工资差距 + 边境地带政治暴力（4篇前沿论文）

- 摄入 raw/papers/healy-2026-digital-state-capacity.md — Healy et al. (2026, arXiv:2608.03221, econ.GN, 171页长文)：用政府持有的公共 IPv4 地址空间测量**数字国家能力**——150,000 条政府实体记录、150+ 国家、2019-2024 面板、Admin-1 省级 1,681 区域；双重验证 + 应用（腐败控制、疫苗接种）
- 摄入 raw/papers/kim-furnas-wang-2026-policy-knowledge.md — Kim, Furnas & Wang (2026, arXiv:2608.01514, physics.soc-ph)：200 万份美国政策文档 + 近 100 万条科学引用——智库是政策知识主导供应商；极化上升由左倾机构内倾驱动；引用高影响力科学的文档更少隔离、更中心
- 摄入 raw/papers/kim-2026-gender-wage-gap-korea.md — Dongwoo Kim (2026, arXiv:2608.03153, econ.GN)：韩国 OECD 最大性别工资差距（29%）但应届毕业生条件差距仅 4.3%（2008-2019，5.0%→3.0%）；半参数/ML/界三重选择修正不变；顶端残余差距；差距主要在进入后产生
- 摄入 raw/papers/russell-walther-2026-african-borderlands.md — Russell & Walther (2026, arXiv:2608.03596, econ.GN)：1997-2024 非洲冲突时空数据 + OECD SCDi——边境地带暴力更多、随距离极速衰减、2000s初高（几内亚湾/大湖地区）、2010s 上升；跨国扩散=空间扩张而非转移
- 创建 concepts/数字国家能力.md — 测量创新（IP 存量=能力化石）、与数据政治对话（眼睛必须先长出来）、韦伯/斯科特/曼/世界体系对话、IPv4 黄昏等局限
- 创建 concepts/政策知识生产.md — 智库总装车间、左倾内倾驱动的极化、科学去极化力量、与曼海姆/Kingdon/科学学对话
- 创建 concepts/性别工资差距.md — 入口 vs 职业生涯归因之争、三重选择修正方法贡献、与女性主义理论/人力资本/玻璃天花板对话、韩国语境特殊性
- 创建 concepts/边境地带政治暴力.md — 边境=暴力磁铁（主权稀释/跨界庇护/走私走廊/族群分布）、空间方法论、扩散机制、与数字国家能力的镜像对话
- 更新 concepts/数据政治与治理.md — 新增交叉引用 [[数字国家能力]]（数据生产前提条件）+ frontmatter
- 更新 applications/社会科学在公共政策中的应用.md — 新增「新前沿：政策知识的供给侧与数字执行能力（2026）」章节 + 3 条交叉引用 + frontmatter
- 更新 theories/女性主义理论.md — 新增「当代证据：性别工资差距的生命周期（2026）」章节 + 交叉引用 [[性别工资差距]] + frontmatter
- 更新 concepts/计算社会科学.md — 新增交叉引用 [[政策知识生产]] [[数字国家能力]]
- 更新 index.md（总页数：59 → 63，学术前沿新增 4 页）
- 更新 log.md

## [2026-08-03] ingest | CSS 领域性质诊断 + 语音 AI 面试田野实验（2篇高质量来源）

- 摄入 raw/papers/ginnerskov-2026-css-field.md — Ginnerskov (2026, Theory and Society 55:68, 开放获取 CC BY 4.0)，从社会科学哲学视角诊断 CSS 的领域性质：构成性计算轴 vs 工具性计算、场域 vs 学科、纽拉特之船→科学舰队框架、方法论/认识论/本体论三组辩论、三条未来轨迹（碎片化=默认风险/多范式船=最可能/单范式船=最苛刻）
- 摄入 raw/papers/jabarian-2026-voice-ai-interviews.md — Jabarian & Henkel (2026, arXiv:2607.28222, econ.GN)，70,884 份求职申请自然田野实验（预注册 AEA #15385）：AI 语音代理面试 → offer +12%、入职/留任 +18%、生产力无差异；机制=受控方差（标准化框架×个体响应）；78% 选择 AI；报告性别歧视减半；招聘官评估权重转移
- 创建 cases/语音AI面试田野实验.md — **Wiki 首个经典案例页面**：研究背景（面试方差问题）、方法论拆解（信息收集与评估分离）、核心发现（全维度改善）、理论对话（韦伯理性化的算法形态、劳动过程理论的概念/执行分离、AI 行为科学三支柱汇聚）
- 更新 concepts/计算社会科学.md — 新增「CSS 是一个什么样的领域？」章节（+71 行）：两个构成性特征、IC2S2'25 经验证据、非范式科学框架、三组深层辩论、三种未来对比表；frontmatter 更新 + 新增交叉引用 [[语音AI面试田野实验]]
- 更新 theories/劳动过程理论.md — 新增交叉引用：AI 接管信息收集的因果证据——自动化"改善匹配"时控制逻辑如何变化
- 更新 concepts/AI行为科学.md — 新增交叉引用：三支柱汇聚案例
- 更新 index.md（总页数：57 → 59，新增「经典案例」分区第一项）
- 更新 log.md

## [2026-07-31] ingest | 政治消费主义 + 不对称沟通 + AI 谄媚 + AI 公共中介（4篇前沿论文）

- 摄入 raw/papers/conway-2026-consuming-values.md — Conway & Boxell (2026)，支付卡交易大数据（~20%美国消费）：消费者对企业社会立场的响应——对齐者+19%，对立者-12%，持续一年
- 摄入 raw/papers/fenoglio-2026-asymmetric-communication.md — Fenoglio (2026)，维特根斯坦/卢曼/布兰顿框架：LLM 沟通是"不对称的"——意义与规范性全在人类接收方
- 摄入 raw/papers/conlon-2026-ai-sycophancy.md — Conlon & Schwardmann (2026)，1,500人实验、30个决策任务：AI 谄媚但不极化——去极化 0.22sd，推翻 82% 专家预测
- 摄入 raw/papers/kwak-2026-ai-go-mediation.md — Kwak (2026, AIES 2026)，十年韩国围棋 YouTube 解说语料库（~1,900 小时）：AI 从命名到退隐——驯化的语言签名
- 创建 concepts/政治消费主义.md — 价值观驱动的消费行为：弗里德曼命题的修正、与韦伯/马克思/布尔迪厄的对话
- 创建 concepts/不对称沟通.md — LLM 与语言游戏：三个结构性条件定义人-AI 沟通的不对称、对五个 AI 叙事的重新分类
- 创建 concepts/AI谄媚与决策.md — AI 的甜言蜜语 ≠ 行为极化：为什么谄媚不导致极化、市场力量分析、专家预测的集体错误
- 更新 concepts/AI行为科学.md — 新增"AI 谄媚的行为后果"和"AI 沟通的结构性分析"两个章节；frontmatter 更新；新增交叉引用
- 更新 concepts/计算社会科学.md — 新增"AI 的公共中介：Go 解说作为自然实验"章节（驯化理论、来源退隐与可争议性）；frontmatter 更新；新增交叉引用
- 更新 index.md（总页数：54 → 57，新增 3 个前沿/当代思潮页面；更新计算社会科学摘要）
- 更新 log.md

## [2026-07-29] ingest | 数据政治与治理 + 技术意识形态分析 + Truth Social 性别传播（3篇前沿论文）

- 摄入 raw/papers/liu-boyd-2026-fake-data.md — Liu & boyd (2026, CHI '26)，中美比较民族志：国家数据的「假性」在创造、修正、共谋、增补四个官僚环节中的生产——关系性、过程性、操演性
- 摄入 raw/papers/reiber-2026-dialectical-ideology-tech.md — Reiber (2026, CHIdeology Workshop)，基于 Burawoy 的辩证框架分析技术项目的政治意识形态：价值→限制→干预三步法
- 摄入 raw/papers/bidewell-2026-gendered-communication-truth-social.md — Bidewell et al. (2026, WebSci '26)，首项大规模 Truth Social 政治精英性别传播分析：10.7 万帖子、129 位政治人物
- 创建 concepts/数据政治与治理.md — 「所有数据都是假的，但有些是有用的」——数据假性的三重性质（关系性/过程性/操演性）+ 四个时刻 + 与韦伯/斯科特/加芬克尔/戈夫曼/福柯的对话
- 更新 paradigms/批判理论.md — 新增「技术项目的意识形态分析」（Reiber 三步框架）+「数据政治」（Liu & boyd 的比较民族志——扩展批判理论到数据生产基础设施）；frontmatter 更新；新增交叉引用 [[数据政治与治理]]
- 更新 concepts/计算社会科学.md — 新增「Alt-Tech 平台的政治传播」章节（Truth Social 性别模式，Bidewell et al.）；frontmatter 更新；新增交叉引用 [[数据政治与治理]]
- 更新 methodologies/田野调查的演化.md — 新增「国家官僚机构作为田野」章节（boyd 2022-2026 人口普查民族志）；frontmatter 更新；新增交叉引用 [[数据政治与治理]]
- 更新 index.md（总页数：53 → 54，新增 concepts/数据政治与治理）
- 更新 log.md

## [2026-07-27] ingest | 意识形态计算框架 + 多元宇宙分析 + 计算基础理论 + 劳动过程理论（4篇前沿论文）

- 摄入 raw/papers/joseph-2026-ideology-framework.md — Joseph, Williams & Lazer (2026, U Buffalo/Northeastern/Portland State)，意识形态作为多层社会-认知概念网络的计算框架，桥接 NLP+CSS 与意识形态理论
- 摄入 raw/papers/linde-2026-multiverse-analysis-css.md — Linde et al. (2026, GESIS)，多元宇宙分析在计算社会科学中的应用：三个案例研究 + "计算失败应被报告"的论证
- 摄入 raw/papers/sfi-2026-computational-foundations.md — SFI 等多机构 (2026)，社会作为分布式计算系统的理论视角：四个社会计算现象 + CS 理论资源
- 摄入 raw/papers/qin-2026-labor-process-theory-hci.md — Qin & Cheon (2026, CHI'26 接收)，劳动过程理论（马克思→布雷弗曼→布若威）在 HCI/设计领域的系统引入
- 创建 concepts/意识形态的计算框架.md — 意识形态 = 归因的多层社会-认知概念网络；与曼海姆、葛兰西、福柯的对话；NLP 任务的操作化方向
- 创建 theories/劳动过程理论.md — LPT 理论谱系：马克思→布雷弗曼→布若威→当代算法管理；LPT × HCI 七个研究方向；与韦伯/批判理论/符号互动论的对话
- 更新 concepts/计算社会科学.md — 新增"多元宇宙分析"章节（Linde et al.：CSS 的 N 条分析路径、计算失败应发表）+ "计算基础理论"章节（SFI：社会=分布式计算，四个核心现象，与斯密/涂尔干/韦伯/哈耶克/阿罗的对话）；frontmatter 更新 + 交叉引用新增 2 条
- 更新 paradigms/批判理论.md — 新增"劳动过程理论"作为当代发展方向；frontmatter 更新 + 交叉引用新增 3 条
- 更新 index.md（总页数：51 → 53，新增 theories/劳动过程理论、concepts/意识形态的计算框架）
- 更新 log.md

## [2026-07-24] ingest | AI 行为科学 + Agentic Reproducibility + HSSBench + 合成社会图（4篇前沿论文）

- 摄入 raw/papers/kohler-2026-agentic-reproduction.md — Kohler et al. (2026, ETH Zurich, under review)，LLM 代理从论文方法描述自主复现 48 篇社科论文：85%+ 符号一致性
- 摄入 raw/papers/kang-2026-hssbench.md — Kang et al. (2026, ICLR 2026)，首个 HSS 领域的多模态大模型基准测试（13K+ 题目，6 语言），揭示"垂直推理"vs"横向推理"根本差异
- 摄入 raw/papers/jackson-2026-ai-behavioral-science.md — Jackson et al. (2026, CASBS 研讨会产物，Stanford+MIT+等全明星阵容)，AI 行为科学的学科宣言：三支柱（评估 AI / AI 工具研究人 / 人-AI 互动生态系统）
- 摄入 raw/papers/cha-2026-frame-entrepreneurs-agent-community.md — Cha & Kim (2026, LG Uplus)，对 AI 代理社区 Moltbook 的社会学分析：框架企业家理论验证，身份主张极度集中
- 更新 concepts/计算社会科学.md — 新增 4 个前沿章节：AI 行为科学三支柱、Agentic Reproducibility、HSSBench、合成社会图中的框架企业家（+约 150 行深度内容）
- 创建 concepts/AI行为科学.md — 新前沿页面：学科定位、三大支柱详解、与经典社会学传统（实证主义/韦伯/戈夫曼）的对话
- 更新 methodologies/定量研究方法论.md — 新增"Agentic Reproducibility"章节于可重复性危机之后
- 更新 index.md（总页数：50 → 51，更新日期）
- 更新 log.md

## [2026-07-22] ingest | AI 时代质性研究 + 社会模拟三代演进 + 差序格局共情研究（3篇来源）

- 摄入 raw/papers/abramson-2026-qualitative-ai.md — Abramson et al. (2026), 即将刊于 Annual Review of Sociology Vol 52，质性研究在 AI 时代的五种路径分类法
- 摄入 raw/papers/cau-2026-social-simulations-abm-digital-twins.md — Cau et al. (2026), Encyclopedia of SNAM，社会模拟从 ABM 到 LLM-ABM 到数字孪生的三代演进
- 摄入 raw/papers/zhu-2026-empathy-chaxu-geju.md — Zhu & Yang (2026), 《心理科学进展》，差序格局框架下的中国文化共情研究
- 更新 methodologies/质性研究方法论.md — 新增「AI 时代的质性研究」章节：五种路径分类、历史语境、务实的中间道路论证
- 更新 concepts/计算社会科学.md — 新增「社会模拟的三代演进」章节：经典 ABM → LLM-ABM → 社会数字孪生
- 更新 concepts/差序格局.md — 新增「差序格局与共情」章节：亲疏/尊卑双重挑战、中国文化共情三特征
- 更新 index.md（总页数保持 50，更新日期）
- 更新 log.md

## [2026-07-20] ingest | 依附理论 + 差序格局更新（3篇来源）

- 摄入 raw/articles/schmidt-2018-dependency-theory.md — Global South Studies，依附理论完整概述
- 摄入 raw/papers/hesketh-2024-dependency-dialectics.md — Alternautas（开放获取），依附理论的辩证复兴：生态-空间转向
- 摄入 raw/papers/hu-2024-differential-mode-association.md — The China Review，差序格局的当代定量验证
- 创建 theories/依附理论.md — 依附理论的完整百科页面：历史情境、两个阵营、核心概念、衰落与生态复兴
- 更新 concepts/差序格局.md — 添加 Hu (2024) 全国调查的 7 项关键发现（父系原则消解！）
- 更新 theories/世界体系理论.md — 修复交叉引用，链接新依附理论页面
- 更新 theories/后殖民理论.md — 添加依附理论交叉引用
- 更新 index.md（总页数：49 → 50）
- 更新 log.md

## [2026-07-15] restructure | 方向升级：从分类目录 → 百科全书式思想长河
- 重写 SCHEMA.md：三层深度（地表/地质/化石）、era/preceded_by/followed_by/responds_to 河流脉络系统
- 创建 timelines/社会科学思想长河.md — 从古希腊到 AI 时代的全景地图
- 创建 genealogies/社会学理论三大传统的对话.md — 马克思/涂尔干/韦伯三条河的源流与合流
- 更新 index.md（总页数：8，新增「主干河流」「理论谱系」等分区）
- 新增目录：timelines/、genealogies/、debates/、cases/、applications/、careers/
- 领域：社会科学知识体系
- 创建 SCHEMA.md、index.md、log.md、目录结构
- 创建 paradigms/实证主义.md — 孔德、涂尔干到后实证主义
- 创建 paradigms/诠释主义.md — 韦伯、格尔茨到深描
- 创建 disciplines/社会学.md — 学科全景
- 创建 theories/结构功能主义.md — 帕森斯 AGIL 到默顿修正
- 更新 index.md（总页数：4）

## [2026-07-15] ingest | 斯坦福批判理论 + CSS 2026 会议

## [2026-07-17] ingest | 去殖民方法论 + 原住民认识论（3篇开放获取论文）
- 摄入 raw/papers/chaves-perez-2025-sentipensar.md — Frontiers in Sociology, 2025, sentipensar 与 Nasa 原住民认识论
- 摄入 raw/papers/kwachou-2025-decolonisation.md — Open Research Europe, 2025, 去殖民化作为认识论去中心化
- 摄入 raw/papers/adjei-moss-2026-academic-boldness.md — Human Arenas (Springer), 2026, 学术勇气与去殖民化知识生产
- 创建 methodologies/去殖民研究方法论.md — 认识论去中心化、sentipensar 田野工作、三条操作路径
- 创建 concepts/原住民认识论.md — sentipensar 详解、多元宇宙、认识论多元主义的社会科学后果
- 更新 theories/后殖民理论.md — 添加来源、交叉引用新页面
- 更新 index.md（总页数：47 → 49）
- 更新 log.md
- 摄入 raw/articles/stanford-critical-theory-2025.md（Stanford Encyclopedia of Philosophy，2025 版）
- 摄入 raw/articles/css-2026-conference.md（CSSSA，2026 年会信息）
- 创建 paradigms/批判理论.md — 法兰克福学派、三代演变、核心概念与当代发展
- 创建 concepts/计算社会科学.md — 方法体系、学术生态与前沿方向
- 更新 index.md（总页数：6）

## [2026-08-10] ingest | 环境正义 + 算法引导与住房歧视 + 社会流动（3篇前沿论文）

- 摄入 raw/papers/cottafava-2026-environmental-justice-networks.md — Cottafava, Nicolás-Carlock, Llavero-Pasquina & Martínez-Alier (2026, arXiv:2603.29722, physics.soc-ph)：EJAtlas 网络分析——3,396 起冲突、6,244 家公司、11,231 个环境正义组织——公司网络部门内聚（59% LCC）、EJO 网络跨部门去中心化（81% LCC、平均路径 3.7）；生态不等价交换（熵出口/环境负债）；全球环境正义运动真实存在
- 摄入 raw/papers/samad-2026-llm-housing-steering.md — Samad, Lam, Mügge-Durum & Akinwumi (2026, arXiv:2606.06694, cs.CY)：7 个 LLM × 4 美国城市 × 3 提示条件的配对测试行为审计——种族引导是「解释许可」的涌现行为（身份×偏好×空间逻辑）；偏好条件化放大引导（同一偏好不同解释）；城市=羊皮纸，非中性测试单元；FHA/不同影响法律框架与 Meta 案先例
- 摄入 raw/papers/cattan-2026-indonesia-multigenerational.md — Cattan, Dalla-Zuanna, Stuhler & Wong (2026, arXiv:2604.19969, econ.GN)：IFLS 三代教育流动——祖父母系数为负（多代际流动高于亲子外推）；信贷约束（1997-98 金融危机）与家族式婚配两机制；Becker-Tomes 原版可正可负（Solon 简化版强制为负）
- 创建 concepts/环境正义.md — 生态分配冲突、熵经济、商品边疆、生态不等价交换；公司 vs EJO 网络结构不对称表；与[[世界体系理论]]（生态资产负债表）、[[依附理论]]（生态转向网络证据）、[[后殖民理论]]、[[冲突论]]、[[去殖民研究方法论]]（共同生产）对话
- 创建 concepts/算法引导与住房歧视.md — 歧视形态变迁史（红线→中介→算法→LLM）；配对测试方法论；引导=解释许可的涌现；城市空间逻辑异质性；与[[AI行为科学]]（支柱一案例扩展）、[[数据政治与治理]]（空间准入中介）、[[城市与政治暴力]]、[[芝加哥学派]]对话
- 创建 concepts/社会流动.md — 代际 vs 多代际测量之争；印尼反例；信贷约束与婚配规范机制；Becker-Tomes 理论贡献；与[[性别工资差距]]（测量窗口姊妹篇）、[[生成式AI与教育差距]]（代际后果）、[[定量研究方法论]]、[[世界体系理论]]对话
- 更新 theories/世界体系理论.md — 新增「生态维度：环境负债与不等价交换」章节 + 交叉引用 [[环境正义]] + frontmatter
- 更新 concepts/AI行为科学.md — 新增「案例扩展：住房搜索中的种族引导审计」章节 + 交叉引用 [[算法引导与住房歧视]] + frontmatter
- 更新 concepts/计算社会科学.md — 新增 3 条交叉引用（[[环境正义]] [[算法引导与住房歧视]] [[社会流动]]）+ frontmatter
- 更新 concepts/性别工资差距.md — 新增交叉引用 [[社会流动]]（测量窗口之争的代际版本）+ frontmatter
- 更新 concepts/生成式AI与教育差距.md — 新增「与社会流动：即时压缩 vs 代际传递」章节 + frontmatter
- 更新 index.md（总页数：66 → 69，学术前沿新增 3 页）
- 更新 log.md

注：Abramson et al. (2026, ARS) 预印本（arXiv:2509.12503）已在此前摄入（raw/papers/abramson-2026-qualitative-ai.md），本次搜索再次命中，未重复摄入。


## [2026-08-12] ingest | 学术分层 + 幽灵工作与情感劳动 + 可复现性（4篇前沿论文）

- 摄入 raw/papers/cook-2026-sociology-of-sociology.md — Cook (2026, arXiv:2601.04579, physics.soc-ph)：社会学的社会学——连接 1970 年以来全部博士论文与期刊文献；三大顶刊对低声望博士项目校友的声望偏见持续（过度发表+引用不足=光环效应）；top20 机构占约 75% 发文；ASR 偏见最重；AJS 对 UChicago 的本校偏见 2000 年后加剧、Social Forces 对 UNC-CH 的偏见消失（天然对照实验）；顶刊=年轻学者的职业筛选装置（博士毕业后 7-9 年）
- 摄入 raw/papers/rahman-2026-ghostcrafting.md — Rahman & Sultana (2026, arXiv:2512.21649, cs.HC)：孟加拉平台劳动 8 个月民族志（n=34）——「幽灵工艺 AI」概念扩展 Gray & Suri 的 ghost work：工人物质支撑 AI 系统却被 NDA/作品集禁令/诉讼威胁抹除署名；情境化学习（网吧、外语教程、WhatsApp 群）与战术库（VPN 伪装美国身份、图片编码绕过平台费）；后殖民劳动等级
- 摄入 raw/papers/mo-2026-game-companionship.md — Mo et al. (2026, arXiv:2607.24363, cs.HC)：中国游戏陪玩 22 人访谈——「订单约束」机制：订单内深度表演+订单后完全情感抽离；陪玩-客户-俱乐部三边网络修正零工双边治理模型；身份流动性（陪玩↔客户↔运营者）
- 摄入 raw/papers/shah-2026-reproducibility-agents.md — Shah, Hopfgartner & Bleier (2026, arXiv:2602.08561, cs.SE/cs.CL, WWW Companion 26)：130 个合成测试用例对比可复现性修复——prompt-based 31-79% vs agent-based 69-96%；结构逻辑缺失最难；>50% 研究者无法复现自己（Baker 2016）、74% R 脚本跑不通（Trisovic 2022）
- 创建 concepts/学术分层与精英主义.md — 科学社会学：期刊金字塔、声望偏见、本校偏见、顶刊年龄结构；默顿不完美科学假说→布尔迪厄趣味政治→Zuckerman 科学精英；与[[政策知识生产]][[意识形态的计算框架]]对话
- 创建 concepts/幽灵工作与全球数据劳动.md — ghost work→ghostcrafting；AI 的署名负债；情境化学习与战术库；与[[劳动过程理论]][[依附理论]][[后殖民理论]][[世界体系理论]]对话
- 创建 concepts/情感劳动.md — Hochschild 1983 → 数字情感劳动 → 订单约束机制；三边治理与身份流动性；与[[符号互动论]][[女性主义理论]][[劳动过程理论]]对话
- 更新 theories/劳动过程理论.md — 新增「数字劳动的新形态：幽灵劳动与情感劳动」章节（控制对象从身体/认知推进到署名与情感）+ 2 条交叉引用 + frontmatter
- 更新 concepts/计算社会科学.md — 新增「可复现性危机与 AI 修复」章节（Shah 2026 + Baker/Trisovic 背景 + CORE-Bench/PaperRepro）+ 交叉引用[[学术分层与精英主义]] + frontmatter（tag 加 reproducibility）
- 更新 index.md（总页数：69 → 72，学术前沿新增 3 页）
- 更新 log.md
