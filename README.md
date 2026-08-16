# Hi, I'm Jay 👋

[中文](./README.zh-CN.md)

I'm a CS student exploring **AI agent runtimes, evaluation, and adaptive execution**.

I learn by building small, inspectable systems and testing concrete questions: how agents navigate repositories, when more complex execution strategies are actually worth their cost, and how runtime policies can make those choices more reliably.

> **Build → measure → inspect failures → iterate.**

## Featured Projects

### [mini-Pi](https://github.com/justlearner010/mini-Pi)

**A small, readable TypeScript terminal agent for studying coding-agent internals.**

Rather than cloning a full coding assistant, mini-Pi keeps the runtime deliberately compact so I can study each layer directly: provider integration, tool calling, the agent loop, context management, repository navigation, permissions, CLI/TUI behavior, and evaluation.

Current work includes:

- a bounded, syntax-level **Repo Index** for TypeScript/JavaScript projects;
- query-aware **Repo Maps** that help the agent locate relevant files before reading source;
- runtime-enforced tool permission boundaries;
- reproducible local and live-provider evaluations of repository navigation behavior.

One external-repository evaluation exposed a weak lexical ranking baseline (product-code Top-3: **1/5**); adding scope/package/role-aware ranking improved it to **5/5** on the same five tasks. The point of the project is not the number itself, but the loop: build a mechanism, measure it, find where it fails, then revise it.

→ [Repository](https://github.com/justlearner010/mini-Pi) · [Experiments](https://github.com/justlearner010/mini-Pi/tree/main/docs/experiments)

---

### [Adaptive Agent Runtime Lab](https://github.com/justlearner010/adaptive-agent-runtime-lab)

**A research-oriented testbed for one question: which execution strategy should an agent use for a given task?**

The runtime implements and compares **Direct, ReAct, and Subagent** execution under a shared evaluation harness. Each strategy is measured using structured traces for correctness, LLM calls, tokens, latency, tool calls, and subagent spawns.

The current experimental loop is:

`Task → Policy → Execution Strategy → Trace → Evaluation`

Preliminary results from the current single-model benchmark suggest that simpler execution is a much stronger baseline than expected: Direct was optimal on **31/40** evaluated tasks, while ReAct became necessary on tasks requiring external corpus search. These are deliberately treated as stage-specific findings rather than universal conclusions.

Longer-term, I want to explore whether execution policies can learn from task features and runtime signals instead of relying on fixed routing rules.

→ [Repository](https://github.com/justlearner010/adaptive-agent-runtime-lab) · [Research Notes](https://github.com/justlearner010/adaptive-agent-runtime-lab/blob/main/RESEARCH.md)

## Questions I'm Exploring

- How should coding agents navigate large repositories under limited context budgets?
- When do ReAct, planning, or subagents justify their additional cost?
- What signals should an agent runtime use to select an execution strategy?
- How should we evaluate agent behavior beyond a single final-answer accuracy score?
- Which runtime guarantees should be enforced by code rather than left to the model?

## How I Work

I prefer projects that leave evidence behind:

- **runnable systems** instead of architecture-only demos;
- **benchmarks and traces** instead of intuition-only claims;
- **failure cases and limitations** documented alongside positive results;
- **Issue → implementation → evaluation → revision** as a repeatable engineering loop.

I'm still early in the journey, so I use these projects as laboratories: each one should teach me something about how real agent systems behave, not just add another framework name to a résumé.

## Other Work

- [Adaptive Learning Agent](https://github.com/justlearner010/adaptive-learning-agent) — a notebook-first learning agent connecting learner profiles, staged plans, theory checks, and code labs.
- [CLI Text Tool](https://github.com/justlearner010/jay-first-cli-text-tool) — a tested Python CLI for text statistics, chunking, structured JSON output, and mock summarization.

## Connect

- GitHub: [@justlearner010](https://github.com/justlearner010)

If you're working on **agent runtimes, evals, coding agents, or execution strategy research**, I'd be interested in comparing notes, benchmarks, and failure cases.
