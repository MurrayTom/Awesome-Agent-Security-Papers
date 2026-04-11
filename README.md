# Awesome-Agent-Security-Papers
Beyond Environment and User Inputs: A Comprehensive Survey of Skill-Oriented Security in Agentic AI


Awesome Skill Security in Agentic AI [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)


## Contents
- [Provenance](#Provenance)
  - [来源可信度](#来源可信度)
  - [作者认证](#作者认证)
  - [篡改防护](#篡改防护)
  - [依赖安全](#依赖安全)
  - [版本可信](#版本可信)
- [Declaration](#Declaration)
  - [内容合规](#内容合规)
  - [虚假信息](#虚假信息)
  - [敏感信息与隐私泄露](#敏感信息与隐私泄露)
  - [高风险/越权操作](#高风险越权操作)
  - [恶意代码注入](#恶意代码注入)
  - [代码漏洞](#代码漏洞)
  - [提示注入](#提示注入)
- [Orchestration](#Orchestration)
  - [系统提示词污染（后门攻击）](#系统提示词污染后门攻击)
  - [恶意用户引导](#恶意用户引导)
  - [记忆污染](#记忆污染)
- [Execution](#Execution)
  - [知识库 RAG 投毒](#知识库-rag-投毒)
  - [Web 网页投毒](#web-网页投毒)
  - [操作系统恶意注入](#操作系统恶意注入)
  - [第三方 MCP 工具恶意提示注入](#第三方-mcp-工具恶意提示注入)

---

## Provenance

### 来源可信度
描述 Skill 来源是否可靠，是否来自可信渠道，可追踪来源链。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
|  | [Link]() |-------|------|
|  | [Link]() |-------|------|

### 作者认证
Skill 作者是否经过认证或可信验证，防止恶意作者注入风险。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
|  | [Link]() |-------|------|
|  | [Link]() |-------|------|

### 篡改防护
Skill 是否可能被篡改，包括传输过程、存储过程的完整性校验等。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
|  | [Link]() |-------|------|
|  | [Link]() |-------|------|

### 依赖安全
Skill 的依赖库、工具或子 Skill 是否安全，是否存在安全漏洞或后门。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
|  | [Link]() |-------|------|
|  | [Link]() |-------|------|

### 版本可信
Skill 版本是否可信，是否存在非官方或未经审查的版本风险。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
|  | [Link]() |-------|------|
|  | [Link]() |-------|------|

---

## Declaration

### 内容合规
Skill 内容是否符合政策法规或平台要求，防止非法或违规操作。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
|  | [Link]() |-------|------|
|  | [Link]() |-------|------|

### 虚假信息
Skill 声称的功能或指令是否真实，防止误导模型或用户。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
|  | [Link]() |-------|------|
|  | [Link]() |-------|------|

### 敏感信息与隐私泄露
Skill 是否处理或泄露敏感信息，如用户数据、机密信息。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
|  | [Link]() |-------|------|
|  | [Link]() |-------|------|

### 高风险/越权操作
Skill 是否尝试执行超出权限范围的操作，如系统级文件操作或管理操作。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
|  | [Link]() |-------|------|
|  | [Link]() |-------|------|

### 恶意代码注入
Skill 内是否包含恶意代码，如 Shell 注入、远程代码执行等。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
|  | [Link]() |-------|------|
|  | [Link]() |-------|------|

### 代码漏洞
Skill 脚本或指令是否存在安全漏洞，如缓冲区溢出、异常执行等。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
|  | [Link]() |-------|------|
|  | [Link]() |-------|------|

### 提示注入
Skill 是否包含恶意 Prompt 注入，篡改或误导模型行为。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
|  | [Link]() |-------|------|
|  | [Link]() |-------|------|

---

## Orchestration

### 系统提示词污染（后门攻击）
模型加载 Skill 时，系统提示词是否可能被污染或嵌入后门指令。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
|  | [Link]() |-------|------|
|  | [Link]() |-------|------|

### 恶意用户引导
用户输入是否可能恶意引导模型加载或执行特定 Skill，从而触发风险。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
|  | [Link]() |-------|------|
|  | [Link]() |-------|------|

### 记忆污染
Memory 模块中历史记录是否可能被污染，影响 Skill 加载决策或模型行为。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
|  | [Link]() |-------|------|
|  | [Link]() |-------|------|

---

## Execution

### 知识库 RAG 投毒
Skill 调用知识库检索时，是否可能检索到恶意或被污染的数据。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
|  | [Link]() |-------|------|
|  | [Link]() |-------|------|

### Web 网页投毒
Skill 调用 Web 页面或网络信息时，是否可能接收到恶意内容或钓鱼信息。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
|  | [Link]() |-------|------|
|  | [Link]() |-------|------|

### 操作系统恶意注入
Skill 执行系统操作时，是否可能被注入恶意命令或操作系统攻击。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
|  | [Link]() |-------|------|
|  | [Link]() |-------|------|

### 第三方 MCP 工具恶意提示注入
Skill 调用第三方 MCP 工具时，工具返回是否可能包含恶意指令，影响模型行为。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
| InjecAgent: Benchmarking Indirect Prompt Injections in Tool-Integrated Large Language Model Agents | [ACL 2024 Findings](https://aclanthology.org/2024.findings-acl.624/) |提出 InjecAgent 基准，系统评估了工具型LLM智能体在间接提示注入攻击下的脆弱性，发现其存在显著安全风险。| Attack |
| Agent Security Bench (ASB): Formalizing and Benchmarking Attacks and Defenses in LLM-based Agents | [ICLR 2025](https://arxiv.org/pdf/2410.02644) |该工作提出 ASB 基准框架，系统评估LLM智能体在多种攻击下的安全性，发现其存在高达84.3%的严重漏洞且现有防御效果有限。四类攻击方式：直接提示注入（DPI），间接提示注入（IPI），记忆污染（Memory Poisoning），规划链后门攻击（POT Backdoor Attack） | Attack/Benchmark |
| AgentDojo: A Dynamic Environment to Evaluate Prompt Injection Attacks and Defenses for LLM Agents | [NeurIPS 2024 D&B](https://arxiv.org/abs/2406.13352) | 该工作提出 AgentDojo 这一可扩展评测框架，用于评估工具调用智能体在间接提示注入攻击下的鲁棒性，提供了四种环境 | Attack/Benchmark |
| ToolSword: Unveiling Safety Issues of Large Language Models in Tool Learning Across Three Stages | [ACL 2024](https://arxiv.org/abs/2402.10753) | 系统评估了现有针对IPI攻击的多种防御方法，并通过设计自适应攻击成功绕过所有防御。 | Attack/Benchmark |
| Adaptive Attacks Break Defenses Against Indirect Prompt Injection Attacks on LLM Agents | [NAACL 2025 Findings](https://arxiv.org/abs/2506.00641) | 提出 AgentAuditor，一种无需训练的记忆增强评估框架，通过模拟人类专家推理显著提升LLM对智能体安全与风险的评估能力，并在新基准 ASSEBench 上达到接近人类水平的性能。 | Attack/Defense |
| AGENTVIGIL: Automatic Black-Box Red-teaming for Indirect Prompt Injection against LLM Agents | [EMNLP 2025 Findings](https://arxiv.org/abs/2506.00641) | 提出一个自动化生成和优化间接提示注入攻击的方法（AGENTVIGIL），通过语料库初始化 + 变异 + MCTS选择 + 评分优化，持续迭代生成更有效的对抗提示，从而系统性提升对智能体系统的提示注入攻击能力与覆盖范围。 | Attack |
| Prompt Injection Attack to Tool Selection in LLM Agents | [NDSS 2026](https://www.ndss-symposium.org/wp-content/uploads/2026-s675-paper.pdf) | 提出 ToolHijacker 攻击，通过注入恶意工具文档操纵智能体的工具选择过程。 | Attack |
| ChatInject: Abusing Chat Templates for Prompt Injection in LLM Agents | [ICLR 2026](https://arxiv.org/abs/2509.22830) | 提出 ToolHijacker 攻击，通过注入恶意工具文档操纵智能体的工具选择过程利用聊天模板漏洞进行注入，在 AgentDojo 上 ASR 从 5.18% 跃升至 32.05%，在 InjecAgent 上达到 45.90%。 | Attack |
| TROJANTOOLS: ADAPTIVE INDIRECT PROMPT INJECTION ON LLM AGENTS VIA MALICIOUS TOOL-CALLING | [ICLR 2026](https://openreview.net/pdf?id=PFbt5pWWh7) | 通过恶意工具输出进行自适应间接提示注入，攻击成功率提升 2.13 倍，且能绕过最新防御。 | Attack |
| Locks Tested Without Burglars: Using Coding Assistants to Break Prompt Injection Defenses | [ICLR 2026](https://openreview.net/pdf?id=ER5Qmhfd5i) | 证明 AI 编码助手可以自动解析防御代码并生成自适应攻击，使现有防御的 ASR 提升 50-60%。 | Attack |
| LlamaFirewall: An open source guardrail system for building secure AI agents | [Arxiv](https://arxiv.org/abs/2505.03574) | 该工作提出 LlamaFirewall 作为AI智能体的最后一道安全防线，通过越狱检测、推理过程审计和代码安全分析三种机制，有效缓解提示注入、目标偏移及不安全代码等风险。 | Defense |
| AgentAuditor: Human-Level Safety and Security Evaluation for LLM Agents | [NeurIPS 2025](https://arxiv.org/abs/2506.00641) | 提出 AgentAuditor，一种无需训练的记忆增强评估框架，通过模拟人类专家推理显著提升LLM对智能体安全与风险的评估能力，并在新基准 ASSEBench 上达到接近人类水平的性能。 | Defense/Evaluation |
| Think Twice Before You Act: Enhancing Agent Behavioral Safety with Thought Correction | [Arxiv](https://arxiv.org/abs/2505.11063) | 提出 Thought-Aligner，一种动态思维纠正模块，通过在每次行动前修正高风险推理过程，将智能体安全性从约50%提升至90%，且无需修改原有框架、具备高效易部署的特点。 | Defense |
| VeriGuard: Enhancing LLM Agent Safety via Verified Code Generation | [Arxiv](https://arxiv.org/abs/2510.05156) | 提出 VeriGuard 框架，通过“离线形式化验证 + 在线行为监控”的双阶段机制，为LLM智能体提供可验证的安全保证 | Defense |
| IPIGUARD: A Novel Tool Dependency Graph-Based Defense Against Indirect Prompt Injection in LLM Agents | [EMNLP 2025](https://arxiv.org/abs/2508.15310) | 基于工具依赖图的防御方法，通过分析工具调用的合理性来检测异常 | Defense |
| MCIP: Protecting MCP Safety via Model Contextual Integrity Protocol | [EMNLP 2025](https://aclanthology.org/2025.emnlp-main.62/) | 为 MCP 系统设计的安全协议，增加了跟踪日志和安全感知护栏，这个护栏针对的是MCP tool的输出 | Defense |
| Agent Safety Alignment via Reinforcement Learning | [Link]() |-------|Defense (Alignment)|
| AgentAlign: Navigating Safety Alignment in the Shift from Informative to Agentic Large Language Models | [Link]() |-------|Defense (Alignment)|
| Towards Tool Use Alignment of Large Language Models | [EMNLP 2024](https://aclanthology.org/2024.emnlp-main.82/) |-------|Defense (Alignment)|
| ToolSafety: A Comprehensive Dataset for Enhancing Safety in LLM-Based Agent Tool Invocations | [EMNLP 2025](https://aclanthology.org/2025.emnlp-main.714/) |-------|Defense (Alignment)|
---

## BibTex
