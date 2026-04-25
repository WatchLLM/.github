<p align="center">
  <img src="https://raw.githubusercontent.com/WatchLLM/.github/refs/heads/main/profile/edited.png" width="500"/>
</p>

---

<p align="center">
  <strong>Reliability infrastructure for AI agents</strong>
</p>

<p align="center">
  <sub>
    Hallucinations. Silent failures. Non-determinism.<br/>
    <strong>You won't catch them in logs — we will.</strong>
  </sub>
</p>

<p align="center">
  <a href="https://watchllm.dev"><b>Join waitlist →</b></a>
  &nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="https://github.com/watchllm-dev/watchllm-docs"><b>Docs</b></a>
  &nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="https://github.com/watchllm-dev/watchllm-sdk"><b>SDK</b></a>
</p>

---

## What is WatchLLM?

WatchLLM is a **chaos + observability layer for AI agents**.

Not logs.
Not evals.
Not retries.

A system that **actively breaks your agent** before production does.

---

## Why this exists

AI systems don’t fail like traditional software.

They fail:

* inconsistently
* silently
* under edge conditions you didn’t simulate

You can pass 100 tests and still ship a broken agent.

WatchLLM closes that gap.

---

## What we build

<table>
<tr>
<td width="160"><code>watchllm-sdk</code></td>
<td>Inject chaos into your agent pipeline. Run in CI, local dev, or staging.</td>
</tr>
<tr>
<td><code>trace analysis</code></td>
<td>Understands agent decisions, not just logs.</td>
</tr>
<tr>
<td><code>severity scoring</code></td>
<td>Separates critical failures from noise.</td>
</tr>
<tr>
<td><code>CI gating</code></td>
<td>Blocks deploys when reliability drops.</td>
</tr>
</table>

---

## How it works

```id="flowblk1"
chaos engine -> trace capture -> failure detection -> severity scoring -> CI gate
```

---

## Why logs / evals are not enough

| Approach   | Limitation                                     |
| ---------- | ---------------------------------------------- |
| Logs       | Failures are visible only after users hit them |
| Evals      | Static and predictable                         |
| Retries    | Hide real issues instead of fixing them        |
| Monitoring | Detection happens too late                     |

WatchLLM focuses on **pre-failure detection**.

---

## Platform

* Edge-native (Cloudflare Workers)
* Zero cold starts
* Scales with usage
* Built for agent-native workflows

---

## Status

Early access. Building in public.

<p align="center">
  <a href="https://watchllm.dev"><strong>Get access →</strong></a>
</p>

---

<p align="center">
  <sub>Built by <a href="https://kaadz.me">@kaadz</a></sub>
</p>
