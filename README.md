# Divyansh Shukla

I build AI systems where the interesting part is the boundary — what the model is
allowed to decide, and what has to be deterministic, durable, and provable.

---

## Selected work

### [Financial Operation Core](https://github.com/devdiv07/financial-operation-core)

Durable execution for agent-initiated financial operations across retries, crashes,
and uncertain provider outcomes.

- Measured Razorpay Refund idempotency and recovery behaviour in **Test Mode**:
  after a lost response, retrying with the same key returned the original refund —
  while two different keys produced two refunds.
- Keeps four identities distinct — business operation, execution attempt, MCP request,
  and provider retry identity — because collapsing them is what silently duplicates
  money movement.
- Every public claim maps to an artifact in `EVIDENCE.md`, including a pilot that was
  **invalidated** and an interpretation that was **corrected** rather than quietly
  rewritten.

### [Multimodal Message Router](https://github.com/devdiv07/multimodal-message-router)

Decides whether a message should interrupt you now, wait for a digest, or be
suppressed — reading attached images and voice notes, not just text.

- Four perception layers (Whisper ASR, RapidOCR, BLIP captioning, video keyframes),
  each pinned and run deterministically behind a strict validation boundary.
- A 4-mode ablation harness measures whether those layers actually helped, under
  leakage-controlled evaluation — 0.966 action macro-F1.

---

## Open source

**[razorpay/razorpay-mcp-server#114](https://github.com/razorpay/razorpay-mcp-server/pull/114)** — open PR

Adds optional refund idempotency-key support to the `create_refund` MCP tool and
forwards the documented `X-Refund-Idempotency` header. The Go SDK already accepted
extra request headers; the tool passed `nil` and exposed no way to set one.

---

## Also here

- **[ClaimTrace](https://github.com/devdiv07/ClaimTrace)** — schema-safe multimodal
  claim verification: a vision model returns Pydantic-validated structured output,
  wrapped in deterministic rule checks and enforced schema validation.
- **[MIRROR](https://github.com/devdiv07/MIRROR)** — research-grade insider-conviction
  signal from SEC Form 4 filings. Explicitly not yet validated.

---

## Working with

Python · PostgreSQL · SQLAlchemy / Alembic · asyncio · Go · MCP and agent tool design ·
LLM evaluation and ablation · Ed25519 / request signing · Docker · GitHub Actions

---

[LinkedIn](https://www.linkedin.com/in/divyanshshukla03/) ·
[X](https://x.com/iam_divyansh7) ·
[Portfolio](https://divyansh-shukla-portfolio.vercel.app/) ·
[Email](mailto:divyanshshukla7597@gmail.com)

Final-year CSE (AI) · Jaipur
