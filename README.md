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
| Title | Link | Description | Category |
|-------|------|-------|------|
| LLM Harms: A Taxonomy and Discussion | [**arXiv 2025**](https://arxiv.org/abs/2512.05929) | 提出针对 GPT-4 级别模型的细粒度危害分类法，区分直接输出危害与间接诱导危害，为内容合规风险定义提供系统框架。 | Definition |
| Guardians and Offenders: A Survey on Harmful Content Generation and Safety Mitigation of LLM | [**arXiv 2025**](https://arxiv.org/abs/2508.05775) | 统一 LLM 相关危害分类，系统分析内置安全护栏的演进，梳理有害内容生成与缓解的研究全貌。 | Definition |
| Risk Taxonomy, Mitigation, and Assessment Benchmarks of Large Language Model Systems | [**arXiv 2024**](https://arxiv.org/abs/2401.05778) | 构建 LLM 系统风险分类体系，涵盖内容安全的多个子类别，为合规风险评估提供标准化框架。 | Definition |
| SafetyBench: Evaluating the Safety of Large Language Models | [**ACL 2024**](https://aclanthology.org/2024.acl-long.830/) | 中英双语综合安全评估基准，包含 11185 道多选题，覆盖 7 大安全类别，系统评估 LLM 内容合规能力。 | Benchmark |
| HarmBench: A Standardized Evaluation Framework for Automated Red Teaming and Robust Refusal | [**ICML 2024**](https://arxiv.org/abs/2402.04249) | 标准化有害行为评测框架，覆盖 18 种红队攻击方法与 400+ 有害行为类别，为 Skill 内容合规防御提供统一评测基准。 | Benchmark |
| Universal Adversarial Attacks on Aligned Language Models (GCG) | [**arXiv 2023**](https://arxiv.org/abs/2307.15043) | 基于贪婪坐标梯度搜索的自动化对抗性后缀生成方法，可跨模型迁移，揭示对齐模型的系统性内容合规漏洞。 | Attack |
| AutoDAN: Generating Stealthy Jailbreak Prompts on Aligned Large Language Models | [**arXiv 2023**](https://arxiv.org/abs/2310.04451) | 自动生成隐蔽越狱提示词，模拟人类语言风格规避检测，对主流安全对齐模型均有效。 | Attack |
| Do Anything Now: Characterizing and Evaluating In-The-Wild Jailbreak Prompts on Large Language Models | [**ACM CCS 2024**](https://arxiv.org/abs/2308.03825) | 收集并分析真实世界中 6387 条越狱提示，揭示内容合规防线的实际脆弱性，为合规检测提供真实攻击数据集。 | Attack |
| WildGuard: Open One-Stop Moderation Tools for Safety Risks, Jailbreaks, and Refusals of LLMs | [**NeurIPS 2024**](https://proceedings.neurips.cc/paper_files/paper/2024/hash/0f69b4b96a46f284b726fbd70f74fb3b-Abstract-Datasets_and_Benchmarks_Track.html) | 开源一站式内容审核工具，覆盖有害请求识别、越狱检测与拒绝响应分类三大功能，在多个基准上超越 GPT-4。 | Defense |
| Improving Safety Alignment via Balanced Direct Preference Optimization | [**arXiv 2026**](https://arxiv.org/abs/2603.22829) | 平衡 DPO 方法解决安全对齐中的过拟合问题，在提升内容合规性的同时保持模型实用性。 | Defense |
| Constitutional AI: Harmlessness from AI Feedback | [**arXiv 2022**](https://arxiv.org/abs/2212.08073) | Anthropic 提出宪法 AI 框架，通过 AI 自我批判与修订机制实现内容合规对齐，无需大量人工标注有害样本。 | Defense |

### 虚假信息
Skill 声称的功能、身份或指令是否真实，防止恶意 Skill 通过虚假声明误导智能体执行不安全操作。
| Title | Link | Description | Category |
|-------|------|-------|------|
| Factuality of Large Language Models: A Survey | [**EMNLP 2024**](https://aclanthology.org/2024.emnlp-main.1088/) | 系统综述 LLM 事实性问题的定义与成因，为分析 Skill 虚假声明如何被智能体信任并执行提供理论基础。 | Definition |
| On the Risk of Misinformation Pollution with Large Language Models | [**EMNLP 2023 Findings**](https://aclanthology.org/2023.findings-emnlp.97/) | 揭示 LLM 生成虚假信息的系统性风险，分析攻击者如何通过污染 Skill 关联知识库诱导智能体基于错误信息行动。 | Definition |
| Attractive Metadata Attack: Inducing LLM Agents to Invoke Malicious Tools | [**arXiv 2025**](https://arxiv.org/abs/2508.02110) | 通过构造误导性工具元数据（名称、描述、示例）操纵智能体工具选择，使其误信恶意 Skill 为合法工具并优先调用，直接证明 Skill 虚假声明对智能体行为的劫持效果。 | Attack |
| Supply-Chain Poisoning Attacks Against LLM Coding Agent Skill Ecosystems | [**arXiv 2026**](https://arxiv.org/pdf/2604.03081) | 揭示 Skill 供应链风险：恶意 Skill 伪装成合法编程工具发布，通过 DDIPE 机制在文档示例中嵌入隐式载荷，智能体加载后在误以为执行授权任务的同时实际执行攻击者控制的操作。 | Attack |
| AgentHarm: A Benchmark for Measuring Harmfulness of LLM Agents | [**arXiv 2024**](https://arxiv.org/abs/2410.09024) | 包含 440 个有害 Agent 任务，可用于评估智能体在加载含虚假声明的恶意 Skill 后执行高危操作的风险程度。 | Benchmark |
| MultiRAG: A Knowledge-Guided Framework for Mitigating Hallucination in Multi-Source RAG | [**IEEE 2025**](https://ieeexplore.ieee.org/abstract/document/11113128/) | 多源知识引导框架通过知识一致性校验，防止智能体因 Skill 关联知识库被污染而基于虚假信息做出错误决策。 | Defense |
| UALIGN: Leveraging Uncertainty Estimations for Factuality Alignment on Large Language Models | [**ACL 2025**](https://aclanthology.org/2025.acl-long.299/) | 利用不确定性估计进行事实性对齐，使智能体在 Skill 声明可信度不足时拒绝执行，降低虚假 Skill 的危害。 | Defense |

### 敏感信息与隐私泄露
Skill 是否处理或泄露敏感信息，包括用户个人数据（PII）、系统提示词、Agent 内部状态、工具凭证及系统文件等。
| Title | Link | Description | Category |
|-------|------|-------|------|
| Understanding PII Leakage in Large Language Models: A Systematic Survey | [**arXiv 2025**](https://digitalcommons.odu.edu/computerscience_fac_pubs/421/) | 系统综述 LLM 中 PII 泄露的攻击向量与防御机制，涵盖训练数据提取、成员推断、属性推断等多类隐私风险。 | Definition |
| Security and Privacy Challenges of Large Language Models: A Survey | [**ACM Computing Surveys 2025**](https://dl.acm.org/doi/abs/10.1145/3712001) | 全面综述 LLM 安全与隐私挑战，涵盖数据泄露、模型逆向、推理隐私等多维度风险分析，包括系统提示词与 Agent 内部状态的泄露威胁。 | Definition |
| Prompt Leakage Effect and Defense Strategies for Multi-Turn LLM Interactions | [**arXiv 2024**](https://arxiv.org/abs/2404.16251) | 系统研究多轮对话中系统提示词的渐进式泄露机制，定义提示泄露的攻击面与危害等级，为 Skill 系统提示词保护提供理论框架。 | Definition |
| PII-Scope: A Comprehensive Study on Training Data PII Extraction Attacks in LLMs | [**arXiv 2024**](https://arxiv.org/abs/2410.06704) | 评估 LLM 训练数据中 PII 提取风险的综合基准，系统测量不同类型 PII 在各类模型中的泄露程度。 | Benchmark |
| Can LLMs Keep a Secret? Testing Privacy Implications of Language Model Chatbots | [**ICLR 2024**](https://arxiv.org/abs/2306.07543) | 提出 ConfAIde 基准，测试 LLM 在对话中保守秘密的能力，揭示 Skill 在多轮交互中系统提示词与用户隐私的泄露风险。 | Benchmark |
| Effective PII Extraction from LLMs through Augmented Few-Shot Learning | [**USENIX Security 2025**](https://www.usenix.org/conference/usenixsecurity25/presentation/cheng-shuai) | 利用少样本学习增强技术诱导 LLM 暴露个人身份信息，揭示 Skill 在少样本场景下的隐私泄露风险。 | Attack |
| LLMs Leak Training Data Beyond Verbatim Memorization via Membership Decoding | [**OpenReview 2023**](https://openreview.net/forum?id=ULqzEEkyxk) | 通过成员推断解码揭示 LLM 训练数据泄露超越逐字记忆，证明模型可泄露语义层面的训练数据信息。 | Attack |
| PLeak: Prompt Leaking Attacks against Large Language Model Applications | [**ACM CCS 2024**](https://arxiv.org/abs/2406.09324) | 提出 PLeak 框架，通过构造对抗性查询序列高效提取开发者保密的系统提示词，揭示 Skill 系统提示词面临的主动窃取威胁。 | Attack |
| Simple Prompt Injection Attacks Can Leak Personal Data Observed by LLM Agents During Task Execution | [**arXiv 2025**](https://arxiv.org/abs/2506.01055) | 揭示 Agent 在执行多步任务时，中间处理的文件内容、工具返回值等系统数据可通过简单提示注入被渗透窃取。 | Attack |
| IP Leakage Attacks Targeting LLM-Based Multi-Agent Systems | [**arXiv 2025**](https://arxiv.org/abs/2505.12442) | 针对多智能体系统的知识产权和敏感信息窃取攻击，揭示 Skill 在多 Agent 协作场景下系统配置与内部状态的泄露路径。 | Attack |
| Fine-tuning Large Language Models with User-level Differential Privacy | [**arXiv 2024**](https://arxiv.org/abs/2407.07737) | 用户级差分隐私保护 LLM 微调数据隐私，在保证模型性能的同时提供可量化的隐私保护。 | Defense |
| Split-and-Denoise: Protect Large Language Model Inference with Local Differential Privacy | [**arXiv 2023**](https://arxiv.org/abs/2310.09130) | 局部差分隐私保护 LLM 推理输入隐私，通过分割与去噪机制防止 Skill 推理过程中的用户数据与系统状态泄露。 | Defense |
| A-MemGuard: A Proactive Defense Framework for LLM-Based Agent Memory | [**arXiv 2025**](https://arxiv.org/abs/2510.02373) | 针对 Agent 记忆系统的主动式防御框架，防止攻击者通过记忆模块提取 Skill 处理过的敏感信息与系统状态。 | Defense |

### 高风险/越权操作
Skill 是否尝试执行超出权限范围的操作，如系统级文件操作或管理操作。
| Title | Link | Description | Category |
|-------|------|-------|------|
| Taming Various Privilege Escalation in LLM-Based Agent Systems: A Mandatory Access Control Framework (SEAgent) | [**arXiv 2026**](https://arxiv.org/abs/2601.11893) | 定义 Agent 权限提升攻击分类（水平提升、垂直提升、跨 Agent 提升），为越权操作风险提供系统化分类框架。 | Definition |
| Identifying the Risks of LM Agents with an LM-Emulated Sandbox (ToolEmu) | [**ICLR 2024**](https://arxiv.org/abs/2309.15817) | 提出 ToolEmu 沙箱框架，用 LLM 模拟工具执行环境，系统识别 Agent 在真实工具调用中的越权操作风险，发现 68.4% 的测试案例存在安全失败。 | Benchmark |
| AgentHarm: A Benchmark for Measuring Harmfulness of LLM Agents | [**arXiv 2024**](https://arxiv.org/abs/2410.09024) | 包含 440 个有害 Agent 任务，覆盖网络攻击、欺诈、武器制造等 11 类高风险操作，衡量 Agent 执行显式恶意任务时的合规性与危害程度。 | Benchmark |
| R-Judge: Benchmarking Safety Risk Awareness for LLM Agents | [**EMNLP 2024**](https://arxiv.org/abs/2401.10019) | 包含 569 个安全风险场景，覆盖 27 类高风险操作，系统评估 LLM Agent 对越权操作的风险感知能力。 | Benchmark |
| AdapTools: Adaptive Tool-based Indirect Prompt Injection Attacks on Agentic LLMs | [**arXiv 2026**](https://arxiv.org/abs/2602.20720) | 自适应工具注入攻击，通过选择更隐蔽且任务相关的攻击工具绕过现有 IPI 防御，显著提升越权操作成功率。 | Attack |
| SEAgent: Mandatory Access Control Framework for LLM-Based Agent Systems | [**arXiv 2026**](https://arxiv.org/abs/2601.11893) | 强制访问控制框架限制 Agent 操作边界，通过最小权限原则防止 Skill 执行超出授权范围的高风险操作。 | Defense |
| Progent: Programmable Privilege Control for LLM Agents | [**arXiv 2025**](https://arxiv.org/abs/2504.11703) | 首个为 LLM Agent 设计的细粒度可编程权限控制框架，支持动态权限策略，精确限制 Skill 的操作边界。 | Defense |
| ToolSafe: Enhancing Tool Invocation Safety via Proactive Step-level Guardrail and Feedback | [**arXiv 2026**](https://arxiv.org/abs/2601.10156) | 执行前步骤级安全护栏检查，在 Skill 调用高风险工具前进行实时拦截与反馈，防止越权操作造成不可逆损害。 | Defense |
| Task Shield: Enforcing Task Alignment to Defend Against Indirect Prompt Injection | [**ACL 2025**](https://aclanthology.org/2025.acl-long.1435/) | 通过强制任务对齐防御环境中的恶意指令注入，确保 Skill 执行始终与原始授权任务保持一致。 | Defense |

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
| Ignore Previous Prompt: Attack Techniques For Language Models | [**NeurIPS 2022 ML Safety**](https://arxiv.org/pdf/2211.09527) | 首次系统性提出提示注入概念，定义了目标劫持与提示泄露，发现模型能力越强越易受攻击。 | Attack |
| Prompt Injection Attack Against LLM-integrated Applications | [**arXiv 2023**](https://arxiv.org/pdf/2306.05499) | 提出 HOUYI 三阶段攻击框架，利用上下文分割技术绕过防御，将攻击扩展至集成应用。 | Attack |
| Not What You've Signed Up For: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection | [**ACM AISec 2023**](https://arxiv.org/pdf/2309.01454) | 首次提出间接提示注入（IPI），通过污染第三方网页或文档远程控制 LLM。 | Attack |
| Strengthening LLM Trust Boundaries: A Survey of Prompt Injection Attacks | [**IEEE ICHMS 2024**](https://arxiv.org/pdf/2310.03684) | 提出五层攻击利用框架，从三个维度系统分析提示注入，建立层次化防御架构。 | Attack/Defense |
| Trust No AI: Prompt Injection Along the CIA Security Triad | [**arXiv 2024**](https://arxiv.org/pdf/2412.06090) | 从 CIA 安全三元组视角分析，涵盖提示泄露、沙箱逃逸等七种系统性攻击方法。 | Attack |
| Backdooring Instruction-Tuned Large Language Models with Virtual Prompt Injection | [**NAACL 2024**](https://arxiv.org/pdf/2402.05298) | 提出虚拟提示注入（VPI），通过少量投毒数据在训练中嵌入恶意行为触发后门。 | Attack |
| Simple Prompt Injection Attacks Can Leak Personal Data Observed by LLM Agents During Task Execution | [**arXiv 2025**](https://arxiv.org/pdf/2506.01055) | 揭示 Agent 在执行多步任务时，其处理的数据流可被渗透导致中间敏感信息泄露。 | Attack |
| PLeak: Prompt Leaking Attacks against Large Language Model Applications | [**ACM CCS 2024**](https://arxiv.org/pdf/2406.09324) | 提出 PLeak 框架，利用增量搜索高效提取开发者保密的系统提示。 | Attack |
| Baseline Defenses for Adversarial Attacks against Aligned Language Models | [**arXiv 2023**](https://arxiv.org/pdf/2309.00614) | 系统评估困惑度、过滤等基线防御，发现单一机制难以平衡安全性和实用性。 | Defense |
| SmoothLLM: Defending Large Language Models Against Jailbreaking Attacks | [**arXiv 2023**](https://arxiv.org/pdf/2310.03684) | 基于随机扰动和预测聚合的防御框架，通过字符级扰动破坏对抗后缀。 | Defense |
| Certifying LLM Safety against Adversarial Prompting | [**arXiv 2023/2024**](https://arxiv.org/pdf/2309.02705) | 提出 Erase-and-Check，首个提供形式化可证明安全保证（安全证书）的防御框架。 | Defense |
| Defending Large Language Models against Jailbreak Attacks via Semantic Smoothing | [**arXiv 2024**](https://arxiv.org/pdf/2402.16192) | 采用语义保持变换（释义、风格转换）和预测聚合，提供比 token 级更鲁棒的防御。 | Defense |
| Self-Guard: Empower the LLM to Safeguard Itself | [**NAACL 2024**](https://arxiv.org/pdf/2310.15851) | 两阶段训练法使 LLM 具备自我审查能力，在输出端附加安全标签进行实时管控。 | Defense |
| Defending Large Language Models against Jailbreaking Attacks through Goal Prioritization | [**ACL 2024**](https://arxiv.org/pdf/2311.09096) | 通过特殊指令在推理和训练阶段强化原始任务优先级，防止系统目标被覆盖。 | Defense |
| MRJ-Agent: An Effective Jailbreak Agent for Multi-Round Dialogue | [**arXiv 2024**](https://arxiv.org/pdf/2411.03814) | 针对多轮对话场景设计的攻击 Agent，自动分析上下文并生成隐蔽越狱提示。 | Attack |
| PrivAgent: Agentic-based Red-teaming for LLM Privacy Leakage | [**arXiv 2024**](https://arxiv.org/pdf/2412.05734) | 利用强化学习训练攻击 Agent，诱导目标模型泄露系统提示或训练数据。 | Attack |
| Evil Geniuses: Delving into the Safety of LLM-based Agents | [**arXiv 2023**](https://arxiv.org/pdf/2311.11855) | 构建多智能体协作（MAS）攻击系统，通过红蓝对抗演练协同实施越狱攻击。 | Attack |
| PANDORA: Detailed LLM Jailbreaking via Collaborated Phishing Agents with Decomposed Reasoning | [**ICLR 2024 Workshop**](https://openreview.net/forum?id=8Wb3aCRe5B) | 提出协同钓鱼 Agent 框架，通过分解推理实现精细化的社会工程学攻击。 | Attack |
| Agent Smith: A Single Image Can Jailbreak One Million Multimodal LLM Agents Exponentially Fast | [**arXiv 2024**](https://arxiv.org/pdf/2402.08567) | 发现可指数级传播的自复制对抗图像，在多模态 Agent 系统中实现病毒式扩散。 | Attack |

---

## Orchestration

### 系统提示词污染（后门攻击）
模型加载 Skill 时，系统提示词是否可能被污染或嵌入后门指令。
| Title | Link | Description | Category |
|-------|------|-------|------|
| Backdoor Attacks on Language Models | [**arXiv 2021**](https://arxiv.org/abs/2110.07849) | 首次系统定义 NLP 后门攻击的威胁模型，区分数据投毒型与模型权重型后门，为系统提示词后门攻击提供基础分类框架。 | Definition |
| A Survey of Backdoor Attacks and Defenses on Large Language Models | [**IEEE TNNLS 2025**](https://arxiv.org/abs/2406.06852) | 全面综述 LLM 后门攻击与防御，涵盖指令微调、RLHF、RAG 等多个攻击面，系统梳理系统提示词污染的威胁模型与防御技术路线。 | Definition |
| Instructions as Backdoors: Backdoor Vulnerabilities of Instruction Tuning for Large Language Models | [**NAACL 2024**](https://arxiv.org/abs/2305.14710) | 首次揭示指令微调数据集中的后门漏洞，证明攻击者可通过污染少量指令数据在 LLM 中植入持久化后门，直接威胁 Skill 系统提示词安全。 | Definition |
| BackdoorBench: A Comprehensive Benchmark of Backdoor Learning | [**NeurIPS 2022**](https://arxiv.org/abs/2206.12654) | 首个系统化后门学习综合基准，统一评估框架覆盖 16 种攻击与 9 种防御方法，为系统提示词后门攻击的评测提供标准化平台。 | Benchmark |
| TrojLLM: A Black-box Trojan Prompt Attack on Large Language Models | [**NeurIPS 2023**](https://arxiv.org/abs/2306.06815) | 提出黑盒木马提示攻击框架，无需访问模型权重即可在提示词中植入触发器，直接针对系统提示词的后门注入场景，并提供评测基准。 | Benchmark |
| Backdooring Instruction-Tuned Large Language Models with Virtual Prompt Injection | [**NAACL 2024**](https://arxiv.org/abs/2307.16888) | 提出虚拟提示注入（VPI），通过少量投毒数据在指令微调阶段嵌入后门，触发后可将任意系统提示词替换为攻击者控制的恶意指令。 | Attack |
| BadAgent: Inserting and Activating Backdoor Attacks in LLM Agents | [**ACL 2024**](https://arxiv.org/abs/2406.03007) | 首个针对 LLM Agent 的后门攻击框架，通过污染 Agent 训练数据在系统提示词层面植入后门，触发后可劫持 Agent 执行任意高危操作。 | Attack |
| Watch Out for Your Agents! Investigating Backdoor Threats to LLM-based Agents | [**arXiv 2024**](https://arxiv.org/abs/2402.11208) | 系统研究 LLM Agent 的后门威胁，涵盖系统提示词污染、工具调用劫持等多种攻击路径，揭示 Agent 场景下后门攻击的独特危险性。 | Attack |
| Sleeper Agents: Training Deceptive LLMs that Persist Through Safety Training | [**arXiv 2024**](https://arxiv.org/abs/2401.05566) | Anthropic 研究揭示可在安全训练后持续存在的"睡眠代理"后门，证明即使经过 RLHF 对齐，系统提示词中的后门行为仍可被激活。 | Attack |
| PoisonedAlign: Poisoning Safety Alignment of Large Language Models via Harmful Demonstrations | [**EMNLP 2024**](https://arxiv.org/abs/2406.09038) | 通过在 RLHF/SFT 对齐阶段注入有害示例污染安全对齐，使模型在特定触发词下绕过安全护栏，直接威胁系统提示词的安全约束。 | Attack |
| Shadow Alignment: The Ease of Subverting Safely-Aligned Language Models | [**arXiv 2023**](https://arxiv.org/abs/2310.02949) | 仅需 100 条有害数据即可颠覆安全对齐，揭示系统提示词安全约束的脆弱性，攻击者可低成本植入后门覆盖原有安全指令。 | Attack |
| ONION: A Simple and Effective Defense Against Textual Backdoor Attacks | [**EMNLP 2021**](https://arxiv.org/abs/2011.10369) | 基于异常词检测的文本后门防御方法，通过识别触发词的语言学异常性过滤后门输入，可用于系统提示词的后门触发器检测。 | Defense |
| Mitigating Backdoor Attacks in LLMs through Activation Patching | [**arXiv 2024**](https://arxiv.org/abs/2408.10178) | 针对 LLM 的激活修补方法，通过定位并修复后门相关的激活模式，在推理阶段实时消除系统提示词污染的影响。 | Defense |
| Fine-Pruning: Defending Against Backdooring Attacks on Deep Neural Networks | [**RAID 2018**](https://arxiv.org/abs/1805.12185) | 提出剪枝+微调的后门消除方法，通过移除对正常输入不活跃的神经元来净化被污染的模型，可用于清除系统提示词后门。 | Defense |

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
| Watch Out for Your Agents! Investigating Backdoor Threats to LLM-based Agents | [**arXiv 2024**](https://arxiv.org/pdf/2402.11208) | 提出 AgentPoison 攻击，通过优化后门触发器并植入向量数据库，实现针对 Agent 记忆模块的持久化后门攻击。 | Attack |

---

## Execution

### 知识库 RAG 投毒
Skill 调用知识库检索时，是否可能检索到恶意或被污染的数据。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
| Prompt-in-Content Attacks: Exploiting Uploaded Inputs to Hijack LLM Behavior | [arXiv:2508.19287](https://arxiv.org/pdf/2508.19287) | 揭示文件上传工作流中的新攻击向量，利用文档内嵌对抗指令实现输出操纵和敏感信息窃取。 | Attack |
| PoisonedRAG: Knowledge Corruption Attacks to Retrieval-Augmented Generation | [arXiv:2409.02354](https://arxiv.org/pdf/2409.02354) | 提出 PoisonedRAG，通过优化恶意文本使其更容易被检索算法选中，从而实现针对 RAG 的知识污染。 | Attack |
| Typos that Broke the RAG's Back: Genetic Attack on RAG Pipeline | [arXiv:2404.13948](https://arxiv.org/pdf/2404.13948) | 提出 GARAG，利用遗传算法和低级字符扰动模拟真实场景文档，自动发现并优化针对 RAG 的攻击模式。 | Attack |
| Certifiably Robust RAG against Retrieval Corruption | [arXiv:2405.15556](https://arxiv.org/pdf/2405.15556) | 分析 RAG 对检索腐败的敏感性，并提出 Isolate-then-Aggregate 防御策略，通过独立生成与聚合来提升鲁棒性。 | Attack/Defense |
| RAG-Thief: Scalable Extraction of Private Data from RAG Applications | [arXiv:2411.14110](https://arxiv.org/pdf/2411.14110) | 提出 RAG-Thief，通过 Agent 自动化优化锚查询和越狱提示，实现对 RAG 知识库中私有数据的规模化窃取。 | Attack |

### Web 网页投毒
Skill 调用 Web 页面或网络信息时，是否可能接收到恶意内容或钓鱼信息。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
| WebInject: Prompt Injection Attack to Web Agents | [**EMNLP 2025**](https://arxiv.org/pdf/2502.00954) | 提出 EnvInjection 攻击，通过神经网络逼近 ICC 配置文件的映射，在网页像素中植入人眼不可见的指令操纵 Web Agent。 | Attack |
| WASP: Benchmarking Web Agent Security Against Prompt Injection Attacks | [**arXiv 2025**](https://arxiv.org/pdf/2504.18575) | 首个 Web Agent 安全基准框架，模拟真实威胁场景并评估多步执行下的中间步骤与端到端攻击成功率。 | Attack/Benchmark |
| Manipulating Multimodal Agents via Cross-Modal Prompt Injection | [**ACM MM 2025**](https://arxiv.org/pdf/2408.09730) | 提出 CrossInject 框架，通过视觉与文本模态间的恶意关联劫持多模态 Agent，利用模态对齐机制绕过单一防御。 | Attack |
| Prompt Injection Attacks on Vision Language Models in Oncology | [**Nature Comm. 2025**](https://www.nature.com/articles/s41467-024-55631-x) | 首次在肿瘤学医学影像领域验证视觉注入攻击，证明通过在 X 光或 CT 中嵌入指令可直接操纵 AI 诊断结果。 | Attack |
| Text-Based Prompt Injection Attack Using Mathematical Functions in Modern Large Language Models | [**Electronics 2024**](https://www.mdpi.com/2079-9292/13/24/5008) | 利用数学函数绘制字形来替换敏感词汇，通过多模态模型的视觉表示特性绕过关键词安全过滤。 | Attack |

### 操作系统恶意注入
Skill 执行系统操作时，是否可能被注入恶意命令或操作系统攻击。
| Title | Link | Description | Category(Attack or Defense) |
|-------|------|-------|------|
| StruQ: Defending Against Prompt Injection with Structured Queries | [**USENIX Security 2025**](https://arxiv.org/pdf/2402.06363) | 借鉴 SQL 注入防御思路，提出控制与数据分离原则，通过 API 层面的结构化查询接口实现系统级注入防御。 | Defense |
| Supply-Chain Poisoning Attacks Against LLM Coding Agent Skill Ecosystems | [**arXiv 2026**](https://arxiv.org/pdf/2604.03081) | 揭示 Agent Skill 供应链风险，提出 DDIPE 机制通过文档示例隐式执行载荷，绕过模型对齐实现系统级劫持。 | Attack |

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
| PIArena: A Platform for Prompt Injection Evaluation | [ACL 2026 Main](https://arxiv.org/abs/2604.08499) | 提出 PIArena 这一统一且可扩展的提示注入评测平台，支持对多种攻击、 防御与基准进行即插即用式系统评估 | Attack/Defense/Benchmark |
| AgentDyn: A Dynamic Open-Ended Benchmark for Evaluating Prompt Injection Attacks of Real-World Agent Security System | [ArXiv 2026](https://arxiv.org/abs/2602.03117) | 提出 AgentDyn，一个面向真实世界智能体安全系统的动态开放式提示注入评测基准 | Attack/Benchmark |
| Benchmarking and Defending against Indirect Prompt Injection Attacks on Large Language Models | [KDD 2025](https://arxiv.org/abs/2312.14197) | 提出针对间接提示注入攻击的系统化评测基准 BIPIA，系统评估了多种 LLM 在外部内容注入场景下的脆弱性，发现模型普遍容易混淆“信息内容”和“可执行指令” | Defense/Benchmark |
| AUTOHIJACKER: AUTOMATIC INDIRECT PROMPT INJECTION AGAINST BLACK-BOX LLM AGENTS | [ArXiv 2025](https://openreview.net/forum?id=2VmB01D9Ef) | 提出 AutoHijacker，一种面向黑盒 LLM 智能体的自动化间接提示注入攻击方法。该方法基于 LLM-as-optimizer，设计了批量优化框架以应对稀疏反馈，并结合可训练记忆机制减少持续查询开销 | Attack |
| MUZZLE: Adaptive Agentic Red-Teaming of Web Agents Against Indirect Prompt Injection Attacks | [ArXiv 2026](https://arxiv.org/abs/2602.09222) | 提出 MUZZLE，一个面向 Web Agent 的自动化、自适应红队攻击框架。该方法利用智能体执行轨迹自动识别高价值注入位置，并结合上下文感知的恶意指令生成与失败反馈迭代优化 | Attack |
| Prompt Injection attack against LLM-integrated Applications | [ArXiv 2023](https://arxiv.org/abs/2306.05499) | 系统研究了真实世界 LLM 集成应用中的提示注入风险，并提出黑盒自动化攻击框架 HouYi。该方法借鉴传统 Web 注入攻击思想，通过预构造提示、上下文分隔注入和恶意载荷三部分实现对应用的攻击 | Attack |
| TopicAttack: An Indirect Prompt Injection Attack via Topic Transition | [EMNLP 2025 main](https://aclanthology.org/2025.emnlp-main.372/) | 提出 TopicAttack，一种通过“话题过渡”实现的间接提示注入攻击方法。该方法先伪造一段自然的用户-助手对话式过渡提示，将模型注意力从原始任务平滑转移到恶意指令上，从而提升注入的隐蔽性与成功率 | Attack |
| Formalizing and Benchmarking Prompt Injection Attacks and Defenses | [USENIX Security 2024](https://arxiv.org/abs/2310.12815) | 提出首个用于形式化描述提示注入攻击的统一框架，并在此基础上系统评测了 5 类攻击、10 种防御、10 个 LLM 与 7 类任务；结果表明现有防御整体效果有限，同时论文还基于该框架构造了组合型新攻击，并开源 Open-Prompt-Injection 平台以支持后续研究。 | Attack/Defense |
| AgentLAB: Benchmarking LLM Agents against Long-Horizon Attacks | [ArXiv 2026](https://arxiv.org/abs/2602.16901) | 提出 AgentLAB，这是首个专门评测 LLM 智能体在长时程攻击下脆弱性的基准，覆盖 28 个真实环境、644 个安全测试样例，并包含意图劫持、工具链攻击、任务注入、目标漂移和记忆污染 5 类新型长程攻击 | Attack/Benchmark |
| Unsafer in Many Turns: Benchmarking and Defending Multi-Turn Safety Risks in Tool-Using Agents | [ArXiv 2026](https://arxiv.org/abs/2602.13379) | 提出首个面向多轮工具型智能体安全的基准 MT-AgentRisk，通过一套原则化分类体系将单轮有害任务系统转化为多轮攻击序列，系统评估了多轮交互下的安全退化现象;同时提出无需训练、与工具无关的防御方法 ToolShield，通过对新工具进行自探索式安全测试与经验蒸馏，将多轮交互中的攻击成功率平均降低约 30%。 | Defense/Benchmark |
| AdapTools: Adaptive Tool-based Indirect Prompt Injection Attacks on Agentic LLMs | [ArXiv 2026](https://arxiv.org/abs/2602.20720) | 提出 AdapTools，一种面向 Agentic LLM 的自适应工具型间接提示注入攻击框架。该方法一方面自动构造可迁移的攻击策略以优化恶意提示，另一方面通过选择更隐蔽且任务相关的攻击工具来绕过相关性防御，从而显著增强攻击效果 | Attack |
| The Ranking Blind Spot: Decision Hijacking in LLM-based Text Ranking | [EMNLP 2025 main](https://aclanthology.org/2025.emnlp-main.1116/) | 不是典型agent IPI的论文，关注的是rank任务里如果被排序内容注入了攻击内容来影响排序结果，提出“Ranking Blind Spot”现象，系统揭示了 LLM 文本排序器在比较式评估中会受到指令跟随能力干扰，并进一步设计了两类决策劫持攻击：Decision Objective Hijacking 与 Decision Criteria Hijacking，使恶意内容提供方能够操纵排序目标或相关性标准，从而影响文档排序结果 | Attack |
| Reasoning Hijacking: Subverting LLM Classification via Decision-Criteria Injection | [ACL 2026](https://arxiv.org/abs/2601.10294) | 提出 Reasoning Hijacking，新型攻击范式不直接改变模型的高层任务目标，而是通过注入伪造的决策标准来操纵模型内部判断逻辑；作者进一步实例化出 Criteria Attack，并在垃圾邮件检测、毒性评论识别和差评识别等分类任务上验证其有效性 | Attack |
| VIGIL: Defending LLM Agents Against Tool-Stream Injection via Verify-Before-Commit | ACL2026 | 提出 VIGIL，一种面向 tool-stream injection 的防御框架，通过“verify-before-commit”机制在执行前对智能体的候选推理与动作进行基于用户意图的验证，从而在保留推理灵活性的同时抑制恶意工具流注入 | Defense |
| PISmith: Reinforcement Learning-based Red Teaming for Prompt Injection Defenses | ArXiv2026 | 提出 PISmith，一种基于强化学习的提示注入防御红队评测框架，在黑盒设定下训练攻击 LLM 自适应优化注入提示，针对IPI奖励极度稀疏的问题，进一步设计了自适应熵正则与动态优势加权机制以维持探索并强化少量成功样本学习 | Attack |
| AgentSentry: Mitigating Indirect Prompt Injection in LLM Agents via Temporal Causal Diagnostics and Context Purification | ArXiv2026 | 提出 AgentSentry，一种面向agent的推理时防御框架，将多轮 IPI 建模为“时间因果接管”过程；该方法通过在工具返回边界执行受控反事实重放来定位接管点，并进一步进行因果引导的上下文净化，在保留任务相关证据的同时移除攻击诱导的偏差信号 | Defense |
| AttriGuard: Defeating Indirect Prompt Injection in LLM Agents via Causal Attribution of Tool Invocations | ArXiv2026 | 提出 AttriGuard，一种基于“工具调用因果归因”的运行时防御框架，不再仅从输入语义层面判断是否存在注入，而是追问某个候选工具调用究竟是由用户意图驱动，还是由不可信工具输出因果诱导产生 | Defense |

---

## BibTex
