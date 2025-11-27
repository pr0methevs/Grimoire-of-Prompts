# Grimoire of Prompts

A curated collection of reusable prompts and instruction files (found online for free) tailored for large language models, designed to streamline prompt engineering, fine-tuning, and deployment across diverse NLP tasks. This repository also documents and organizes a wide range of prompt-engineering paradigms, styles, and best practices—from chain-of-thought and role-based prompting to instruction-hierarchy design, meta-prompting, and advanced conversational scaffolding—serving as both a practical toolkit and an educational reference for modern promptcraft.


Below are several prompt-engineering paradigms ranked by observed effectiveness across common LLM workloads (analysis, reasoning, summarization, planning, and optimization). Rankings are informed by benchmark results where available (e.g., Chain-of-Thought consistently delivering ~14–15% accuracy gains) and by community testing when formal benchmarks are sparse.

## Structured Reasoning 
> Top-Tier Methods

### Chain-of-Thought (CoT) / Stepwise Decomposition

Structured reasoning that forces the model to externalize intermediate steps.
Observed Benefit: ~15.6% accuracy improvement across reasoning, summarization, and analysis tasks.

Example Prompt:
```
Solve this problem step-by-step.  
1. Identify variables  
2. Break down subproblems  
3. Derive intermediate results  
4. Provide final answer
```

## Structured Decision Optimization Framework (SDOF)

A planning → execution → evaluation loop modeled after RL-style problem decomposition.

Example Prompt:
```
Define states, actions, and rewards for this optimization problem.  
Simulate iterative cycles of planning → execution → evaluation.
```

### 3C Prompt Framework (Clarity, Context, Constraints)

Enforce explicit structure on inputs.

Example Prompt:
```
Task: Analyze dataset X  
Context: Logs from service Y  
Constraints: Use bullet points, expert tone
```

## Self-Improvement & Self-Critique Methods

### Recursive Self-Improvement (RSIP)

Ask the model to iteratively refine its own outputs based on scoring or heuristics.

Example:
```
Generate three solutions.  
Score each (1–10) on feasibility.  
If highest score < 8, revise and regenerate.
```

### Adversarial Self-Critique

Alternate between “creator” and “critic” roles to evolve stronger outputs.

Example:
```
Propose solution A.  
Switch to critic: list flaws.  
Revise solution based on critique.
```

### Meta-Prompting & Self-Assessment

Ask the model to analyze and optimize its own reasoning chain or the prompt itself.

Example:
```
Review the reasoning above for missing assumptions and improve the chain.
```


## Multi-Agent & Distributed Reasoning

### A2A + MCP (Agent-to-Agent + Multi-Context Prompting)

Use multiple agents with different tools or contexts to cross-validate results.

Example:
```
Agent1: Research topic X  
Agent2: Verify the findings using tool Y  
Merge and reconcile both outputs
```

### THINK + RAT Framework

THINK: hierarchical decomposition

RAT: retrieval-augmented reasoning

Example:
```
THINK: Decompose the problem hierarchically.  
RAT: Retrieve evidence and reason aloud using it.
```


### Multi-Perspective Simulation (MPS)

Simulate multiple domain roles and synthesize conclusions.

Example:
```
As a CEO: provide strategic view.  
As an engineer: critique feasibility.  
Synthesize into a final decision.
```

### Discursive Paradigm

Agents debate proposals under explicit discussion rules.

Example:
```
Agent A proposes a design.  
Agent B challenges assumptions.  
Resolve by consensus or voting.
```

## Optimization & System-Level Techniques

### Evolutionary Solution Generation

Iteratively evolve candidate solutions using mutation and selection.

Example:
```
Generate 3 variants.  
Score fitness.  
Breed the top 2 into the next generation.
```

### Nested Role Anchoring

Assign staged roles: planner → executor → reviewer.

Example:
```
Planner: Outline solution.  
Executor: Implement.  
Reviewer: Polish and verify correctness.
```

### System Prompt Engineering

Use high-level system instructions to enforce stateful structure, memory, or conventions across steps.

Example:
```
System: Maintain a running memory of constraints and enforce sectioned outputs.
```

### Constraint-Focused Prompting

Test solutions under varying constraint levels to expose trade-offs.

Example:
```
Produce a solution under a strict budget.  
Repeat with relaxed constraints.  
Compare differences.
```

## Summary

Structured reasoning (CoT and related frameworks) remains the most reliable high-impact approach for LLM accuracy, particularly on analytical and multi-step tasks. Self-critique and multi-agent paradigms offer strong benefits for complex reasoning, design generation, and validation workflows. System-level orchestration and optimization frameworks further enhance robustness in production-grade applications.