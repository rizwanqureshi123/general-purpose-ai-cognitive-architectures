# Toward General-Purpose AI: Beyond Next-Token Prediction to Cognitive Architectures

![Paper](https://img.shields.io/badge/Paper-ACM%20CSUR-blue)
![Status](https://img.shields.io/badge/Status-Under%20Review-orange)
![Topic](https://img.shields.io/badge/Topic-General--Purpose%20AI-purple)
![License](https://img.shields.io/badge/License-MIT-green)

Official repository for the survey paper:
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
