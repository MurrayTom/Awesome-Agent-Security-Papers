<h1 align="center">Pandora's Toolbox: Generalist Agent Security Paper List</h1>

<div align="center">

**通用智能体安全：攻击面、评测基准与防御方法文献索引**

[中文](./README.md) | [English](./README_EN.md)

[综述 PDF](./Pandora-agent-survey.pdf) · [参考 README](./README_reference.md)

</div>

## 🌟 Overview

本仓库整理综述 *Pandora's Toolbox: A Survey of Security Risks, Attacks, Evaluation, and Defenses for Generalist Agents* 的分类法与代表性研究，面向通用智能体（generalist agents）的安全文献调研。

综述以智能体运行时生命周期为主线，将生命周期划分为 **来源（provenance）—编排（orchestration）—执行（execution）** 三个阶段，并从以下三个维度组织研究：

1. **安全风险与攻击**：技能供应链、用户输入、长期记忆、外部环境四类攻击面；
2. **安全评测**：领域专用智能体、通用智能体、离线轨迹审计三条评测主线；
3. **安全防御**：输入与上下文过滤、决策与控制完整性、运行时监控与执行约束三层防线。

> 本列表依据综述 Figure 2 及 Tables 2–9 整理。论文可能同时提出攻击、基准与防御，因此会出现在多个类别中。年份采用论文首次公开年份；链接优先指向 arXiv、OpenReview、ACL Anthology 或项目主页。

## 🧭 Taxonomy at a Glance

| 研究维度 | 一级分类 | 二级分类 |
|---|---|---|
| 风险与攻击 | 技能供应链攻击 | 声明式技能文件投毒；多组件技能生态投毒；良性技能误用与组合风险；跨会话技能重写与后门触发 |
| 风险与攻击 | 用户侧攻击 | 人工越狱；启发式优化越狱；智能体化自动红队 |
| 风险与攻击 | 长期记忆风险 | 直接长期记忆投毒；基于交互的间接记忆注入；后门攻击 |
| 风险与攻击 | 环境侧攻击 | Web 注入；计算机使用环境恶意注入；工具输出注入 |
| 安全评测 | 领域专用智能体基准 | 工具调用；Web 浏览；计算机与移动端操作 |
| 安全评测 | 通用智能体基准 | 基于技能的行为安全；恶意技能检测 |
| 安全评测 | 离线轨迹审计 | 轨迹级安全检测；步骤级安全检测 |
| 安全防御 | 输入与上下文过滤 | 技能风险扫描；提示注入与越狱护栏；记忆护栏 |
| 安全防御 | 决策与控制完整性 | Harness 外置防御；模型对齐内化防御 |
| 安全防御 | 运行时监控与执行约束 | 规划阶段审计；步骤级监控；轨迹级复核 |

<details open>
  <summary><b>📂 Table of Contents</b>（点击展开/折叠）</summary>
  <ul>
    <li><a href="#security-risks-and-attacks">Security Risks and Attacks</a>
      <ul>
        <li><a href="#skill-supply-chain-attacks">Skill Supply-Chain Attacks</a></li>
        <li><a href="#user-side-attacks">User-Side Attacks</a></li>
        <li><a href="#long-term-memory-risks">Long-Term Memory Risks</a></li>
        <li><a href="#environment-side-attacks">Environment-Side Attacks</a></li>
      </ul>
    </li>
    <li><a href="#security-evaluation-benchmarks">Security Evaluation Benchmarks</a>
      <ul>
        <li><a href="#domain-specific-agent-safety-benchmarks">Domain-Specific Agent Safety Benchmarks</a></li>
        <li><a href="#generalist-agent-safety-benchmarks">Generalist Agent Safety Benchmarks</a></li>
        <li><a href="#offline-trajectory-auditing">Offline Trajectory Auditing</a></li>
      </ul>
    </li>
    <li><a href="#security-defense-methods">Security Defense Methods</a>
      <ul>
        <li><a href="#input-and-context-filtering">Input and Context Filtering</a></li>
        <li><a href="#decision-and-control-integrity">Decision and Control Integrity</a></li>
        <li><a href="#runtime-monitoring-and-enforcement">Runtime Monitoring and Enforcement</a></li>
      </ul>
    </li>
    <li><a href="#research-outlook">Research Outlook</a></li>
  </ul>
</details>

---

<a id="security-risks-and-attacks"></a>

# 1. Security Risks and Attacks

<a id="skill-supply-chain-attacks"></a>

## 1.1 Skill Supply-Chain Attacks（技能供应链攻击）

技能由第三方开发并可被智能体自主选择和加载，风险可存在于元数据、`SKILL.md`、脚本、依赖、配置、检索资源及跨会话持久状态中。

### Declarative Skill File Poisoning（声明式技能文件投毒）

攻击者污染技能元数据、说明、示例或触发规则，使恶意自然语言指令进入规划上下文。

- (2026) [Skill-Inject: Measuring Agent Vulnerability to Skill File Attacks](https://arxiv.org/abs/2602.20156)
- (2026) [Supply-Chain Poisoning Attacks Against LLM Coding Agent Skill Ecosystems (PoisonedSkills)](https://arxiv.org/abs/2604.03081)
- (2026) [SkillJect: Effectively Automating Skill-Based Prompt Injection for Skill-Enabled Agents](https://arxiv.org/abs/2602.14211)
- (2026) [Under the Hood of SKILL.md: Semantic Supply-Chain Attacks on AI Agent Skill Registry](https://arxiv.org/abs/2605.11418)

### Multi-Component Skill Ecosystem Poisoning（多组件技能生态投毒）

攻击面从主技能文件扩展到辅助脚本、工具接口、依赖、外部资产、配置文件、RAG 数据库和本地缓存。

- (2026) [SkillSafetyBench: Evaluating Agent Safety under Skill-Facing Attack Surfaces](https://arxiv.org/abs/2605.12015)
- (2026) [Skill-Inject: Measuring Agent Vulnerability to Skill File Attacks](https://arxiv.org/abs/2602.20156)
- (2026) [Proteus: A Self-Evolving Red Team for Agent Skill Ecosystems](https://arxiv.org/abs/2605.11891)

### Benign Skill Misuse and Compositional Risks（良性技能误用与组合风险）

单个技能可能本身无恶意载荷，却能被对抗输入利用；多个单独良性的技能在共享执行路径中组合后，也可能形成越权、泄露或破坏性行为。

- (2026) [SkillAttack: Automated Red Teaming of Agent Skills through Attack Path Refinement](https://arxiv.org/abs/2604.04989)
- (2026) [Benign in Isolation, Harmful in Composition: Security Risks in Agent Skill Ecosystems (SCR-Bench)](https://arxiv.org/abs/2606.15242)
- (2026) [OpenSkillRisk: Benchmarking Agent Safety When Using Real-World Risky Third-Party Skills](https://arxiv.org/abs/2607.20121)

### Cross-Session Skill Rewriting and Backdoor Triggering（跨会话技能重写与后门触发）

攻击在当前会话中修改技能文件、缓存、项目制品或依赖，恶意行为在后续会话或特定触发条件下才激活。

- (2026) [SkillHarm: Lifecycle-Aware Skill-Based Attacks via Automated Construction](https://arxiv.org/abs/2606.02540)
- (2026) [SkillTrojan: Backdoor Attacks on Skill-Based Agent Systems](https://arxiv.org/abs/2604.06811)

<a id="user-side-attacks"></a>

## 1.2 User-Side Attacks（用户侧攻击）

恶意用户通过直接交互界面提交有害任务、越狱提示、混淆上下文或多轮诱导，使智能体绕过安全策略并执行高风险操作。

### Manual Jailbreak Attacks（人工越狱攻击）

依赖人工设计的模板，通过角色扮演、拒答抑制、场景伪装、编码转换、载荷拆分或少样本示例重述恶意请求。

- (2024) [Refusal-Trained LLMs Are Easily Jailbroken as Browser Agents (BrowserART)](https://arxiv.org/abs/2410.13886)
- (2025) [Large Language Models Often Say One Thing and Do Another (WDCT)](https://arxiv.org/abs/2503.07003)
- (2024) [AgentHarm: A Benchmark for Measuring Harmfulness of LLM Agents](https://arxiv.org/abs/2410.09024)
- (2025) [The Dark Side of Function Calling: Pathways to Jailbreaking Large Language Models](https://aclanthology.org/2025.coling-main.39/)
- (2023) [Jailbroken: How Does LLM Safety Training Fail?](https://arxiv.org/abs/2307.02483)
- (2023) [DeepInception: Hypnotize Large Language Model to Be Jailbreaker](https://arxiv.org/abs/2311.03191)
- (2024) [EasyJailbreak: A Unified Framework for Jailbreaking Large Language Models](https://arxiv.org/abs/2403.12171)

### Heuristic Optimization-Based Jailbreak Attacks（启发式优化越狱）

将越狱提示构造转化为搜索或优化问题，利用梯度搜索、遗传算法、黑盒迭代或提示变异自动生成攻击输入。

- (2024) [Imprompter: Tricking LLM Agents into Improper Tool Use](https://arxiv.org/abs/2410.14923)
- (2025) [STAC: When Innocent Tools Form Dangerous Chains to Jailbreak LLM Agents](https://arxiv.org/abs/2509.25624)
- (2023) [Universal and Transferable Adversarial Attacks on Aligned Language Models (GCG)](https://arxiv.org/abs/2307.15043)
- (2023) [AutoDAN: Generating Stealthy Jailbreak Prompts on Aligned Large Language Models](https://arxiv.org/abs/2310.04451)
- (2023) [Jailbreaking Black Box Large Language Models in Twenty Queries (PAIR)](https://arxiv.org/abs/2310.08419)

### Agentic Red-Teaming for Jailbreak（智能体化自动红队）

攻击智能体通过任务分解、反馈评估、自我反思、记忆和多轮优化，自主寻找能诱导目标智能体完成复杂有害任务的策略。

- (2025) [Agent vs. Agent: Automated Data Generation and Red-Teaming for Custom Agentic Workflows (Red-Agent-Reflect)](https://aclanthology.org/2025.emnlp-industry.62/)
- (2024) [RedAgent: Red Teaming Large Language Models with Context-Aware Autonomous Language Agent](https://arxiv.org/abs/2407.16667)
- (2025) [RedCodeAgent: Automatic Red-Teaming Agent against Diverse Code Agents](https://arxiv.org/abs/2510.02609)
- (2026) [TRACE: Task-Aware Adaptive Self-Evolving Agentic Jailbreaking](https://arxiv.org/abs/2605.30883)
- (2025) [X-Teaming: Multi-Turn Jailbreaks and Defenses with Adaptive Multi-Agents](https://arxiv.org/abs/2504.13203)

<a id="long-term-memory-risks"></a>

## 1.3 Long-Term Memory Risks（长期记忆风险）

长期记忆会在未来会话中被自动检索并作为可信上下文重复使用，因此一次投毒可能形成隐蔽、持久且可传播的行为操纵。

### Direct Long-Term Memory Poisoning（直接长期记忆投毒）

攻击者直接污染 RAG 语料、知识库、检索索引、图结构或检索证据，使恶意内容在未来查询中被召回。

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

### Indirect Interaction-Based Memory Injection（基于交互的间接记忆注入）

攻击者不直接修改存储，而是通过正常对话、查询、网页观察或环境内容，诱导智能体把恶意信息写入长期记忆。

- (2025) [Memory Injection Attacks on LLM Agents via Query-Only Interaction (MINJA)](https://arxiv.org/abs/2503.03704)
- (2026) [Poison Once, Exploit Forever: Environment-Injected Memory Poisoning Attacks on Web Agents (eTAMP)](https://arxiv.org/abs/2604.02623)

### Backdoor Attacks（后门攻击）

恶意记忆在普通输入下保持休眠，仅在特定触发词、目标查询、主题或上下文模式出现时执行定向操纵。

- (2024) [AgentPoison: Red-Teaming LLM Agents via Poisoning Memory or Knowledge Bases](https://arxiv.org/abs/2407.12784)
- (2025) [PR-Attack: Coordinated Prompt-RAG Attacks via Bilevel Optimization](https://arxiv.org/abs/2504.07717)

<a id="environment-side-attacks"></a>

## 1.4 Environment-Side Attacks（环境侧攻击）

攻击者操纵智能体所感知的网页、文档、GUI、终端、API 或工具返回值，使非可信数据被误当作高优先级指令。

### Web Injection Attacks（Web 注入攻击）

恶意指令被嵌入 HTML、CSS、隐藏文本、图片、PDF、表单或其他网页元素，进而劫持浏览智能体。

- (2025) [EIA: Environmental Injection Attack on Generalist Web Agents for Privacy Leakage](https://openreview.net/forum?id=xMOLUzo2Lk)
- (2025) [WASP: Benchmarking Web Agent Security against Prompt Injection Attacks](https://arxiv.org/abs/2504.18575)
- (2025) [WebInject: Prompt Injection Attack to Web Agents](https://aclanthology.org/2025.emnlp-main.104/)
- (2024) [Dissecting Adversarial Robustness of Multimodal LM Agents (VisualWebArena-Adv)](https://arxiv.org/abs/2406.12814)
- (2026) [MUZZLE: Adaptive Agentic Red-Teaming of Web Agents against Indirect Prompt Injection Attacks](https://arxiv.org/abs/2602.09222)

### Malicious Injection in Computer-Use Environments（计算机使用环境恶意注入）

通过文件、终端输出、通知、弹窗、截图、按钮或移动端覆盖层操纵 GUI/OS 智能体的感知、定位与系统操作。

- (2025) [OS-Harm: A Benchmark for Measuring Safety of Computer Use Agents](https://arxiv.org/abs/2506.14866)
- (2025) [RedTeamCUA: Realistic Adversarial Testing of Computer-Use Agents in Hybrid Web-OS Environments](https://arxiv.org/abs/2505.21936)
- (2025) [RiOSWorld: Benchmarking the Risk of Multimodal Computer-Use Agents](https://arxiv.org/abs/2506.00618)
- (2026) [AgentHazard: A Benchmark for Evaluating Harmful Behavior in Computer-Use Agents](https://arxiv.org/abs/2604.02947)
- (2025) ["Your AI, My Shell": Demystifying Prompt Injection Attacks on Agentic AI Coding Editors](https://arxiv.org/abs/2509.22040)
- (2025) [Attacking Vision-Language Computer Agents via Pop-Ups](https://aclanthology.org/2025.acl-long.411/)
- (2025) [Evaluating the Robustness of Multimodal Agents against Active Environmental Injection Attacks (AEIA)](https://arxiv.org/abs/2503.02539)

### Tool-Output Injection（工具输出注入）

恶意指令来自搜索结果、API 响应、数据库记录、邮件、命令输出或 MCP 服务返回值，并影响后续规划和工具调用。

- (2024) [InjecAgent: Benchmarking Indirect Prompt Injections in Tool-Integrated LLM Agents](https://arxiv.org/abs/2403.02691)
- (2024) [ToolSword: Unveiling Safety Issues of Large Language Models in Tool Learning across Three Stages](https://arxiv.org/abs/2402.10753)
- (2023) [Benchmarking and Defending against Indirect Prompt Injection Attacks on Large Language Models (BIPIA)](https://arxiv.org/abs/2312.14197)
- (2025) [Attractive Metadata Attack: Inducing LLM Agents to Invoke Malicious Tools (AMA)](https://arxiv.org/abs/2508.02110)
- (2025) [ChatInject: Abusing Chat Templates for Prompt Injection in LLM Agents](https://arxiv.org/abs/2509.22830)
- (2026) [AdapTools: Adaptive Tool-Based Indirect Prompt Injection Attacks on Agentic LLMs](https://arxiv.org/abs/2602.20720)

---

<a id="security-evaluation-benchmarks"></a>

# 2. Security Evaluation Benchmarks

安全评测已从静态回复检测转向行为级评估：不仅判断智能体是否生成有害文本，还检查其工具调用、交互轨迹和最终环境状态是否安全。

<a id="domain-specific-agent-safety-benchmarks"></a>

## 2.1 Domain-Specific Agent Safety Benchmarks（领域专用智能体安全基准）

### Tool-Use Safety Benchmarks（工具调用安全）

评测恶意用户请求、工具输出注入、工具/协议元数据投毒、危险参数以及最终执行状态。

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

### Web-Browsing Safety Benchmarks（Web 浏览安全）

评测网页间接提示注入、恶意用户滥用、策略违规、页面级攻击目标完成度及最终网页状态。

- (2025) [WASP: Benchmarking Web Agent Security against Prompt Injection Attacks](https://arxiv.org/abs/2504.18575)
- (2024) [ST-WebAgentBench: A Benchmark for Evaluating Safety and Trustworthiness in Web Agents](https://arxiv.org/abs/2410.06703)
- (2025) [SafeArena: Evaluating the Safety of Autonomous Web Agents](https://arxiv.org/abs/2503.04957)

### Computer and Mobile Operation Safety Benchmarks（计算机与移动端操作安全）

评测 GUI 感知、跨应用交互、文件与终端操作、敏感权限、不可逆动作和持久环境副作用。

- (2025) [OS-Harm](https://arxiv.org/abs/2506.14866)
- (2025) [RiOSWorld](https://arxiv.org/abs/2506.00618)
- (2025) [RedTeamCUA / RTC-Bench](https://arxiv.org/abs/2505.21936)
- (2026) [AgentHazard](https://arxiv.org/abs/2604.02947)
- (2024) [MobileSafetyBench: Evaluating Safety of Autonomous Agents in Mobile Device Control](https://arxiv.org/abs/2410.17520)
- (2025) [GhostEI-Bench: Environmental Injection in Dynamic On-Device Environments](https://arxiv.org/abs/2510.20333)

<a id="generalist-agent-safety-benchmarks"></a>

## 2.2 Generalist Agent Safety Benchmarks（通用智能体安全基准）

### Skill-Based Agent Behavioral Safety Benchmarks（基于技能的行为安全）

给定用户任务和一个或多个技能，让智能体真实执行任务，并依据回复、工具证据或最终状态判断技能介导的执行是否安全。

- (2026) [Skill-Inject](https://arxiv.org/abs/2602.20156)
- (2026) [SkillSafetyBench](https://arxiv.org/abs/2605.12015)
- (2026) [SkillAttack](https://arxiv.org/abs/2604.04989)
- (2026) [SCR-Bench](https://arxiv.org/abs/2606.15242)
- (2026) [OpenSkillRisk](https://arxiv.org/abs/2607.20121)
- (2026) [HarmfulSkillBench: How Do Harmful Skills Weaponize Your Agents?](https://arxiv.org/abs/2604.15415)
- (2026) [BioSkillSafety: A Systematic Benchmark for Evaluating Agent Skill Safety in Bioinformatics](https://openreview.net/forum?id=iIQ8DOGu8S)
- (2026) [SkillHarm](https://arxiv.org/abs/2606.02540)
- (2026) [SkillTrojan](https://arxiv.org/abs/2604.06811)

### Malicious Skill Detection Benchmarks（恶意技能检测）

不执行用户任务，而是让规则、模型、静态分析器或验证器检查技能包本身，评测其对语义级、代码级和混合攻击的检测能力。

- (2026) [Agent Skills in the Wild: An Empirical Study of Security Vulnerabilities at Scale](https://arxiv.org/abs/2601.10338)
- (2026) [SkillSieve: A Hierarchical Triage Framework for Detecting Malicious AI Agent Skills](https://arxiv.org/abs/2604.06550)
- (2026) [MalSkillBench: A Runtime-Verified Benchmark of Malicious Agent Skills](https://arxiv.org/abs/2606.07131)
- (2026) [SkillsMetric: Mapping the Detection Boundary of Static Analysis for Malicious Agent Skills](https://arxiv.org/abs/2608.08468)

<a id="offline-trajectory-auditing"></a>

## 2.3 Offline Trajectory Auditing（离线轨迹审计）

### Trajectory-Level Safety Detection（轨迹级安全检测）

输入完整多步交互记录，评测安全评判器能否发现渐进式风险、定位危险步骤并解释因果链。

- (2024) [R-Judge: Benchmarking Safety Risk Awareness for LLM Agents](https://arxiv.org/abs/2401.10019)
- (2025) [AgentAuditor: Human-Level Safety and Security Evaluation for LLM Agents (ASSEBench)](https://arxiv.org/abs/2506.00641)
- (2026) [ATBench: A Diverse and Realistic Agent Trajectory Benchmark for Safety Evaluation and Diagnosis](https://arxiv.org/abs/2604.02022)

### Step-Level Safety Detection（步骤级安全检测）

输入当前上下文与候选动作，在执行前判断单个浏览、代码或工具调用是否应允许、阻止或进一步验证。

- (2025) [AGrail: A Lifelong Agent Guardrail with Effective and Adaptive Safety Detection (Safe-OS)](https://arxiv.org/abs/2502.11448)
- (2025) [ShieldAgent: Shielding Agents via Verifiable Safety Policy Reasoning (ShieldAgent-Bench)](https://arxiv.org/abs/2503.22738)
- (2026) [ToolSafe: Enhancing Tool Invocation Safety via Proactive Step-Level Guardrail and Feedback (TS-Bench)](https://arxiv.org/abs/2601.10156)

---

<a id="security-defense-methods"></a>

# 3. Security Defense Methods

<a id="input-and-context-filtering"></a>

## 3.1 Input and Context Filtering（输入与上下文过滤）

### Skill Risk Scanning（技能风险扫描）

在安装、集成或调用技能前，联合检查自然语言声明、权限、依赖、可执行脚本及跨技能数据流。

- (2026) [ClawVet: 6-Pass Security Scanner for OpenClaw Skills](https://www.npmjs.com/package/clawvet)
- (2026) [Agent Skills in the Wild / SkillScan](https://arxiv.org/abs/2601.10338)
- (2026) [SkillSieve](https://arxiv.org/abs/2604.06550)
- (2026) [SkillProbe: Security Auditing for Emerging Agent Skill Marketplaces via Multi-Agent Collaboration](https://arxiv.org/abs/2603.21019)

### Prompt Injection and Jailbreak Guardrails（提示注入与越狱护栏）

在用户输入、检索内容、网页数据、工具输出和模型回复等边界部署轻量检测器或安全分类器。

- (2025) [Llama Prompt Guard 2](https://github.com/meta-llama/PurpleLlama/tree/main/Llama-Prompt-Guard-2)
- (2025) [PIGuard: Prompt Injection Guardrail via Mitigating Overdefense for Free](https://aclanthology.org/2025.acl-long.1468/)
- (2023) [Llama Guard: LLM-Based Input-Output Safeguard for Human-AI Conversations](https://arxiv.org/abs/2312.06674)
- (2025) [Llama Guard 4](https://www.llama.com/docs/model-cards-and-prompt-formats/llama-guard-4/)
- (2025) [Aegis 2.0: A Diverse AI Safety Dataset and Risks Taxonomy for Alignment of LLM Guardrails](https://arxiv.org/abs/2501.09004)
- (2025) [SafeRoute: Adaptive Model Selection for Efficient and Accurate Safety Guardrails](https://aclanthology.org/2025.findings-acl.105/)
- (2025) [Qwen3Guard Technical Report](https://arxiv.org/abs/2510.14276)
- (2026) [SingGuard-NSFA: Extensible Guardrails for Agentic AI](https://arxiv.org/abs/2607.13081)
- (2025) [ShieldHead: Decoding-Time Safeguard for Large Language Models](https://aclanthology.org/2025.findings-acl.932/)

### Memory Guardrails（记忆护栏）

覆盖记忆写入、检索、推理和恢复阶段，结合来源验证、一致性检查、异常检测、因果审计与鲁棒性认证。

- (2025) [A-MemGuard: Defending against Memory Poisoning in LLM Agents](https://arxiv.org/abs/2510.02373)
- (2026) [Your Agent's Memories Are Not Its Own: Forged Reasoning Attacks on LLM Agent Memory and Defenses (SENTINEL)](https://arxiv.org/abs/2607.05029)
- (2026) [MEMSAD: Gradient-Coupled Anomaly Detection for Memory Poisoning in Retrieval-Augmented Agents](https://arxiv.org/abs/2605.03482)
- (2026) [MemShield: A Three-Tier Retrieval-Time Defense against Coordinated Memory Poisoning](https://arxiv.org/search/?query=%22MemShield%22&searchtype=all)
- (2026) [MIND: Memory Injection Defense via Intent-Aware Information Bottleneck](https://arxiv.org/abs/2607.28103)
- (2026) [MemAudit: Post-Hoc Auditing of Poisoned Agent Memory](https://arxiv.org/abs/2605.23723)
- (2026) [SMSR: Certified Defence against Runtime Memory Poisoning in Persistent LLM Agent Systems](https://arxiv.org/abs/2606.12703)

<a id="decision-and-control-integrity"></a>

## 3.2 Decision and Control Integrity（决策与控制完整性）

### Harness-Externalized Defenses（Harness 外置防御）

在模型外部的编排层重构或隔离不可信上下文，并以任务对齐、工具依赖图、信息流控制等方式约束规划和控制流。

- (2024) [Defending against Indirect Prompt Injection Attacks with Spotlighting](https://arxiv.org/abs/2403.14720)
- (2024) [StruQ: Defending against Prompt Injection with Structured Queries](https://arxiv.org/abs/2402.06363)
- (2024) [The Task Shield: Enforcing Task Alignment to Defend against Indirect Prompt Injection](https://arxiv.org/abs/2412.16682)
- (2025) [IPIGuard: A Tool Dependency Graph-Based Defense against Indirect Prompt Injection](https://aclanthology.org/2025.emnlp-main.53/)
- (2025) [Defeating Prompt Injections by Design (CaMeL)](https://arxiv.org/abs/2503.18813)

### Alignment-Internalized Defenses（模型对齐内化防御）

通过指令层级训练、监督微调、偏好优化或强化学习，把可信优先级和安全工具使用策略内化到模型决策策略中。

- (2024) [The Instruction Hierarchy: Training LLMs to Prioritize Privileged Instructions](https://arxiv.org/abs/2404.13208)
- (2024) [SecAlign: Defending against Prompt Injection with Preference Optimization](https://arxiv.org/abs/2410.05451)
- (2024) [Towards Tool Use Alignment of Large Language Models (ToolAlign)](https://aclanthology.org/2024.emnlp-main.82/)
- (2025) [AgentAlign: Navigating Safety Alignment in the Shift from Informative to Agentic LLMs](https://arxiv.org/abs/2505.23020)
- (2025) [ToolSafety: A Comprehensive Dataset for Enhancing Safety in LLM-Based Agent Tool Invocations](https://aclanthology.org/2025.emnlp-main.714/)
- (2025) [The Alignment Waltz: Jointly Training Agents to Collaborate for Safety](https://arxiv.org/abs/2510.08240)
- (2026) [On-Policy Self-Evolution via Failure Trajectories for Agentic Safety Alignment (FATE)](https://arxiv.org/abs/2605.11882)

<a id="runtime-monitoring-and-enforcement"></a>

## 3.3 Runtime Monitoring and Enforcement（运行时监控与执行约束）

### Planning-Stage Auditing（规划阶段审计）

在任何外部动作执行前检查完整计划，识别危险目标、权限违规和高风险动作组合。

- (2025) [Building a Foundational Guardrail for General Agentic Systems via Synthetic Data (Safiron)](https://arxiv.org/abs/2510.09781)

### Step-Level Monitoring（步骤级监控）

在每次工具调用或环境动作提交前审查推理状态、动作语义和参数，并进行阻止、修正、确认或形式化验证。

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

### Trajectory-Level Review（轨迹级复核）

分析部分或完整执行历史，以发现跨步骤权限升级、跨工具信息泄露和累积性策略违规，并支持根因诊断与持续改进。

- (2025) [AgentAuditor](https://arxiv.org/abs/2506.00641)
- (2026) [AgentDoG 1.5: A Lightweight and Scalable Alignment Framework for AI Agent Safety and Security](https://arxiv.org/abs/2605.29801)
- (2026) [BraveGuard: From Open-World Threats to Safer Computer-Use Agents](https://arxiv.org/abs/2606.01166)

---

<a id="research-outlook"></a>

# 4. Research Outlook

综述将未来方向概括为一个“风险生成—风险诊断—安全演化”的闭环：

1. **Automatic Generation of Adversarial Environments and Safety Data**：自动构造可执行、可验证且持续演化的对抗环境与安全数据；
2. **Fine-Grained Safety Attribution over Agent Trajectories**：沿长程交互轨迹定位风险来源、关键步骤与因果链；
3. **Adversarial-Feedback-Driven Continual Safety Evolution**：把新攻击与失败轨迹转化为训练反馈，使安全策略持续更新。

## Citation

如本列表对你的研究有帮助，请优先引用原综述及对应论文。原综述的正式 BibTeX 信息发布后，可在此处补充。

## Contributing

欢迎通过 Issue 或 Pull Request 补充新论文、代码仓库、数据集与勘误。建议沿用现有分类，并使用以下格式：

```markdown
- (Year) [Paper Title](Paper URL)
```
