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
| Agent Security Bench (ASB): Formalizing and Benchmarking Attacks and Defenses in LLM-based Agents | [ICLR 2025](https://arxiv.org/pdf/2410.02644) |该工作提出 ASB 基准框架，系统评估LLM智能体在多种攻击下的安全性，发现其存在高达84.3%的严重漏洞且现有防御效果有限。四类攻击方式：直接提示注入（DPI），间接提示注入（IPI），记忆污染（Memory Poisoning），规划链后门攻击（POT Backdoor Attack） | Attack |
| AgentDojo: A Dynamic Environment to Evaluate Prompt Injection Attacks and Defenses for LLM Agents | [NeurIPS 2024 D&B](https://arxiv.org/abs/2406.13352) | 该工作提出 AgentDojo 这一可扩展评测框架，用于评估工具调用智能体在间接提示注入攻击下的鲁棒性，提供了四种环境 | Attack |
---

## BibTex
