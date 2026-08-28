<div align="center">

# Pandora's Toolbox｜潘多拉工具箱

### 生命周期视角下的通用智能体安全综述

**覆盖智能体完整生命周期的风险、评测与防御文献图谱**

[![Lifecycle](https://img.shields.io/badge/Perspective-Agent%20Lifecycle-284B75?style=flat-square)](#生命周期视角)
[![Topic](https://img.shields.io/badge/Topic-Generalist%20Agent%20Security-8C3B3B?style=flat-square)](#文献图谱)
[![Status](https://img.shields.io/badge/Status-Actively%20Maintained-3B6B57?style=flat-square)](#参与贡献)

🌐 **Language / 语言:** [**English**](./README.md) · **简体中文**

[**论文 PDF**](<./Pandora-agent-survey (Arxiv).pdf>) · [**分类体系**](#生命周期视角) · [**参与贡献**](#参与贡献)

</div>

---

## 概览

通用智能体已经不再是受限的对话接口。它们能够获取可复用技能、检索长期记忆、选择工具、与外部环境交互，并跨会话保留执行产物。因此，其安全问题不能再被理解为彼此孤立的模型缺陷或组件风险：一个漏洞可能在早期进入系统并保持潜伏，在决策过程中被激活和放大，最终表现为具有现实后果的外部动作，并进一步污染持久状态。

本仓库配套综述论文 *Pandora's Toolbox: A Survey of Generalist Agent Security from the Lifecycle Perspective*，通过两个相互正交的结构组织通用智能体安全研究：

- **生命周期阶段：** **来源（provenance）→ 编排（orchestration）→ 执行（execution）**，以及由持久状态形成的反馈回路。
- **安全研究视角：**在每个阶段分别考察**风险与攻击、评测基准和防御方法**。

> 下文的阶段归属分别表示风险主要从何处引入、安全证据主要在哪里收集，或防御措施主要在哪里介入。这些类别并非互斥：同一种攻击或方法可能跨越多个阶段，同一篇论文也可能出现在多个类别中。

## 生命周期视角

<p align="center">
  <img src="./assets/figures/lifecycle-overview.png" width="100%" alt="通用智能体安全生命周期：来源、编排、执行，以及持久状态造成的反向污染。">
</p>

<p align="center"><sub><b>图 1.</b> 风险在来源阶段进入系统，在编排阶段传播并放大，在执行阶段表现为外部行为，并通过受污染的持久状态影响未来工作流。</sub></p>

| 生命周期阶段 | 核心安全问题 | 主要风险路径 | 典型安全证据 | 主要干预位置 |
|---|---|---|---|---|
| **来源** | 哪些能力和工件被允许进入系统？ | 被投毒的元数据、技能文件、依赖和伪造信任信号 | 技能包、清单、来源记录 | 安装前检查与准入控制 |
| **编排** | 上下文、记忆、技能和工具如何被组合成决策？ | 恶意请求、检索记忆、技能指令和不安全组合 | 技能选择、规划、候选工具调用 | 上下文过滤、决策完整性与规划审计 |
| **执行** | 哪些动作被真正提交，环境如何响应？ | Web、GUI、工具输出、API、文件和终端注入 | 动作、轨迹、工具证据和最终环境状态 | 步骤级执行约束与轨迹复核 |
| **持久反馈** | 哪些状态会保留并重新进入未来工作流？ | 受污染的记忆、被改写的技能和受损工件 | 跨会话状态和风险复现 | 来源追踪、状态恢复与持续安全演化 |

<details>
<summary><b>查看论文中的完整分类体系</b></summary>

<br>

<p align="center">
  <a href="./assets/figures/lifecycle-taxonomy.png">
    <img src="./assets/figures/lifecycle-taxonomy.png" width="92%" alt="通用智能体完整生命周期中的安全风险、评测与防御分类体系。">
  </a>
</p>

<p align="center"><sub><b>图 2.</b> 通用智能体完整生命周期中的安全风险、评测基准与防御方法分类体系。点击图片可查看高清版本。</sub></p>

</details>

## 文献图谱

- [1. 来源阶段（Provenance）](#provenance)
  - [风险与攻击](#provenance-risks)
  - [评测基准](#provenance-evaluation)
  - [防御方法](#provenance-defense)
- [2. 编排阶段（Orchestration）](#orchestration)
  - [风险与攻击](#orchestration-risks)
  - [评测基准](#orchestration-evaluation)
  - [防御方法](#orchestration-defense)
- [3. 执行阶段（Execution）](#execution)
  - [风险与攻击](#execution-risks)
  - [评测基准](#execution-evaluation)
  - [防御方法](#execution-defense)
- [4. 持久反馈与研究展望](#persistent-feedback)
  - [自进化智能体安全](#self-evolving-agent-safety)

---

<a id="provenance"></a>

## 1. 来源阶段（Provenance）

来源阶段决定哪些能力可以进入智能体的可用能力空间。技能元数据可能在任务开始前就被加载，而技能规范、脚本、资源、依赖和信任信号则可能长期保持潜伏，直到后续用户请求将其激活。

<a id="provenance-risks"></a>

### 1.1 风险与攻击

#### 声明式技能文件投毒

攻击者污染技能元数据、说明、示例或触发规则，使恶意自然语言指令进入智能体的规划上下文。

- (2026) [Skill-Inject: Measuring Agent Vulnerability to Skill File Attacks](https://arxiv.org/abs/2602.20156)
- (2026) [Supply-Chain Poisoning Attacks Against LLM Coding Agent Skill Ecosystems (PoisonedSkills)](https://arxiv.org/abs/2604.03081)
- (2026) [SkillJect: Effectively Automating Skill-Based Prompt Injection for Skill-Enabled Agents](https://arxiv.org/abs/2602.14211)
- (2026) [Under the Hood of SKILL.md: Semantic Supply-Chain Attacks on AI Agent Skill Registry](https://arxiv.org/abs/2605.11418)

#### 多组件技能生态投毒

攻击面从主技能文件扩展到辅助脚本、工具接口、依赖、外部资产、配置、检索资源和本地缓存。

- (2026) [SkillSafetyBench: Evaluating Agent Safety under Skill-Facing Attack Surfaces](https://arxiv.org/abs/2605.12015)
- (2026) [Skill-Inject: Measuring Agent Vulnerability to Skill File Attacks](https://arxiv.org/abs/2602.20156)
- (2026) [Proteus: A Self-Evolving Red Team for Agent Skill Ecosystems](https://arxiv.org/abs/2605.11891)

#### 跨会话技能重写与后门触发

攻击在当前会话中修改可复用技能、缓存、项目工件或依赖，而恶意行为只在未来会话或特定触发条件下出现。

- (2026) [SkillHarm: Lifecycle-Aware Skill-Based Attacks via Automated Construction](https://arxiv.org/abs/2606.02540)
- (2026) [SkillTrojan: Backdoor Attacks on Skill-Based Agent Systems](https://arxiv.org/abs/2604.06811)

<a id="provenance-evaluation"></a>

### 1.2 评测基准

#### 恶意技能检测

这类基准评测规则系统、模型、静态分析器或验证器能否在执行前识别技能包中的语义攻击、代码攻击和混合攻击。

- (2026) [Agent Skills in the Wild: An Empirical Study of Security Vulnerabilities at Scale](https://arxiv.org/abs/2601.10338)
- (2026) [SkillSieve: A Hierarchical Triage Framework for Detecting Malicious AI Agent Skills](https://arxiv.org/abs/2604.06550)
- (2026) [MalSkillBench: A Runtime-Verified Benchmark of Malicious Agent Skills](https://arxiv.org/abs/2606.07131)
- (2026) [SkillsMetric: Mapping the Detection Boundary of Static Analysis for Malicious Agent Skills](https://arxiv.org/abs/2608.08468)

<a id="provenance-defense"></a>

### 1.3 防御方法

#### 技能风险扫描

在技能被安装、集成或调用之前，扫描器联合检查自然语言声明、所需权限、依赖、可执行资源和跨技能数据流。

- (2026) [ClawVet: 6-Pass Security Scanner for OpenClaw Skills](https://www.npmjs.com/package/clawvet)
- (2026) [Agent Skills in the Wild / SkillScan](https://arxiv.org/abs/2601.10338)
- (2026) [SkillSieve](https://arxiv.org/abs/2604.06550)
- (2026) [SkillProbe: Security Auditing for Emerging Agent Skill Marketplaces via Multi-Agent Collaboration](https://arxiv.org/abs/2603.21019)

---

<a id="orchestration"></a>

## 2. 编排阶段（Orchestration）

在编排阶段，智能体理解用户请求、检索记忆、选择和组合技能、构建计划并准备工具调用。潜伏风险会在这一阶段通过上下文和控制流被激活和放大。

<a id="orchestration-risks"></a>

### 2.1 风险与攻击

#### 良性技能误用与组合风险

单个良性技能可能被对抗输入利用；多个单独良性的技能沿同一执行路径组合后，也可能产生越权、隐私泄露或破坏性行为。

- (2026) [SkillAttack: Automated Red Teaming of Agent Skills through Attack Path Refinement](https://arxiv.org/abs/2604.04989)
- (2026) [Benign in Isolation, Harmful in Composition: Security Risks in Agent Skill Ecosystems (SCR-Bench)](https://arxiv.org/abs/2606.15242)
- (2026) [OpenSkillRisk: Benchmarking Agent Safety When Using Real-World Risky Third-Party Skills](https://arxiv.org/abs/2607.20121)

#### 用户侧攻击

恶意用户通过直接交互接口提交有害任务、越狱提示、混淆上下文或多轮诱导，以绕过安全策略并触发高风险动作。

<details open>
<summary><b>人工越狱攻击</b></summary>

- (2024) [Refusal-Trained LLMs Are Easily Jailbroken as Browser Agents (BrowserART)](https://arxiv.org/abs/2410.13886)
- (2025) [Large Language Models Often Say One Thing and Do Another (WDCT)](https://arxiv.org/abs/2503.07003)
- (2024) [AgentHarm: A Benchmark for Measuring Harmfulness of LLM Agents](https://arxiv.org/abs/2410.09024)
- (2025) [The Dark Side of Function Calling: Pathways to Jailbreaking Large Language Models](https://aclanthology.org/2025.coling-main.39/)
- (2023) [Jailbroken: How Does LLM Safety Training Fail?](https://arxiv.org/abs/2307.02483)
- (2023) [DeepInception: Hypnotize Large Language Model to Be Jailbreaker](https://arxiv.org/abs/2311.03191)
- (2024) [EasyJailbreak: A Unified Framework for Jailbreaking Large Language Models](https://arxiv.org/abs/2403.12171)

</details>

<details>
<summary><b>启发式优化越狱攻击</b></summary>

- (2024) [Imprompter: Tricking LLM Agents into Improper Tool Use](https://arxiv.org/abs/2410.14923)
- (2025) [STAC: When Innocent Tools Form Dangerous Chains to Jailbreak LLM Agents](https://arxiv.org/abs/2509.25624)
- (2023) [Universal and Transferable Adversarial Attacks on Aligned Language Models (GCG)](https://arxiv.org/abs/2307.15043)
- (2023) [AutoDAN: Generating Stealthy Jailbreak Prompts on Aligned Large Language Models](https://arxiv.org/abs/2310.04451)
- (2023) [Jailbreaking Black Box Large Language Models in Twenty Queries (PAIR)](https://arxiv.org/abs/2310.08419)

</details>

<details>
<summary><b>智能体化自动红队</b></summary>

- (2025) [Agent vs. Agent: Automated Data Generation and Red-Teaming for Custom Agentic Workflows (Red-Agent-Reflect)](https://aclanthology.org/2025.emnlp-industry.62/)
- (2024) [RedAgent: Red Teaming Large Language Models with Context-Aware Autonomous Language Agent](https://arxiv.org/abs/2407.16667)
- (2025) [RedCodeAgent: Automatic Red-Teaming Agent against Diverse Code Agents](https://arxiv.org/abs/2510.02609)
- (2026) [TRACE: Task-Aware Adaptive Self-Evolving Agentic Jailbreaking](https://arxiv.org/abs/2605.30883)
- (2025) [X-Teaming: Multi-Turn Jailbreaks and Defenses with Adaptive Multi-Agents](https://arxiv.org/abs/2504.13203)

</details>

#### 记忆与长期状态风险

长期记忆会在未来任务中被自动检索并作为可信上下文复用，因此一次投毒事件就可能造成隐蔽、持久且可传播的行为操纵。

<details open>
<summary><b>直接记忆投毒</b></summary>

- (2024) [PoisonedRAG: Knowledge Corruption Attacks to Retrieval-Augmented Generation of Large Language Models](https://arxiv.org/abs/2409.02354)
- (2025) [Corpus Poisoning via Approximate Greedy Gradient Descent (AGGD)](https://aclanthology.org/2025.findings-acl.222/)
- (2025) [One Shot Dominance: Knowledge Poisoning Attack on Retrieval-Augmented Generation Systems (AuthChain)](https://aclanthology.org/2025.findings-emnlp.1023/)
- (2025) [Tricking Retrievers with Influential Tokens: An Efficient Black-Box Corpus Poisoning Attack (DIGA)](https://aclanthology.org/2025.naacl-long.210/)
- (2024) [HijackRAG: Hijacking Attacks against Retrieval-Augmented Large Language Models](https://arxiv.org/abs/2410.22832)
- (2025) [CPA-RAG: Covert Poisoning Attacks on Retrieval-Augmented Generation in Large Language Models](https://arxiv.org/abs/2505.19864)
- (2025) [Disabling Self-Correction in Retrieval-Augmented Generation via Stealthy Retriever Poisoning (Disarm-RAG)](https://arxiv.org/abs/2508.20083)
- (2024) [Typos That Broke the RAG's Back: Genetic Attack on RAG Pipeline (GARAG)](https://arxiv.org/abs/2404.13948)
- (2026) [KEPo: Knowledge Evolution Poison on Graph-Based Retrieval-Augmented Generation](https://arxiv.org/abs/2603.11501)
- (2025) [Topic-FlipRAG: Topic-Orientated Adversarial Opinion Manipulation Attacks to RAG](https://arxiv.org/abs/2502.01386)

</details>

<details>
<summary><b>基于交互的记忆注入与后门</b></summary>

- (2025) [Memory Injection Attacks on LLM Agents via Query-Only Interaction (MINJA)](https://arxiv.org/abs/2503.03704)
- (2026) [Poison Once, Exploit Forever: Environment-Injected Memory Poisoning Attacks on Web Agents (eTAMP)](https://arxiv.org/abs/2604.02623)
- (2024) [AgentPoison: Red-Teaming LLM Agents via Poisoning Memory or Knowledge Bases](https://arxiv.org/abs/2407.12784)
- (2025) [PR-Attack: Coordinated Prompt-RAG Attacks via Bilevel Optimization](https://arxiv.org/abs/2504.07717)

</details>

<a id="orchestration-evaluation"></a>

### 2.2 评测基准

#### 技能介导的智能体安全评测

给定用户任务和一个或多个技能，智能体在环境中执行任务，基准通过响应、执行证据或最终状态判断其行为是否安全。

- (2026) [Skill-Inject](https://arxiv.org/abs/2602.20156)
- (2026) [SkillSafetyBench](https://arxiv.org/abs/2605.12015)
- (2026) [SkillAttack](https://arxiv.org/abs/2604.04989)
- (2026) [SCR-Bench](https://arxiv.org/abs/2606.15242)
- (2026) [OpenSkillRisk](https://arxiv.org/abs/2607.20121)
- (2026) [HarmfulSkillBench: How Do Harmful Skills Weaponize Your Agents?](https://arxiv.org/abs/2604.15415)
- (2026) [BioSkillSafety: A Systematic Benchmark for Evaluating Agent Skill Safety in Bioinformatics](https://openreview.net/forum?id=iIQ8DOGu8S)
- (2026) [SkillHarm](https://arxiv.org/abs/2606.02540)
- (2026) [SkillTrojan](https://arxiv.org/abs/2604.06811)

<a id="orchestration-defense"></a>

### 2.3 防御方法

#### 提示注入与越狱护栏

边界检测器和安全分类器检查用户输入、检索内容、网页数据、工具输出和模型响应，避免不可信信号影响后续决策。

- (2025) [Llama Prompt Guard 2](https://github.com/meta-llama/PurpleLlama/tree/main/Llama-Prompt-Guard-2)
- (2025) [PIGuard: Prompt Injection Guardrail via Mitigating Overdefense for Free](https://aclanthology.org/2025.acl-long.1468/)
- (2023) [Llama Guard: LLM-Based Input-Output Safeguard for Human-AI Conversations](https://arxiv.org/abs/2312.06674)
- (2025) [Llama Guard 4](https://www.llama.com/docs/model-cards-and-prompt-formats/llama-guard-4/)
- (2025) [Aegis 2.0: A Diverse AI Safety Dataset and Risks Taxonomy for Alignment of LLM Guardrails](https://arxiv.org/abs/2501.09004)
- (2025) [SafeRoute: Adaptive Model Selection for Efficient and Accurate Safety Guardrails](https://aclanthology.org/2025.findings-acl.105/)
- (2025) [Qwen3Guard Technical Report](https://arxiv.org/abs/2510.14276)
- (2026) [SingGuard-NSFA: Extensible Guardrails for Agentic AI](https://arxiv.org/abs/2607.13081)
- (2025) [ShieldHead: Decoding-Time Safeguard for Large Language Models](https://aclanthology.org/2025.findings-acl.932/)

#### 记忆护栏

记忆防御通过来源验证、一致性检查、异常检测、因果审计和鲁棒性认证来治理记忆写入、检索、推理与恢复。

- (2025) [A-MemGuard: Defending against Memory Poisoning in LLM Agents](https://arxiv.org/abs/2510.02373)
- (2026) [Your Agent's Memories Are Not Its Own: Forged Reasoning Attacks on LLM Agent Memory and Defenses (SENTINEL)](https://arxiv.org/abs/2607.05029)
- (2026) [MEMSAD: Gradient-Coupled Anomaly Detection for Memory Poisoning in Retrieval-Augmented Agents](https://arxiv.org/abs/2605.03482)
- (2026) [MemShield: A Three-Tier Retrieval-Time Defense against Coordinated Memory Poisoning](https://arxiv.org/search/?query=%22MemShield%22&searchtype=all)
- (2026) [MIND: Memory Injection Defense via Intent-Aware Information Bottleneck](https://arxiv.org/abs/2607.28103)
- (2026) [MemAudit: Post-Hoc Auditing of Poisoned Agent Memory](https://arxiv.org/abs/2605.23723)
- (2026) [SMSR: Certified Defence against Runtime Memory Poisoning in Persistent LLM Agent Systems](https://arxiv.org/abs/2606.12703)

#### 决策与控制完整性

**Harness 外置防御**在模型之外重构或隔离不可信上下文，并通过任务对齐、工具依赖图和信息流控制约束规划过程。

- (2024) [Defending against Indirect Prompt Injection Attacks with Spotlighting](https://arxiv.org/abs/2403.14720)
- (2024) [StruQ: Defending against Prompt Injection with Structured Queries](https://arxiv.org/abs/2402.06363)
- (2024) [The Task Shield: Enforcing Task Alignment to Defend against Indirect Prompt Injection](https://arxiv.org/abs/2412.16682)
- (2025) [IPIGuard: A Tool Dependency Graph-Based Defense against Indirect Prompt Injection](https://aclanthology.org/2025.emnlp-main.53/)
- (2025) [Defeating Prompt Injections by Design (CaMeL)](https://arxiv.org/abs/2503.18813)

**模型对齐内化防御**通过指令层级训练、监督微调、偏好优化或强化学习，将信任优先级和安全工具使用策略内化到模型的决策策略中。

- (2024) [The Instruction Hierarchy: Training LLMs to Prioritize Privileged Instructions](https://arxiv.org/abs/2404.13208)
- (2024) [SecAlign: Defending against Prompt Injection with Preference Optimization](https://arxiv.org/abs/2410.05451)
- (2024) [Towards Tool Use Alignment of Large Language Models (ToolAlign)](https://aclanthology.org/2024.emnlp-main.82/)
- (2025) [AgentAlign: Navigating Safety Alignment in the Shift from Informative to Agentic LLMs](https://arxiv.org/abs/2505.23020)
- (2025) [ToolSafety: A Comprehensive Dataset for Enhancing Safety in LLM-Based Agent Tool Invocations](https://aclanthology.org/2025.emnlp-main.714/)
- (2025) [The Alignment Waltz: Jointly Training Agents to Collaborate for Safety](https://arxiv.org/abs/2510.08240)
- (2026) [On-Policy Self-Evolution via Failure Trajectories for Agentic Safety Alignment (FATE)](https://arxiv.org/abs/2605.11882)
- (2026) [ToolHazard: Scaling Adversarial Environments for Security Evaluation and Alignment of LLM-based Agents](https://arxiv.org/abs/2608.11878)

#### 规划阶段审计

在任何外部动作执行之前检查完整计划，以识别危险目标、权限违规和高风险动作组合。

- (2025) [Building a Foundational Guardrail for General Agentic Systems via Synthetic Data (Safiron)](https://arxiv.org/abs/2510.09781)

---

<a id="execution"></a>

## 3. 执行阶段（Execution）

在执行阶段，智能体提交工具调用和环境动作、观察其效果，并更新计划或内部状态。安全失败在这里转化为具有现实后果的行为，并可能产生能够跨任务留存的受污染工件。

<a id="execution-risks"></a>

### 3.1 风险与攻击

#### Web 注入攻击

恶意指令被嵌入 HTML、CSS、隐藏文本、图像、PDF、表单或其他页面元素，以劫持浏览智能体。

- (2025) [EIA: Environmental Injection Attack on Generalist Web Agents for Privacy Leakage](https://openreview.net/forum?id=xMOLUzo2Lk)
- (2025) [WASP: Benchmarking Web Agent Security against Prompt Injection Attacks](https://arxiv.org/abs/2504.18575)
- (2025) [WebInject: Prompt Injection Attack to Web Agents](https://aclanthology.org/2025.emnlp-main.104/)
- (2024) [Dissecting Adversarial Robustness of Multimodal LM Agents (VisualWebArena-Adv)](https://arxiv.org/abs/2406.12814)
- (2026) [MUZZLE: Adaptive Agentic Red-Teaming of Web Agents against Indirect Prompt Injection Attacks](https://arxiv.org/abs/2602.09222)

#### 计算机使用环境中的恶意注入

文件、终端输出、通知、弹窗、截图、按钮和移动端覆盖层会操纵 GUI 或操作系统智能体的感知、定位和系统操作。

- (2025) [OS-Harm: A Benchmark for Measuring Safety of Computer Use Agents](https://arxiv.org/abs/2506.14866)
- (2025) [RedTeamCUA: Realistic Adversarial Testing of Computer-Use Agents in Hybrid Web-OS Environments](https://arxiv.org/abs/2505.21936)
- (2025) [RiOSWorld: Benchmarking the Risk of Multimodal Computer-Use Agents](https://arxiv.org/abs/2506.00618)
- (2026) [AgentHazard: A Benchmark for Evaluating Harmful Behavior in Computer-Use Agents](https://arxiv.org/abs/2604.02947)
- (2025) ["Your AI, My Shell": Demystifying Prompt Injection Attacks on Agentic AI Coding Editors](https://arxiv.org/abs/2509.22040)
- (2025) [Attacking Vision-Language Computer Agents via Pop-Ups](https://aclanthology.org/2025.acl-long.411/)
- (2025) [Evaluating the Robustness of Multimodal Agents against Active Environmental Injection Attacks (AEIA)](https://arxiv.org/abs/2503.02539)

#### 工具输出注入

恶意指令通过搜索结果、API 响应、数据库记录、电子邮件、命令输出或 MCP 服务器响应进入上下文，并影响后续规划和动作。

- (2024) [InjecAgent: Benchmarking Indirect Prompt Injections in Tool-Integrated LLM Agents](https://arxiv.org/abs/2403.02691)
- (2024) [ToolSword: Unveiling Safety Issues of Large Language Models in Tool Learning across Three Stages](https://arxiv.org/abs/2402.10753)
- (2023) [Benchmarking and Defending against Indirect Prompt Injection Attacks on Large Language Models (BIPIA)](https://arxiv.org/abs/2312.14197)
- (2025) [Attractive Metadata Attack: Inducing LLM Agents to Invoke Malicious Tools (AMA)](https://arxiv.org/abs/2508.02110)
- (2025) [ChatInject: Abusing Chat Templates for Prompt Injection in LLM Agents](https://arxiv.org/abs/2509.22830)
- (2026) [AdapTools: Adaptive Tool-Based Indirect Prompt Injection Attacks on Agentic LLMs](https://arxiv.org/abs/2602.20720)

<a id="execution-evaluation"></a>

### 3.2 评测基准

以执行为中心的评测关注智能体是否实施不安全动作、沿攻击者控制的轨迹运行，或使环境进入有害终态；同时也包括对已记录轨迹和候选动作的离线审计。

<details open>
<summary><b>工具调用安全评测</b></summary>

- (2023) [Identifying the Risks of LM Agents with an LM-Emulated Sandbox (ToolEmu)](https://arxiv.org/abs/2309.15817)
- (2024) [InjecAgent](https://arxiv.org/abs/2403.02691)
- (2024) [ToolSword](https://arxiv.org/abs/2402.10753)
- (2024) [AgentHarm](https://arxiv.org/abs/2410.09024)
- (2024) [Agent-SafetyBench: Evaluating the Safety of LLM Agents](https://arxiv.org/abs/2412.14470)
- (2024) [HAICOSYSTEM: An Ecosystem for Sandboxing Safety Risks in Human-AI Interactions](https://arxiv.org/abs/2409.16427)
- (2024) [AgentDojo: A Dynamic Environment to Evaluate Prompt Injection Attacks and Defenses for LLM Agents](https://arxiv.org/abs/2406.13352)
- (2024) [Agent Security Bench (ASB)](https://arxiv.org/abs/2410.02644)
- (2025) [MCP-SafetyBench](https://arxiv.org/abs/2512.15163)
- (2025) [MCP Security Bench (MSB)](https://arxiv.org/abs/2510.15994)
- (2025) [MCPSecBench](https://arxiv.org/abs/2508.13220)
- (2026) [AgentLAB: Benchmarking LLM Agents against Long-Horizon Attacks](https://arxiv.org/abs/2602.16901)

</details>

<details>
<summary><b>Web 浏览行为安全评测</b></summary>

- (2025) [WASP: Benchmarking Web Agent Security against Prompt Injection Attacks](https://arxiv.org/abs/2504.18575)
- (2024) [ST-WebAgentBench: A Benchmark for Evaluating Safety and Trustworthiness in Web Agents](https://arxiv.org/abs/2410.06703)
- (2025) [SafeArena: Evaluating the Safety of Autonomous Web Agents](https://arxiv.org/abs/2503.04957)

</details>

<details>
<summary><b>计算机与移动端行为安全评测</b></summary>

- (2025) [OS-Harm](https://arxiv.org/abs/2506.14866)
- (2025) [RiOSWorld](https://arxiv.org/abs/2506.00618)
- (2025) [RedTeamCUA / RTC-Bench](https://arxiv.org/abs/2505.21936)
- (2026) [AgentHazard](https://arxiv.org/abs/2604.02947)
- (2024) [MobileSafetyBench: Evaluating Safety of Autonomous Agents in Mobile Device Control](https://arxiv.org/abs/2410.17520)
- (2025) [GhostEI-Bench: Environmental Injection in Dynamic On-Device Environments](https://arxiv.org/abs/2510.20333)

</details>

<details>
<summary><b>轨迹级安全检测</b></summary>

将完整的多步交互记录提供给安全判别器，要求其发现逐步形成的风险、定位危险步骤并解释因果链。

- (2024) [R-Judge: Benchmarking Safety Risk Awareness for LLM Agents](https://arxiv.org/abs/2401.10019)
- (2025) [AgentAuditor: Human-Level Safety and Security Evaluation for LLM Agents (ASSEBench)](https://arxiv.org/abs/2506.00641)
- (2026) [ATBench: A Diverse and Realistic Agent Trajectory Benchmark for Safety Evaluation and Diagnosis](https://arxiv.org/abs/2604.02022)

</details>

<details>
<summary><b>步骤级安全检测</b></summary>

给定当前上下文和候选动作，评测器在执行前判断动作应被允许、阻止，还是需要进一步验证。

- (2025) [AGrail: A Lifelong Agent Guardrail with Effective and Adaptive Safety Detection (Safe-OS)](https://arxiv.org/abs/2502.11448)
- (2025) [ShieldAgent: Shielding Agents via Verifiable Safety Policy Reasoning (ShieldAgent-Bench)](https://arxiv.org/abs/2503.22738)
- (2026) [ToolSafe: Enhancing Tool Invocation Safety via Proactive Step-Level Guardrail and Feedback (TS-Bench)](https://arxiv.org/abs/2601.10156)

</details>

<a id="execution-defense"></a>

### 3.3 防御方法

#### 步骤级监控与执行约束

在每次工具调用或环境动作真正提交之前，监控器检查当前状态、动作语义和参数，并选择阻止、修正、确认或形式化验证。

- (2025) [AGrail](https://arxiv.org/abs/2502.11448)
- (2024) [GuardAgent: Safeguard LLM Agents by a Guard Agent via Knowledge-Enabled Reasoning](https://arxiv.org/abs/2406.09187)
- (2025) [ShieldAgent](https://arxiv.org/abs/2503.22738)
- (2025) [Think Twice before You Act: Enhancing Agent Behavioral Safety with Thought Correction (Thought-Aligner)](https://arxiv.org/abs/2505.11063)
- (2026) [Safety Sidecar: Reflection-Driven Runtime Control for Safer Agents](https://aclanthology.org/2026.findings-acl.1542/)
- (2025) [OS-Sentinel: Safety-Enhanced Mobile GUI Agents via Hybrid Validation](https://arxiv.org/abs/2510.24411)
- (2026) [ToolSafe](https://arxiv.org/abs/2601.10156)
- (2025) [LlamaFirewall: An Open Source Guardrail System for Building Secure AI Agents](https://arxiv.org/abs/2505.03574)
- (2025) [VeriGuard: Enhancing LLM Agent Safety via Verified Code Generation](https://arxiv.org/abs/2510.05156)
- (2026) [VIGIL: Defending LLM Agents against Tool Stream Injection via Verify-Before-Commit](https://arxiv.org/abs/2601.05755)

#### 轨迹级复核

分析部分或完整执行历史，以识别跨步骤权限升级、跨工具信息泄露和累积性策略违规，并支持根因诊断与持续改进。

- (2025) [AgentAuditor](https://arxiv.org/abs/2506.00641)
- (2026) [AgentDoG 1.5: A Lightweight and Scalable Alignment Framework for AI Agent Safety and Security](https://arxiv.org/abs/2605.29801)
- (2026) [BraveGuard: From Open-World Threats to Safer Computer-Use Agents](https://arxiv.org/abs/2606.01166)

---

<a id="persistent-feedback"></a>

## 4. 持久反馈与研究展望

执行并不是生命周期的终点。智能体动作可能更新长期记忆、改写可复用技能，或留下将在未来工作流中重新成为输入的工件。因此，综述将未来研究组织为一个闭环安全过程：

<a id="self-evolving-agent-safety"></a>

### 自进化智能体安全代表性工作

论文 Introduction 重点引用了三项研究，它们直接讨论智能体自主更新模型、记忆、工具、工作流或经验积累机制时可能出现的安全失效：

- (2026) [Safety in Self-Evolving LLM Agent Systems: Threats, Amplification, and Case Studies](https://arxiv.org/abs/2606.23075) — 分析自进化原生攻击面，包括恶意影响的持久编码、跨代放大，以及风险在自修改智能体系统中的传播。
- (2025) [Your Agent May Misevolve: Emergent Risks in Self-Evolving LLM Agents](https://arxiv.org/abs/2509.26354) — 提出 **misevolution（错误进化）**概念，并从模型、记忆、工具和工作流四条进化路径研究涌现式安全失效。
- (2026) [Large Language Model Agents Are Not Always Faithful Self-Evolvers](https://arxiv.org/abs/2601.22436) — 研究**经验忠实性（experience faithfulness）**，揭示自进化智能体可能忽视或误解原本用于指导后续行为的压缩经验。

这些工作共同表明，自进化带来的不只是更大的静态攻击面：安全失败可能被持久化、随时间放大，并使能力提升与可靠、安全的行为逐渐解耦。

1. **风险生成**——自动构造可执行、可验证且持续演化的对抗环境和安全数据。
2. **风险诊断**——沿长程交互轨迹，将安全失败归因到具体阶段、步骤、工具、参数或状态转移。
3. **安全演化**——将新发现的攻击和已诊断的失败轨迹转化为反馈，实现持续、稳定且具备泛化能力的安全策略更新。

这一闭环连接了对抗环境生成、细粒度轨迹归因和对抗反馈驱动的持续安全演化，目标是支持更安全的递归自我改进。

## 仓库说明

- 文献列表依据综述 **Figure 2** 以及评测与防御相关表格整理。
- 年份表示论文首次公开发布的年份。
- 链接优先指向 arXiv、OpenReview、ACL Anthology、官方项目页和官方代码仓库。
- 同一篇论文可能同时提出攻击、基准和防御，因此可能在多个类别中出现。
- 两张核心图的版权归原作者所有，本仓库仅将其用于介绍配套综述的分类体系。

## 引用

如果本仓库对您的研究有所帮助，请引用综述及您实际使用的原始论文：

> Yutao Mou, Dingyao Yu, Xiaotian Luan, Zhe Yin, Zhangchi Xue, Peiyang Liu, Pengfei Yang, Tong Zhang, Shikun Zhang, and Wei Ye. **Pandora's Toolbox: A Survey of Generalist Agent Security from the Lifecycle Perspective.** 2026.

正式的 BibTeX 条目将在公开预印本记录发布后补充。

## 参与贡献

欢迎通过 Issue 或 Pull Request 补充新论文、代码仓库、数据集或勘误。请先确定条目的主要生命周期阶段与安全研究视角，再使用以下格式：

```markdown
- (Year) [Paper Title](Paper URL)
```

如果一项工作跨越多个阶段，应优先放置在风险主要引入、安全证据主要收集，或防御措施主要介入的阶段；当跨类别列出能够显著提升检索体验时，也欢迎进行交叉收录。

---

<div align="center">

**来源 → 编排 → 执行 → 持久反馈**

</div>
