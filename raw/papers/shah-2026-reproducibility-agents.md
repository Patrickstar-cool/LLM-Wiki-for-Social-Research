---
source_url: https://arxiv.org/abs/2602.08561
ingested: 2026-08-12
sha256: d48cb77870ba6c013a28f3c545a0c0482725a7b24c21ef209957b4eb9ebd48b9
---

# Automating Computational Reproducibility in Social Science: Comparing Prompt-Based and Agent-Based Approaches

- 作者：Syed Mehtab Hussain Shah, Frank Hopfgartner, Arnim Bleier
- arXiv:2602.08561v3 [cs.SE, cs.CL]，2026-02-09 提交，2026-04-23 更新；WWW Companion '26（2026 年 6 月 29 日-7 月 3 日，迪拜）
- 关键词：computational reproducibility, LLM agents, social science, benchmark, repair

## 摘要

复现计算研究常被视为「在共享数据上重跑共享代码」的简单事。实际上，即使材料齐全，已发表分析也经常失败——依赖缺失、脆弱路径、版本不匹配，以及更棘手的计算逻辑缺口。本研究考察 LLM 与自主 AI 代理能否自动化修复此类失败的常规劳动。基于 5 个完全可复现的 R 社会科学研究，注入真实错误（执行级问题、上下文代码修复、结构逻辑缺失），打包成 130 个合成测试用例。对比两种修复范式：**prompt-based 工作流**（结构化提示迭代查询 LLM，上下文丰富度递增）与 **agent-based 工作流**（编码代理检查项目文件、针对性编辑、重跑分析直至完成或超时）。修复成功以「输出匹配 ground-truth 结果」为准，而非仅仅代码可执行。

## 关键结果

- **Prompt-based 成功率 31-79%**：高度依赖失败复杂性与上下文量；更丰富的上下文（论文全文+补充脚本）对结构复杂案例增益最大
- **Agent-based 成功率 69-96%**：全类别一致优于 prompt-based——**环境感知的迭代式代理工具使用**是关键优势，而非模型能力本身
- **结构逻辑缺失（Category C）最难**：需要重建缺失分析逻辑的错误，仅靠提示难以修复
- 提示设计敏感：最小上下文对逻辑密集型修复往往不足

## 背景数据：可复现性危机的规模

- Baker (2016, Nature) 调查：>70% 研究者报告无法复现他人发现，**>50% 无法复现自己**的早期工作
- Trisovic et al. (2022)：共享的 R 脚本中约 **74%** 在干净环境无法运行
- Hardwicke et al. (2018)：期刊强制开放数据政策下，仅极少数作者提供分析脚本
- 生态与演化生物学：仅 15% 的 meta 分析共享可用数据与代码，多数结果仍无法复现（Kambouris et al. 2024）
- 透明性本身不足（Fidler 2024：即使名义上材料可得，已发表 meta 分析结果仍常无法复现）

## 相关基准与工作

- **CORE-Bench**：将计算复现框定为交互式代理任务（执行、检查、输出验证）
- **PaperBench**：从论文描述端到端复现 ML 研究——去除可执行结构后性能急剧下降
- **REPRO-Bench**：代理评估社科研究可复现性（Hu et al. 2025）——评估任务而非修复任务
- **PaperRepro**（Zhang et al. 2026）：两阶段多代理复现性评估流水线，执行与评估分离
- 既有工作把可复现性当作**评估任务**，本研究补充了**修复任务**视角——发表后失败（材料在但跑不通）的系统化研究

## 方法要点

- Ground-truth：从 StatCodeSearch 子集（Saju et al. 2025 验证过的工作流）筛选 5 篇完全可复现的开放论文
- 错误注入分三类：A=执行级、B=上下文代码修复、C=结构逻辑缺失
- 验证环境：Rocker (rocker/r-ver:4.4.1) Docker，8GB RAM / 8 核
- 修复成功的判定：执行输出与 ground-truth 输出匹配（status.txt 标记 Reproduced/Not Reproduced）
- 数据与代码公开：github.com/Mehtab07/Automating-Computational-Reproducibility（DFG 资助 551687338、460234259）

## 意涵

- **实践**：代理修复系统可显著减少手工劳动，提高真实社科研究情境下计算可复现性的可靠性
- **方法论**：环境访问+迭代执行反馈是代理优于纯提示的关键——「能跑」比「会说」重要
- **科学社会学**：可复现性缺口是知识累积的结构性障碍——AI 修复只是缓解症状，不解决「发表即终审」的激励结构

## 局限与未来

- 合成基准规模有限（5 篇研究、130 用例）；将扩展更多研究与失败模式
- 当前 agent 环境中 ground-truth 输出与修复环境同容器挂载（人工日志检查确认未提前访问，但架构上未强制隔离）——未来需环境隔离防数据泄漏
- 未系统分析「可执行但结果错误」的失败案例
- 单一模型（Qwen3-Coder-480B-A35B）；需跨模型/架构评估泛化性

## 关联研究

- Baker (2016)：1,500 位科学家揭示可复现性之困
- Trisovic et al. (2022)：研究代码质量与执行的大规模研究
- Saju et al. (2025)：OSF 上 R 代码补充的计算可复现性
- Siegel et al. (2024)：CORE-Bench
- Hu et al. (2025)：REPRO-Bench
