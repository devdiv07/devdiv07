<div align="center">

# Divyansh Shukla

**Software & AI engineer, early in my career. I build backends and AI systems that behave predictably when something fails.**

Final-year CSE (AI) · Jaipur · [Portfolio](https://divyansh-shukla-portfolio.vercel.app/) · [LinkedIn](https://www.linkedin.com/in/divyanshshukla03/) · [Email](mailto:divyanshshukla7597@gmail.com)

</div>

---

I like engineering questions where a green test suite is not enough: what evidence supports the claim, what would falsify it, and does the implementation still hold when the input comes from somewhere independent?

My work sits where software has to keep a promise under failure: a refund retried after its response was lost, a verifier handed a malformed quote, model output that must pass a deterministic check before anything acts on it.

## Open-source contributions

<sub>Merged pull requests to the <a href="https://github.com/agentrust-io">AgenTrust</a> confidential-agent stack.</sub>

#### [cmcp#528](https://github.com/agentrust-io/cmcp/pull/528) · Delegate duplicate Intel TDX signature parsing

cMCP's own DCAP v4 parser sliced buffers using attacker-controlled lengths, which Python silently truncates. Following a maintainer's review suggestion, I replaced it with Agent Manifest's canonical parser, keeping cMCP's error contract. Two of the new malformed-length regressions failed against the old parser.

#### [ca2a#120](https://github.com/agentrust-io/ca2a/pull/120) · Verify each inbound delegation chain once

Every inbound peer request verified its delegation chain twice ([#105](https://github.com/agentrust-io/ca2a/issues/105)). The chain is now verified once, before holder proof, and the public `effective_scope()` stays defensive. An exact-once regression failed on the old code (`assert 2 == 1`), and a second test confirms that untrusted roots are still rejected.

#### [agent-manifest#323](https://github.com/agentrust-io/agent-manifest/pull/323) · TPM reference-simulator test vectors

This change is test-only. It adds RSASSA, RSAPSS and ECDSA vectors from the Microsoft/TCG TPM 2.0 reference simulator, so the maintainer-authored verifier ([#320](https://github.com/agentrust-io/agent-manifest/pull/320)) is checked against evidence it did not produce itself. 26 tests cover verification, tampering and scheme mismatches. The vectors are simulator output, not hardware captures.

#### [integrations#221](https://github.com/agentrust-io/integrations/pull/221) · Make incomplete Shadow AI scans explicit

Records without a usable agent identity were silently classified or crashed the scan. I added per-record diagnostics, strict failure on incomplete classification, and removed untested compatibility claims. A maintainer later moved Shadow AI into standalone tooling. It has no direct cMCP or Agent Manifest integration.

**In review:** [razorpay-mcp-server#114](https://github.com/razorpay/razorpay-mcp-server/pull/114) adds an optional refund idempotency key. It is still open.

## Selected projects

### [Financial Operation Core](https://github.com/devdiv07/financial-operation-core)

Durable execution for agent-initiated refunds when the provider's response is lost.

- It keeps business-operation identity separate from per-attempt IDs and persists the provider idempotency key, so retrying the same operation does not create a second refund. `UNKNOWN` is an explicit outcome.
- Razorpay Test Mode measurements are kept separate from mutation, crash and concurrency tests. This is at-least-once execution with provider deduplication, not a production system.

[5-minute demo](https://youtu.be/QcwbQ7QrX9o) · [Chaos lab](https://github.com/devdiv07/fincore-chaos-lab)

### [Multimodal Message Router](https://github.com/devdiv07/multimodal-message-router)

Routes messages, including images and voice notes, to notify, digest or mute. I built it solo in a 24-hour HackerRank challenge, then hardened it.

- Offline Whisper, OCR and BLIP output passes validation gates before it is used. Blank media and text-in-image instructions are not acted on. There are 277 tests.
- Action macro-F1 is 0.966 on 30 labelled examples, with leakage controls. My own ablation showed that vision and speech did *not* improve action accuracy.

### [PREFLIGHT](https://github.com/devdiv07/preflight-gate6)

A Razorpay AI Buildathon project: a gate that checks a payment-recovery agent's message against current provider state before it is sent.

- An LLM identifies what a message assumes. Deterministic contracts decide ALLOW, BLOCK or ESCALATE, and the model's output type has no verdict field.
- A self-audit found a defect in my own baseline. Correcting it cut the reported recall advantage from +0.556 to +0.302 on a 48-message synthetic pilot, and the result is labelled post-hoc.

[Live demo](https://preflight-gate6.vercel.app/)

<sub>Also: <a href="https://github.com/devdiv07/ClaimTrace">ClaimTrace</a>, a schema-validated VLM claim-verification pipeline.</sub>

 Toolkit

| | Used in the work above |
|---|---|
| **Languages** | Python (primary) · TypeScript (Next.js/React front ends) · Go (one PR in review) |
| **Backend & data** | FastAPI · MCP servers · Pydantic · PostgreSQL · SQLAlchemy · Alembic · SQLite · Docker |
| **AI & multimodal** | LLM structured output · faster-whisper · BLIP (Transformers) · RapidOCR/ONNX Runtime |
| **Verification** | pytest · mutation testing · regression tests checked against pre-fix code · reference vectors · ablations · ruff · mypy · bandit · GitHub Actions |

## Currently exploring

- **Attestation evidence:** where conformance evidence for Intel TDX and TPM 2.0 verifiers comes from.
- **[Screenshot provenance](https://github.com/devdiv07/when-is-a-screenshot-evidence):** a measurement study of when a computer-use agent's screenshot proves what an evaluator thinks it does.
- **[MIRROR](https://github.com/devdiv07/MIRROR):** a watchlist research assistant. Its data layer is built and tested offline. The product itself is still planned
