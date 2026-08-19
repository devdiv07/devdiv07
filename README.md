# Divyansh Shukla

Final-year CSE (AI) student working on **reliability, open-source verification,
and hardware-attestation testing**.

I like engineering questions where a green test suite is not enough:
what evidence supports the claim, what would falsify it, and does the
implementation still hold when the input comes from somewhere independent?

---

## AgenTrust work

### Hardware-attestation verification

Recent work across the AgenTrust repositories has focused on verifier
correctness and evidence provenance.

- Reproduced a historical Intel TDX DCAP-v4 parser/fixture defect and isolated
  the difference to the six-byte `QE_REPORT_CERTIFICATION_DATA` wrapper.
- Compiled Intel's upstream QVL quote generator and used independently originated
  evidence to reproduce the structural distinction without physical TDX hardware.
- Generated TPM quote vectors with the Microsoft/TCG TPM 2.0 reference simulator
  and measured a signature/hash-agility false reject in a pinned Agent Manifest
  revision.

### Contributions

**[cMCP #528](https://github.com/agentrust-io/cmcp/pull/528)**  
Delegate duplicate Intel TDX signature-section parsing to Agent Manifest's
canonical parser, with regressions for overstated declared lengths.

**[cA2A #120](https://github.com/agentrust-io/ca2a/pull/120)**  
Remove redundant delegation-chain verification while preserving trusted-root,
holder-proof, and authorization ordering.

**[Agent Manifest #323](https://github.com/agentrust-io/agent-manifest/pull/323)**  
Simulator-driven reproduction, verifier fix, and reference-simulator regression
vectors for TPM signature/hash agility. Maintainer PR #320 subsequently landed
the canonical implementation.

---

## Selected engineering work

### [Financial Operation Core](https://github.com/devdiv07/financial-operation-core)

Durable execution for agent-initiated financial operations across retries,
crashes, concurrency, and uncertain provider outcomes.

- Separates logical operation identity from execution attempts and provider retry
  identity so retry safety is explicit rather than assumed.
- Measured Razorpay Test Mode behavior and backed the failure model with crash,
  concurrency, authorization-replay, and mutation tests.
- Public claims map to reproducible evidence rather than inferred API behavior.

### [Multimodal Message Router](https://github.com/devdiv07/multimodal-message-router)

A notify / digest / mute decision system with leakage-controlled evaluation,
explicit policy precedence, and 277 automated tests.

---

## Other open source

**[Razorpay MCP #114](https://github.com/razorpay/razorpay-mcp-server/pull/114)**  
Adds optional refund idempotency-key support to `create_refund` while preserving
existing behavior when omitted.

---

## Working with

Python · pytest · mutation testing · Git / GitHub · Docker · PostgreSQL ·
SQLAlchemy · REST APIs · TPM 2.0 / Intel TDX attestation work ·
LLM/VLM integration and evaluation

---

[LinkedIn](https://www.linkedin.com/in/divyanshshukla03/) ·
[Portfolio](https://divyansh-shukla-portfolio.vercel.app/) ·
[Email](mailto:divyanshshukla7597@gmail.com)

Final-year CSE (AI) · Jaipur
