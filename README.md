Official repository for the Position survey paper:
# Toward General-Purpose AI: Beyond Next-Token Prediction to Cognitive Architectures

![Paper](https://img.shields.io/badge/Paper-ACM%20CSUR-blue)
![Status](https://img.shields.io/badge/Status-Under%20Review-orange)
![Topic](https://img.shields.io/badge/Topic-General--Purpose%20AI-purple)
![Benchmark](https://img.shields.io/badge/Benchmark-Coordination--Bench-red)
![Prediction](https://img.shields.io/badge/Prediction-24--Month%20Claim-purple)
![License](https://img.shields.io/badge/License-MIT-green)

Official repository for the survey paper:

**Toward General-Purpose AI: Beyond Next-Token Prediction to Cognitive Architectures**

## Overview

Recent foundation models, including large language models, multimodal models, and agentic systems, have achieved strong performance across many tasks. However, these systems still struggle with persistent memory, long-horizon control, compositional reasoning, dynamic adaptation, and cross-episode consistency.

This paper argues that the central bottleneck for general-purpose AI is not scale alone, but the absence of explicit mechanisms for **coordinating specialized functions over time**. We frame coordination as a missing computational primitive and propose that future progress will require stronger mechanisms for memory, reasoning, planning, control, and adaptive routing.

## Core Thesis

Current foundation models can often solve local tasks fluently, but they remain weak at global coordination.

In particular, they struggle when a task requires:

- maintaining constraints across multiple steps,
- coordinating memory and reasoning over time,
- switching rules dynamically,
- preserving goals across changing contexts,
- composing specialized capabilities reliably,
- adapting beyond a single prompt or episode.

We therefore argue that the next major step toward general-purpose AI will require **coordination-aware cognitive architectures**, rather than larger end-to-end models alone.

## Coordination Benchmark

This repository is designed to support the development of a lightweight benchmark suite, tentatively called:

**Coordination-Bench**

The goal of Coordination-Bench is to evaluate whether AI systems can coordinate multiple cognitive functions across time, constraints, and changing task demands.

### Target Capabilities

| Capability | What It Tests |
|---|---|
| Cross-Episode Memory | Whether information learned earlier can be reused later |
| Dynamic Rule Switching | Whether the model can change task rules without confusion |
| Global Constraint Tracking | Whether the model can maintain shared constraints across subtasks |
| Long-Horizon Reasoning | Whether reasoning remains consistent over multiple steps |
| Interference Control | Whether one task contaminates another task |
| Tool and Memory Coordination | Whether retrieval, planning, and action are integrated correctly |
| Adaptive Reconfiguration | Whether the system can reorganize behavior when task demands change |

## Example Benchmark Tasks

### 1. Global Constraint Coordination

The model must satisfy several local constraints while also obeying a global constraint.

Example:

- Generate three sections.
- Each section must satisfy its own rule.
- The total number of tokens across all sections must equal a fixed budget.
- The model must detect infeasible constraints instead of hallucinating a solution.

### 2. Dynamic Rule Switching

The model receives changing rules during the task.

Example:

- Rule A: sort items alphabetically.
- Rule B: classify items semantically.
- Rule C: reverse the previous operation.
- The model must switch rules when signaled and preserve the current control state.

### 3. Interference Control

The model performs two different tasks in parallel.

Example:

- Task A: mathematical reasoning.
- Task B: creative writing.
- The model must prevent vocabulary, style, and constraints from one task leaking into the other.

### 4. Cross-Episode Coordination

The model is given information in one episode and tested on related reasoning in a later episode.

Example:

- Episode 1: introduce facts, goals, and constraints.
- Episode 2: ask the model to reason using those facts under new constraints.
- The model must retain and reuse the relevant information without contradiction.

## 24-Month Prediction Claim

We include a falsifiable prediction to make the coordination thesis testable.

**Prediction:**  
Within the next 24 months, scaling end-to-end foundation models alone will continue to improve local task performance, but will not fully resolve failures in cross-episode memory, dynamic rule switching, global constraint tracking, and long-horizon coordination unless explicit coordination mechanisms are introduced.

This claim can be evaluated by testing future models on Coordination-Bench-style tasks.

### Prediction Evaluation Criteria

The prediction is supported if future models show:

- improved fluency and local accuracy,
- but persistent failures in multi-step coordination,
- weak cross-episode memory,
- inconsistent rule switching,
- poor global constraint satisfaction,
- and fragile integration of tools, memory, and reasoning.

The prediction is weakened if future end-to-end models solve these tasks robustly without explicit memory, routing, control, tool coordination, or modular architecture.

## Key Contributions

- **Coordination-Centric View:** We identify coordination across time as a central bottleneck for general-purpose AI.
- **Cognitive Architecture Framing:** We connect AI systems with cognitive science and neuroscience accounts of memory, reasoning, perception, action, and control.
- **Benchmark Motivation:** We argue that current benchmarks are insufficient for testing cross-episode coordination and dynamic adaptation.
- **Prediction Claim:** We formulate a 24-month falsifiable claim about the limits of scale-only progress.
- **Research Roadmap:** We outline directions for coordination-aware architectures, evaluation protocols, and adaptive AI systems.

## Research Themes

| Theme | Description |
|---|---|
| Foundation Models | Large-scale language, vision, and multimodal models |
| Coordination | Mechanisms for organizing memory, reasoning, perception, and action |
| Cognitive Architectures | AI systems inspired by human cognition and brain networks |
| Agentic AI | Planning, tool use, memory, and environment interaction |
| Neuro-Symbolic AI | Integration of neural learning with explicit reasoning |
| World Models | Internal representations of environment dynamics |
| Mixture-of-Experts | Sparse routing and modular specialization |
| Reinforcement Learning | Sequential decision-making and learning through interaction |
| Evaluation | Benchmarks for memory, reasoning, adaptation, and coordination |

## Research Highlights and Related Resources

This section provides curated resources related to coordination-centric general-purpose AI, foundation models, agentic AI, cognitive architectures, and evaluation benchmarks.

### Coordination-Centric AI and Agentic Systems

| System / Concept | Focus | Key Idea | Links | Status |
|---|---|---|---|---|
| ReAct | Reasoning + Acting | Interleaves reasoning with tool/environment actions | [Paper](https://arxiv.org/abs/2210.03629) | Available |
| Reflexion | Agentic Memory | Uses verbal feedback and memory for iterative improvement | [Paper](https://arxiv.org/abs/2303.11366) | Available |
| AutoGPT | Autonomous Agents | Goal-driven autonomous task execution | [GitHub](https://github.com/Significant-Gravitas/AutoGPT) | Available |
| BabyAGI | Task Loop Agents | Task creation, prioritization, and execution loop | [GitHub](https://github.com/yoheinakajima/babyagi) | Available |
| MetaGPT | Multi-Agent Framework | Role-based multi-agent collaboration for software tasks | [GitHub](https://github.com/geekan/MetaGPT) | Available |
| AutoGen | Multi-Agent Conversation | Framework for multi-agent LLM workflows | [GitHub](https://github.com/microsoft/autogen) | Available |
| LangChain | Tool-Augmented LLMs | Framework for agents, tools, memory, and RAG | [GitHub](https://github.com/langchain-ai/langchain) | Available |
| CrewAI | Agent Teams | Role-based collaborative AI agents | [GitHub](https://github.com/crewAIInc/crewAI) | Available |

### Foundation Models and Reasoning Models

| Model | Organization | Main Capability | Links | Status |
|---|---|---|---|---|
| GPT-4 / GPT-4.5 | OpenAI | General-purpose language and multimodal reasoning | [OpenAI](https://openai.com/) | Available |
| Claude | Anthropic | Long-context reasoning and safety-focused dialogue | [Anthropic](https://www.anthropic.com/) | Available |
| Gemini | Google DeepMind | Multimodal reasoning and long-context understanding | [Google AI](https://ai.google.dev/) | Available |
| DeepSeek-R1 | DeepSeek | Reasoning-oriented LLM | [GitHub](https://github.com/deepseek-ai/DeepSeek-R1) | Available |
| Qwen | Alibaba | Open-weight LLM and multimodal model family | [GitHub](https://github.com/QwenLM/Qwen) | Available |
| Llama | Meta | Open-weight foundation model family | [Meta AI](https://ai.meta.com/llama/) | Available |
| Phi | Microsoft | Small reasoning-oriented language models | [Microsoft](https://www.microsoft.com/en-us/research/) | Available |
| Grok | xAI | Real-time information-oriented assistant | [xAI](https://x.ai/) | Available |

### Large Reasoning Models and Inference-Time Computation

| Model / Method | Focus | Key Idea | Links | Status |
|---|---|---|---|---|
| Chain-of-Thought | Reasoning Prompting | Elicits intermediate reasoning steps | [Paper](https://arxiv.org/abs/2201.11903) | Available |
| Tree-of-Thoughts | Search-Based Reasoning | Explores multiple reasoning paths | [Paper](https://arxiv.org/abs/2305.10601) | Available |
| Self-Consistency | Reasoning Robustness | Samples multiple reasoning paths and aggregates answers | [Paper](https://arxiv.org/abs/2203.11171) | Available |
| OpenAI o-series | Inference-Time Reasoning | Uses extended reasoning-time computation | [OpenAI](https://openai.com/) | Available |
| DeepSeek-R1 | RL-Based Reasoning | Reasoning model trained with reinforcement learning methods | [GitHub](https://github.com/deepseek-ai/DeepSeek-R1) | Available |
| Qwen Reasoning Models | Hybrid Reasoning | Supports explicit reasoning-style generation | [GitHub](https://github.com/QwenLM/Qwen) | Available |

### Vision-Language and Multimodal Models

| Model | Organization | Key Feature | Links | Status |
|---|---|---|---|---|
| CLIP | OpenAI | Contrastive image-text representation learning | [GitHub](https://github.com/openai/CLIP) | Available |
| LLaVA | Open Source | Instruction-tuned vision-language model | [GitHub](https://github.com/haotian-liu/LLaVA) | Available |
| Qwen-VL | Alibaba | Multilingual vision-language model family | [GitHub](https://github.com/QwenLM/Qwen-VL) | Available |
| InternVL | OpenGVLab | General-purpose vision-language model | [GitHub](https://github.com/OpenGVLab/InternVL) | Available |
| Flamingo | DeepMind | Few-shot multimodal learning | [Paper](https://arxiv.org/abs/2204.14198) | Paper |
| BLIP / BLIP-2 | Salesforce | Vision-language pretraining and captioning | [GitHub](https://github.com/salesforce/LAVIS) | Available |
| Kosmos | Microsoft | Multimodal large language model | [Paper](https://arxiv.org/abs/2302.14045) | Paper |

### Brain-Inspired and Cognitive Architectures

| Architecture | Type | Main Idea | Links | Status |
|---|---|---|---|---|
| Spiking Neural Networks | Neuromorphic AI | Event-driven computation inspired by biological spikes | [NEST](https://www.nest-simulator.org/) | Available |
| Neural Turing Machines | Memory-Augmented AI | Neural networks with external memory | [Paper](https://arxiv.org/abs/1410.5401) | Paper |
| Differentiable Neural Computers | Memory-Augmented AI | Learns to read/write from external memory | [Paper](https://www.nature.com/articles/nature20101) | Paper |
| World Models | Model-Based AI | Learns internal models of environment dynamics | [Paper](https://arxiv.org/abs/1803.10122) | Paper |
| Dreamer | Model-Based RL | Learns behavior from latent imagination | [GitHub](https://github.com/danijar/dreamerv3) | Available |
| MuZero | Planning + RL | Learns a model for planning without explicit rules | [Paper](https://www.nature.com/articles/s41586-020-03051-4) | Paper |
| Global Workspace Theory | Cognitive Architecture | Selective broadcasting across specialized systems | [Overview](https://en.wikipedia.org/wiki/Global_workspace_theory) | Concept |
| ACT-R | Cognitive Architecture | Symbolic cognitive architecture for human cognition | [Website](http://act-r.psy.cmu.edu/) | Available |

### Coordination-Bench: Proposed Evaluation Dimensions

| Dimension | What It Measures | Example Failure Mode |
|---|---|---|
| Global Constraint Tracking | Maintains shared constraints across subtasks | Correct local outputs but wrong global total |
| Dynamic Rule Switching | Switches rules based on changing control signals | Keeps applying old rule after new signal |
| Interference Control | Keeps parallel tasks separated | Math terms leak into creative writing task |
| Cross-Episode Memory | Reuses information from earlier sessions | Forgets prior facts or contradicts them |
| Long-Horizon Planning | Maintains goals over many steps | Drifts from original objective |
| Tool-Memory Coordination | Uses tools and memory consistently | Retrieves evidence but ignores it |
| Infeasibility Detection | Identifies impossible constraints | Hallucinates a solution instead of saying impossible |

### Benchmark Datasets and Evaluation Suites

| Benchmark | Focus | Why It Matters | Links | Status |
|---|---|---|---|---|
| BIG-Bench | Broad language reasoning | Tests diverse reasoning tasks | [GitHub](https://github.com/google/BIG-bench) | Available |
| ARC-AGI | Abstract reasoning | Tests abstraction and generalization | [Website](https://arcprize.org/) | Available |
| HELM | Holistic LLM Evaluation | Evaluates language models across scenarios | [Website](https://crfm.stanford.edu/helm/latest/) | Available |
| MMLU | Multitask knowledge | Tests broad academic knowledge | [Paper](https://arxiv.org/abs/2009.03300) | Available |
| GPQA | Graduate-level reasoning | Tests difficult scientific reasoning | [Paper](https://arxiv.org/abs/2311.12022) | Available |
| SWE-Bench | Software engineering | Evaluates real-world coding agents | [Website](https://www.swebench.com/) | Available |
| AgentBench | LLM agents | Evaluates agents in interactive environments | [GitHub](https://github.com/THUDM/AgentBench) | Available |
| MineDojo | Embodied AI | Minecraft-based open-ended agent learning | [Website](https://minedojo.org/) | Available |
| MMMU | Multimodal understanding | College-level multimodal reasoning | [Website](https://mmmu-benchmark.github.io/) | Available |
| LiveCodeBench | Coding evaluation | Dynamic coding benchmark | [Website](https://livecodebench.github.io/) | Available |

### Coordination Failure Modes

| Failure Mode | Description | Example |
|---|---|---|
| Local Fluency, Global Failure | Output looks good locally but violates global constraints | Correct paragraphs but wrong total word budget |
| Rule Persistence Failure | Model fails to preserve or switch task rules | Continues old sorting rule after new rule |
| Contextual Leakage | One task contaminates another | Technical vocabulary appears in unrelated creative task |
| Memory Fragmentation | Relevant information is retrieved but not integrated | RAG retrieves facts but answer contradicts them |
| Tool Misalignment | Tool output is ignored or misused | Calculator gives answer but model changes it |
| Over-Reliance on Prompt State | Model behaves correctly only inside one prompt | Fails when task continues across episodes |
| Infeasibility Hallucination | Model invents solution to impossible task | Produces invalid answer instead of detecting impossibility |

### 24-Month Prediction Tracking

| Claim | Evaluation Target | Supported If | Weakened If |
|---|---|---|---|
| Scale alone will improve local performance but not fully solve coordination | Future frontier models | Models improve fluency but still fail Coordination-Bench tasks | End-to-end models solve coordination tasks without explicit memory/control |
| Cross-episode memory will remain fragile | Multi-session tasks | Models forget or contradict prior episode information | Models reliably retain and reuse cross-session facts |
| Dynamic rule switching will remain inconsistent | Rule-switching tasks | Models show control drift after rule changes | Models switch rules reliably across long sequences |
| Tool use will not equal coordination | Tool-augmented tasks | Models use tools but fail global reasoning | Models integrate tools, memory, and goals consistently |
| Benchmarks will shift toward process evaluation | Evaluation research | New benchmarks score reasoning process and coordination | Static answer-only benchmarks remain dominant |

## Useful Links

- [ACM Computing Surveys](https://dl.acm.org/journal/csur)
- [BIG-Bench](https://github.com/google/BIG-bench)
- [ARC Prize / ARC-AGI](https://arcprize.org/)
- [HELM Evaluation](https://crfm.stanford.edu/helm/latest/)
- [AgentBench](https://github.com/THUDM/AgentBench)
- [SWE-Bench](https://www.swebench.com/)
- [MineDojo](https://minedojo.org/)
- [LLaVA](https://github.com/haotian-liu/LLaVA)
- [DeepSeek-R1](https://github.com/deepseek-ai/DeepSeek-R1)
- [Qwen](https://github.com/QwenLM/Qwen)
- [LangChain](https://github.com/langchain-ai/langchain)
- [AutoGen](https://github.com/microsoft/autogen)

## Repository Structure

```text
general-purpose-ai-cognitive-architectures/
├── README.md
├── figures/
├── tables/
├── prompts/
├── benchmark/
├── prediction-claim/
└── paper/
