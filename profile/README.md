<div align="center">
  <img src="https://raw.githubusercontent.com/kaadipranav/kaadipranav/refs/heads/main/assets/img2.png"/>
</div>

> Agents are probabilistic. Infrastructure cannot be.

WatchLLM builds deterministic, local-first infrastructure that governs how autonomous coding agents read, write, and execute code — before unsafe changes reach disk.

## The Stack

| Layer | Component | Description |
|-------|-----------|-------------|
| Governance | `kernel` | Deterministic local runtime enforcement engine (Python, Tree-sitter AST) |
| Governance | `runtime` | High-performance Rust + Wasm implementation with JSON schema parity |
| Orchestration | `orchestrator` | Policy graph, model routing, and sub-agent spawning |
| Contracts | `schemas` | Central event, rule, policy, and violation schema contracts (v1) |
| Memory | `klyd` | Persistent architectural memory — extract, store, enforce design decisions |
| Observability | `replay` | Execution graph replay, DAG rendering, and runtime forensics |
| Reliability | `reliability` | Adversarial stress-testing, prompt injection, and sandboxed evaluation |
| Quality | `benchmarks` | Ecosystem-wide performance and regression benchmarking |
| Editor | `vscode` | VS Code extension — save interception, diagnostics, and inline governance |
| Docs | `docs` | Architecture, RFCs, threat model, roadmap, and gap analysis |
| Demos | `examples` | Curated scenarios: secrets, boundary enforcement, auth flow |

## Quick Links

- 🌐 [watchllm.dev](https://watchllm.dev)
- 📖 [Documentation](https://github.com/WatchLLM/docs)
- 🏗️ [Monorepo](https://github.com/WatchLLM/WATCHLLM)
- 📬 [support@watchllm.dev](mailto:support@watchllm.dev)
