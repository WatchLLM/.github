# WatchLLM

### Deterministic Write-Path Governance Layer for AI-Generated Code

WatchLLM is a security and governance gatekeeper designed to prevent AI coding assistants from introducing security vulnerabilities, broken module interfaces, or unauthorized boundary transgressions into production environments.

By intercepting code modifications **at the save boundary**, WatchLLM provides local, instant deterministic checks, ensuring that governance decisions are final and fast, while utilizing Large Language Models exclusively for explanations and remedial guidance.

---

## 🏛️ System Architecture

```
                       [ Developer Environment ]
                       
  +---------------------------------------------------------------+
  |  Editor Save / CLI check                                      |
  |  --> Runs local AST traversal (Tree-sitter) (<10ms)           |
  |  --> Validates Auth Rules, Secret Scans, & Boundaries         |
  +-------------------------------+-------------------------------+
                                  |
                                  +--> [ Pass ] --> Ingest to Cloudflare Worker
                                  |                 - Validates Clerk JWT
                                  |                 - Saves session & diff to D1
                                  |                 - Uploads raw code to R2
                                  |
                                  +--> [ Block ] -> Call Worker Explanation
                                                    - LLM review violation
                                                    - Suggests remedial fix
```

---

## 📦 The Ecosystem

| Repository | Scope | Description |
|---|---|---|
| **[WATCHLLM](https://github.com/WatchLLM/WATCHLLM)** | Public Core | Monorepo containing the CLI checking engine and the VS Code save-interception extension. |
| **[watchllm-cloud](https://github.com/WatchLLM/watchllm-cloud)** | Private Cloud | Cloudflare Workers orchestrating ingestion logging, D1 persistence, R2 code storage, and LLM reviews. |
| **[WATCHLLM-DOCS](https://github.com/WatchLLM/WATCHLLM-DOCS)** | Public Docs | Technical specifications, architecture decisions, and exhaustive manual setup guides. |
| **[WATCHLLM-SDK-PYTHON](https://github.com/WatchLLM/WATCHLLM-SDK-PYTHON)** | SDK & Lib | Reusable Python SDK for programmatic rule evaluation and package-based CLI tooling. |
| **[WATCHLLM-SDK-NODE](https://github.com/WatchLLM/WATCHLLM-SDK-NODE)** | SDK & Lib | Native Node.js SDK for JS/TS pipelines (Husky, pre-commits, custom linters). |

---

## 🔒 Core Governance Principles

1.  **Deterministic Enforcement First**: Governance rules (like auth requirements and forbidden modules) must be absolute, deterministic, and executable locally.
2.  **LLM is Explanation-Only**: Large Language Models must never decide whether code is blocked. They are restricted purely to telling developers *why* the deterministic engine blocked the change and *how* to resolve it.
3.  **Local Independence**: Editor save interception must remain network-independent and complete in under 200ms, guaranteeing high productivity even in disconnected states.
