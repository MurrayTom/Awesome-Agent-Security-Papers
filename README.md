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
---

## BibTex
