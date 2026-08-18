<h1 align="center">Pandora's Toolbox: Generalist Agent Security Paper List</h1>

<div align="center">

**A Literature Index of Attack Surfaces, Evaluation Benchmarks, and Defenses for Generalist Agents**

[中文](./README.md) | [English](./README_EN.md)

[Survey PDF](./Pandora-agent-survey.pdf) · [Reference README](./README_reference.md)

</div>

## 🌟 Overview

This repository organizes the taxonomy and representative studies from *Pandora's Toolbox: A Survey of Security Risks, Attacks, Evaluation, and Defenses for Generalist Agents*. It is intended as a literature-research resource for the security of generalist agents.

The survey takes a runtime-lifecycle perspective and divides the lifecycle into three stages: **provenance, orchestration, and execution**. It organizes the literature along three dimensions:

1. **Security risks and attacks**: four attack surfaces covering skill supply chains, user inputs, long-term memory, and external environments;
2. **Security evaluation**: three lines of work covering domain-specific agents, generalist agents, and offline trajectory auditing;
3. **Security defenses**: three layers covering input and context filtering, decision and control integrity, and runtime monitoring and enforcement.

> This list is based on Figure 2 and Tables 2–9 of the survey. A paper may propose an attack, a benchmark, and a defense, so it may appear in multiple categories. Years refer to the first public release. Links prioritize arXiv, OpenReview, ACL Anthology, and official project pages.

## 🧭 Taxonomy at a Glance

| Dimension | Primary category | Subcategories |
|---|---|---|
| Risks and attacks | Skill supply-chain attacks | Declarative skill file poisoning; multi-component skill ecosystem poisoning; benign skill misuse and compositional risks; cross-session skill rewriting and backdoor triggering |
| Risks and attacks | User-side attacks | Manual jailbreak attacks; heuristic optimization-based jailbreak attacks; agentic red-teaming for jailbreak |
| Risks and attacks | Long-term memory risks | Direct long-term memory poisoning; indirect interaction-based memory injection; backdoor attacks |
| Risks and attacks | Environment-side attacks | Web injection attacks; malicious injection in computer-use environments; tool-output injection |
| Evaluation | Domain-specific agent safety benchmarks | Tool use; web browsing; computer and mobile operation |
| Evaluation | Generalist agent safety benchmarks | Skill-based behavioral safety; malicious skill detection |
| Evaluation | Offline trajectory auditing | Trajectory-level safety detection; step-level safety detection |
| Defenses | Input and context filtering | Skill risk scanning; prompt injection and jailbreak guardrails; memory guardrails |
| Defenses | Decision and control integrity | Harness-externalized defenses; alignment-internalized defenses |
| Defenses | Runtime monitoring and enforcement | Planning-stage auditing; step-level monitoring; trajectory-level review |

<details open>
  <summary><b>📂 Table of Contents</b> (click to expand/collapse)</summary>
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

## 1.1 Skill Supply-Chain Attacks

Skills can be developed by third parties and autonomously selected and loaded by agents. Risks may reside in metadata, `SKILL.md`, scripts, dependencies, configuration, retrieval resources, and persistent cross-session state.

### Declarative Skill File Poisoning

Attackers poison skill metadata, instructions, examples, or trigger rules so that malicious natural-language instructions enter the planning context.

- (2026) [Skill-Inject: Measuring Agent Vulnerability to Skill File Attacks](https://arxiv.org/abs/2602.20156)
- (2026) [Supply-Chain Poisoning Attacks Against LLM Coding Agent Skill Ecosystems (PoisonedSkills)](https://arxiv.org/abs/2604.03081)
- (2026) [SkillJect: Effectively Automating Skill-Based Prompt Injection for Skill-Enabled Agents](https://arxiv.org/abs/2602.14211)
- (2026) [Under the Hood of SKILL.md: Semantic Supply-Chain Attacks on AI Agent Skill Registry](https://arxiv.org/abs/2605.11418)

### Multi-Component Skill Ecosystem Poisoning

The attack surface extends beyond the primary skill file to auxiliary scripts, tool interfaces, dependencies, external assets, configuration files, RAG databases, and local caches.

- (2026) [SkillSafetyBench: Evaluating Agent Safety under Skill-Facing Attack Surfaces](https://arxiv.org/abs/2605.12015)
- (2026) [Skill-Inject: Measuring Agent Vulnerability to Skill File Attacks](https://arxiv.org/abs/2602.20156)
- (2026) [Proteus: A Self-Evolving Red Team for Agent Skill Ecosystems](https://arxiv.org/abs/2605.11891)

### Benign Skill Misuse and Compositional Risks

An individual skill may contain no malicious payload yet remain exploitable through adversarial input. Multiple individually benign skills may also produce unauthorized, privacy-leaking, or destructive behavior when composed along a shared execution path.

- (2026) [SkillAttack: Automated Red Teaming of Agent Skills through Attack Path Refinement](https://arxiv.org/abs/2604.04989)
- (2026) [Benign in Isolation, Harmful in Composition: Security Risks in Agent Skill Ecosystems (SCR-Bench)](https://arxiv.org/abs/2606.15242)
- (2026) [OpenSkillRisk: Benchmarking Agent Safety When Using Real-World Risky Third-Party Skills](https://arxiv.org/abs/2607.20121)

### Cross-Session Skill Rewriting and Backdoor Triggering

An attack modifies skill files, caches, project artifacts, or dependencies in the current session, while malicious behavior activates only in a later session or under a specific trigger.

- (2026) [SkillHarm: Lifecycle-Aware Skill-Based Attacks via Automated Construction](https://arxiv.org/abs/2606.02540)
- (2026) [SkillTrojan: Backdoor Attacks on Skill-Based Agent Systems](https://arxiv.org/abs/2604.06811)

<a id="user-side-attacks"></a>

## 1.2 User-Side Attacks

Malicious users submit harmful tasks, jailbreak prompts, obfuscated contexts, or multi-turn inducements through the direct interaction interface to bypass safety policies and trigger high-risk actions.

### Manual Jailbreak Attacks

These attacks rely on human-designed templates that reformulate malicious requests through role-playing, refusal suppression, scenario disguise, encoding transformations, payload splitting, or few-shot examples.

- (2024) [Refusal-Trained LLMs Are Easily Jailbroken as Browser Agents (BrowserART)](https://arxiv.org/abs/2410.13886)
- (2025) [Large Language Models Often Say One Thing and Do Another (WDCT)](https://arxiv.org/abs/2503.07003)
- (2024) [AgentHarm: A Benchmark for Measuring Harmfulness of LLM Agents](https://arxiv.org/abs/2410.09024)
- (2025) [The Dark Side of Function Calling: Pathways to Jailbreaking Large Language Models](https://aclanthology.org/2025.coling-main.39/)
- (2023) [Jailbroken: How Does LLM Safety Training Fail?](https://arxiv.org/abs/2307.02483)
- (2023) [DeepInception: Hypnotize Large Language Model to Be Jailbreaker](https://arxiv.org/abs/2311.03191)
- (2024) [EasyJailbreak: A Unified Framework for Jailbreaking Large Language Models](https://arxiv.org/abs/2403.12171)

### Heuristic Optimization-Based Jailbreak Attacks

Jailbreak construction is formulated as a search or optimization problem, with gradient search, genetic algorithms, black-box iteration, or prompt mutation used to generate attacks automatically.

- (2024) [Imprompter: Tricking LLM Agents into Improper Tool Use](https://arxiv.org/abs/2410.14923)
- (2025) [STAC: When Innocent Tools Form Dangerous Chains to Jailbreak LLM Agents](https://arxiv.org/abs/2509.25624)
- (2023) [Universal and Transferable Adversarial Attacks on Aligned Language Models (GCG)](https://arxiv.org/abs/2307.15043)
- (2023) [AutoDAN: Generating Stealthy Jailbreak Prompts on Aligned Large Language Models](https://arxiv.org/abs/2310.04451)
- (2023) [Jailbreaking Black Box Large Language Models in Twenty Queries (PAIR)](https://arxiv.org/abs/2310.08419)

### Agentic Red-Teaming for Jailbreak

Attack agents use task decomposition, feedback evaluation, self-reflection, memory, and multi-turn optimization to autonomously discover strategies that induce a target agent to complete complex harmful tasks.

- (2025) [Agent vs. Agent: Automated Data Generation and Red-Teaming for Custom Agentic Workflows (Red-Agent-Reflect)](https://aclanthology.org/2025.emnlp-industry.62/)
- (2024) [RedAgent: Red Teaming Large Language Models with Context-Aware Autonomous Language Agent](https://arxiv.org/abs/2407.16667)
- (2025) [RedCodeAgent: Automatic Red-Teaming Agent against Diverse Code Agents](https://arxiv.org/abs/2510.02609)
- (2026) [TRACE: Task-Aware Adaptive Self-Evolving Agentic Jailbreaking](https://arxiv.org/abs/2605.30883)
- (2025) [X-Teaming: Multi-Turn Jailbreaks and Defenses with Adaptive Multi-Agents](https://arxiv.org/abs/2504.13203)

<a id="long-term-memory-risks"></a>

## 1.3 Long-Term Memory Risks

Long-term memories are automatically retrieved and reused as trusted context in future sessions. A single poisoning event can therefore cause stealthy, persistent, and transmissible behavioral manipulation.

### Direct Long-Term Memory Poisoning

Attackers directly contaminate RAG corpora, knowledge bases, retrieval indexes, graph structures, or retrieved evidence so that malicious content is recalled by future queries.

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

### Indirect Interaction-Based Memory Injection

Rather than modifying storage directly, an attacker uses ordinary dialogues, queries, web observations, or environmental content to induce the agent to write malicious information into long-term memory.

- (2025) [Memory Injection Attacks on LLM Agents via Query-Only Interaction (MINJA)](https://arxiv.org/abs/2503.03704)
- (2026) [Poison Once, Exploit Forever: Environment-Injected Memory Poisoning Attacks on Web Agents (eTAMP)](https://arxiv.org/abs/2604.02623)

### Backdoor Attacks

Malicious memories remain dormant under ordinary inputs and perform targeted manipulation only when a particular trigger, query, topic, or contextual pattern appears.

- (2024) [AgentPoison: Red-Teaming LLM Agents via Poisoning Memory or Knowledge Bases](https://arxiv.org/abs/2407.12784)
- (2025) [PR-Attack: Coordinated Prompt-RAG Attacks via Bilevel Optimization](https://arxiv.org/abs/2504.07717)

<a id="environment-side-attacks"></a>

## 1.4 Environment-Side Attacks

Attackers manipulate web pages, documents, GUIs, terminals, APIs, or tool results perceived by an agent, causing untrusted data to be interpreted as high-priority instructions.

### Web Injection Attacks

Malicious instructions are embedded in HTML, CSS, hidden text, images, PDFs, forms, or other web elements to hijack browsing agents.

- (2025) [EIA: Environmental Injection Attack on Generalist Web Agents for Privacy Leakage](https://openreview.net/forum?id=xMOLUzo2Lk)
- (2025) [WASP: Benchmarking Web Agent Security against Prompt Injection Attacks](https://arxiv.org/abs/2504.18575)
- (2025) [WebInject: Prompt Injection Attack to Web Agents](https://aclanthology.org/2025.emnlp-main.104/)
- (2024) [Dissecting Adversarial Robustness of Multimodal LM Agents (VisualWebArena-Adv)](https://arxiv.org/abs/2406.12814)
- (2026) [MUZZLE: Adaptive Agentic Red-Teaming of Web Agents against Indirect Prompt Injection Attacks](https://arxiv.org/abs/2602.09222)

### Malicious Injection in Computer-Use Environments

Files, terminal output, notifications, pop-ups, screenshots, buttons, and mobile overlays manipulate the perception, grounding, and system operations of GUI or OS agents.

- (2025) [OS-Harm: A Benchmark for Measuring Safety of Computer Use Agents](https://arxiv.org/abs/2506.14866)
- (2025) [RedTeamCUA: Realistic Adversarial Testing of Computer-Use Agents in Hybrid Web-OS Environments](https://arxiv.org/abs/2505.21936)
- (2025) [RiOSWorld: Benchmarking the Risk of Multimodal Computer-Use Agents](https://arxiv.org/abs/2506.00618)
- (2026) [AgentHazard: A Benchmark for Evaluating Harmful Behavior in Computer-Use Agents](https://arxiv.org/abs/2604.02947)
- (2025) ["Your AI, My Shell": Demystifying Prompt Injection Attacks on Agentic AI Coding Editors](https://arxiv.org/abs/2509.22040)
- (2025) [Attacking Vision-Language Computer Agents via Pop-Ups](https://aclanthology.org/2025.acl-long.411/)
- (2025) [Evaluating the Robustness of Multimodal Agents against Active Environmental Injection Attacks (AEIA)](https://arxiv.org/abs/2503.02539)

### Tool-Output Injection

Malicious instructions arrive through search results, API responses, database records, emails, command output, or MCP server responses and influence subsequent planning and tool calls.

- (2024) [InjecAgent: Benchmarking Indirect Prompt Injections in Tool-Integrated LLM Agents](https://arxiv.org/abs/2403.02691)
- (2024) [ToolSword: Unveiling Safety Issues of Large Language Models in Tool Learning across Three Stages](https://arxiv.org/abs/2402.10753)
- (2023) [Benchmarking and Defending against Indirect Prompt Injection Attacks on Large Language Models (BIPIA)](https://arxiv.org/abs/2312.14197)
- (2025) [Attractive Metadata Attack: Inducing LLM Agents to Invoke Malicious Tools (AMA)](https://arxiv.org/abs/2508.02110)
- (2025) [ChatInject: Abusing Chat Templates for Prompt Injection in LLM Agents](https://arxiv.org/abs/2509.22830)
- (2026) [AdapTools: Adaptive Tool-Based Indirect Prompt Injection Attacks on Agentic LLMs](https://arxiv.org/abs/2602.20720)

---

<a id="security-evaluation-benchmarks"></a>

# 2. Security Evaluation Benchmarks

Safety evaluation has moved from static response checking to behavioral assessment. It now examines not only whether an agent generates harmful text, but also whether its tool calls, interaction trajectory, and final environment state are safe.

<a id="domain-specific-agent-safety-benchmarks"></a>

## 2.1 Domain-Specific Agent Safety Benchmarks

### Tool-Use Safety Benchmarks

These benchmarks evaluate malicious user requests, tool-output injection, tool and protocol metadata poisoning, dangerous arguments, and final execution states.

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

### Web-Browsing Safety Benchmarks

These benchmarks evaluate indirect prompt injection, malicious user abuse, policy violations, completion of page-level attacker goals, and final web states.

- (2025) [WASP: Benchmarking Web Agent Security against Prompt Injection Attacks](https://arxiv.org/abs/2504.18575)
- (2024) [ST-WebAgentBench: A Benchmark for Evaluating Safety and Trustworthiness in Web Agents](https://arxiv.org/abs/2410.06703)
- (2025) [SafeArena: Evaluating the Safety of Autonomous Web Agents](https://arxiv.org/abs/2503.04957)

### Computer and Mobile Operation Safety Benchmarks

These benchmarks evaluate GUI perception, cross-application interaction, file and terminal operations, sensitive permissions, irreversible actions, and persistent environmental side effects.

- (2025) [OS-Harm](https://arxiv.org/abs/2506.14866)
- (2025) [RiOSWorld](https://arxiv.org/abs/2506.00618)
- (2025) [RedTeamCUA / RTC-Bench](https://arxiv.org/abs/2505.21936)
- (2026) [AgentHazard](https://arxiv.org/abs/2604.02947)
- (2024) [MobileSafetyBench: Evaluating Safety of Autonomous Agents in Mobile Device Control](https://arxiv.org/abs/2410.17520)
- (2025) [GhostEI-Bench: Environmental Injection in Dynamic On-Device Environments](https://arxiv.org/abs/2510.20333)

<a id="generalist-agent-safety-benchmarks"></a>

## 2.2 Generalist Agent Safety Benchmarks

### Skill-Based Agent Behavioral Safety Benchmarks

Given a user task and one or more skills, the agent executes the task in an environment. Safety is judged from responses, tool evidence, or final state changes across the skill-mediated execution.

- (2026) [Skill-Inject](https://arxiv.org/abs/2602.20156)
- (2026) [SkillSafetyBench](https://arxiv.org/abs/2605.12015)
- (2026) [SkillAttack](https://arxiv.org/abs/2604.04989)
- (2026) [SCR-Bench](https://arxiv.org/abs/2606.15242)
- (2026) [OpenSkillRisk](https://arxiv.org/abs/2607.20121)
- (2026) [HarmfulSkillBench: How Do Harmful Skills Weaponize Your Agents?](https://arxiv.org/abs/2604.15415)
- (2026) [BioSkillSafety: A Systematic Benchmark for Evaluating Agent Skill Safety in Bioinformatics](https://openreview.net/forum?id=iIQ8DOGu8S)
- (2026) [SkillHarm](https://arxiv.org/abs/2606.02540)
- (2026) [SkillTrojan](https://arxiv.org/abs/2604.06811)

### Malicious Skill Detection Benchmarks

Instead of executing a user task, these benchmarks ask a rule system, model, static analyzer, or verifier to inspect the skill package itself and detect semantic, code-level, and mixed attacks.

- (2026) [Agent Skills in the Wild: An Empirical Study of Security Vulnerabilities at Scale](https://arxiv.org/abs/2601.10338)
- (2026) [SkillSieve: A Hierarchical Triage Framework for Detecting Malicious AI Agent Skills](https://arxiv.org/abs/2604.06550)
- (2026) [MalSkillBench: A Runtime-Verified Benchmark of Malicious Agent Skills](https://arxiv.org/abs/2606.07131)
- (2026) [SkillsMetric: Mapping the Detection Boundary of Static Analysis for Malicious Agent Skills](https://arxiv.org/abs/2608.08468)

<a id="offline-trajectory-auditing"></a>

## 2.3 Offline Trajectory Auditing

### Trajectory-Level Safety Detection

Complete multi-step interaction records are provided to safety judges, which must detect gradually emerging risks, localize risky steps, and explain causal chains.

- (2024) [R-Judge: Benchmarking Safety Risk Awareness for LLM Agents](https://arxiv.org/abs/2401.10019)
- (2025) [AgentAuditor: Human-Level Safety and Security Evaluation for LLM Agents (ASSEBench)](https://arxiv.org/abs/2506.00641)
- (2026) [ATBench: A Diverse and Realistic Agent Trajectory Benchmark for Safety Evaluation and Diagnosis](https://arxiv.org/abs/2604.02022)

### Step-Level Safety Detection

Given the current context and a candidate action, the evaluator decides before execution whether a browser action, code command, or tool call should be allowed, blocked, or verified further.

- (2025) [AGrail: A Lifelong Agent Guardrail with Effective and Adaptive Safety Detection (Safe-OS)](https://arxiv.org/abs/2502.11448)
- (2025) [ShieldAgent: Shielding Agents via Verifiable Safety Policy Reasoning (ShieldAgent-Bench)](https://arxiv.org/abs/2503.22738)
- (2026) [ToolSafe: Enhancing Tool Invocation Safety via Proactive Step-Level Guardrail and Feedback (TS-Bench)](https://arxiv.org/abs/2601.10156)

---

<a id="security-defense-methods"></a>

# 3. Security Defense Methods

<a id="input-and-context-filtering"></a>

## 3.1 Input and Context Filtering

### Skill Risk Scanning

Before a skill is installed, integrated, or invoked, scanners jointly inspect natural-language declarations, permissions, dependencies, executable scripts, and cross-skill data flows.

- (2026) [ClawVet: 6-Pass Security Scanner for OpenClaw Skills](https://www.npmjs.com/package/clawvet)
- (2026) [Agent Skills in the Wild / SkillScan](https://arxiv.org/abs/2601.10338)
- (2026) [SkillSieve](https://arxiv.org/abs/2604.06550)
- (2026) [SkillProbe: Security Auditing for Emerging Agent Skill Marketplaces via Multi-Agent Collaboration](https://arxiv.org/abs/2603.21019)

### Prompt Injection and Jailbreak Guardrails

Lightweight detectors or safety classifiers are deployed at boundaries around user inputs, retrieved content, web data, tool outputs, and model responses.

- (2025) [Llama Prompt Guard 2](https://github.com/meta-llama/PurpleLlama/tree/main/Llama-Prompt-Guard-2)
- (2025) [PIGuard: Prompt Injection Guardrail via Mitigating Overdefense for Free](https://aclanthology.org/2025.acl-long.1468/)
- (2023) [Llama Guard: LLM-Based Input-Output Safeguard for Human-AI Conversations](https://arxiv.org/abs/2312.06674)
- (2025) [Llama Guard 4](https://www.llama.com/docs/model-cards-and-prompt-formats/llama-guard-4/)
- (2025) [Aegis 2.0: A Diverse AI Safety Dataset and Risks Taxonomy for Alignment of LLM Guardrails](https://arxiv.org/abs/2501.09004)
- (2025) [SafeRoute: Adaptive Model Selection for Efficient and Accurate Safety Guardrails](https://aclanthology.org/2025.findings-acl.105/)
- (2025) [Qwen3Guard Technical Report](https://arxiv.org/abs/2510.14276)
- (2026) [SingGuard-NSFA: Extensible Guardrails for Agentic AI](https://arxiv.org/abs/2607.13081)
- (2025) [ShieldHead: Decoding-Time Safeguard for Large Language Models](https://aclanthology.org/2025.findings-acl.932/)

### Memory Guardrails

These defenses cover memory writing, retrieval, reasoning, and recovery through provenance verification, consistency checking, anomaly detection, causal auditing, and robustness certification.

- (2025) [A-MemGuard: Defending against Memory Poisoning in LLM Agents](https://arxiv.org/abs/2510.02373)
- (2026) [Your Agent's Memories Are Not Its Own: Forged Reasoning Attacks on LLM Agent Memory and Defenses (SENTINEL)](https://arxiv.org/abs/2607.05029)
- (2026) [MEMSAD: Gradient-Coupled Anomaly Detection for Memory Poisoning in Retrieval-Augmented Agents](https://arxiv.org/abs/2605.03482)
- (2026) [MemShield: A Three-Tier Retrieval-Time Defense against Coordinated Memory Poisoning](https://arxiv.org/search/?query=%22MemShield%22&searchtype=all)
- (2026) [MIND: Memory Injection Defense via Intent-Aware Information Bottleneck](https://arxiv.org/abs/2607.28103)
- (2026) [MemAudit: Post-Hoc Auditing of Poisoned Agent Memory](https://arxiv.org/abs/2605.23723)
- (2026) [SMSR: Certified Defence against Runtime Memory Poisoning in Persistent LLM Agent Systems](https://arxiv.org/abs/2606.12703)

<a id="decision-and-control-integrity"></a>

## 3.2 Decision and Control Integrity

### Harness-Externalized Defenses

The orchestration layer outside the model restructures or isolates untrusted context and constrains planning and control flow through task alignment, tool dependency graphs, and information-flow control.

- (2024) [Defending against Indirect Prompt Injection Attacks with Spotlighting](https://arxiv.org/abs/2403.14720)
- (2024) [StruQ: Defending against Prompt Injection with Structured Queries](https://arxiv.org/abs/2402.06363)
- (2024) [The Task Shield: Enforcing Task Alignment to Defend against Indirect Prompt Injection](https://arxiv.org/abs/2412.16682)
- (2025) [IPIGuard: A Tool Dependency Graph-Based Defense against Indirect Prompt Injection](https://aclanthology.org/2025.emnlp-main.53/)
- (2025) [Defeating Prompt Injections by Design (CaMeL)](https://arxiv.org/abs/2503.18813)

### Alignment-Internalized Defenses

Instruction hierarchy training, supervised fine-tuning, preference optimization, and reinforcement learning internalize trust priorities and safe tool-use policies within the model's decision policy.

- (2024) [The Instruction Hierarchy: Training LLMs to Prioritize Privileged Instructions](https://arxiv.org/abs/2404.13208)
- (2024) [SecAlign: Defending against Prompt Injection with Preference Optimization](https://arxiv.org/abs/2410.05451)
- (2024) [Towards Tool Use Alignment of Large Language Models (ToolAlign)](https://aclanthology.org/2024.emnlp-main.82/)
- (2025) [AgentAlign: Navigating Safety Alignment in the Shift from Informative to Agentic LLMs](https://arxiv.org/abs/2505.23020)
- (2025) [ToolSafety: A Comprehensive Dataset for Enhancing Safety in LLM-Based Agent Tool Invocations](https://aclanthology.org/2025.emnlp-main.714/)
- (2025) [The Alignment Waltz: Jointly Training Agents to Collaborate for Safety](https://arxiv.org/abs/2510.08240)
- (2026) [On-Policy Self-Evolution via Failure Trajectories for Agentic Safety Alignment (FATE)](https://arxiv.org/abs/2605.11882)
- (2026) [ToolHazard: Scaling Adversarial Environments for Security Evaluation and Alignment of LLM-based Agents](https://arxiv.org/abs/2608.11878)

<a id="runtime-monitoring-and-enforcement"></a>

## 3.3 Runtime Monitoring and Enforcement

### Planning-Stage Auditing

Complete plans are checked before any external action executes to identify dangerous goals, privilege violations, and hazardous action compositions.

- (2025) [Building a Foundational Guardrail for General Agentic Systems via Synthetic Data (Safiron)](https://arxiv.org/abs/2510.09781)

### Step-Level Monitoring

Before each tool call or environment action is committed, the system inspects the reasoning state, action semantics, and arguments, then blocks, corrects, confirms, or formally verifies the action.

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

### Trajectory-Level Review

Partial or complete execution histories are analyzed to detect cross-step privilege escalation, cross-tool information leakage, and cumulative policy violations, supporting root-cause diagnosis and continual improvement.

- (2025) [AgentAuditor](https://arxiv.org/abs/2506.00641)
- (2026) [AgentDoG 1.5: A Lightweight and Scalable Alignment Framework for AI Agent Safety and Security](https://arxiv.org/abs/2605.29801)
- (2026) [BraveGuard: From Open-World Threats to Safer Computer-Use Agents](https://arxiv.org/abs/2606.01166)

---

<a id="research-outlook"></a>

# 4. Research Outlook

The survey summarizes future research as a closed loop of **risk generation, risk diagnosis, and safety evolution**:

1. **Automatic Generation of Adversarial Environments and Safety Data**: automatically construct executable, verifiable, and continuously evolving adversarial environments and safety data;
2. **Fine-Grained Safety Attribution over Agent Trajectories**: localize risk sources, critical steps, and causal chains along long-horizon interaction trajectories;
3. **Adversarial-Feedback-Driven Continual Safety Evolution**: convert emerging attacks and failure trajectories into training feedback so safety policies can continually evolve.

## Citation

If this list supports your research, please cite the original survey and the corresponding papers. The survey's formal BibTeX entry can be added here once it becomes available.

## Contributing

Issues and pull requests that add new papers, code repositories, datasets, or corrections are welcome. Please follow the existing taxonomy and use this format:

```markdown
- (Year) [Paper Title](Paper URL)
```
