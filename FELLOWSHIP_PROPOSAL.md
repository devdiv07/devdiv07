# Individual FOSS Contributor Fellowship — 3-Month Proposal

**Applicant:** Divyansh Shukla (`devdiv07`), Jaipur, India  
**Funding requested:** INR 90,000 total, equivalent to INR 30,000/month over 3 months of supported contribution time.  
**Application type:** Individual contributor support across public upstream projects.  
**Time period:** Three months from an agreed grant start date, not a claim that funding has already been awarded.

## Purpose

Support bounded, reproducible investigations of correctness and evidence provenance at security boundaries in existing open-source AI-agent tooling. Deliver credible tests, upstream proposals where justified, and public technical reports. The work is deliberately directed toward established upstream interfaces, not building an unvalidated standalone product or guaranteeing code merges.

## Evidence of prior work

1. **Four merged AgenTrust pull requests, all authored from `devdiv07`:**
   - [agent-manifest #323](https://github.com/agentrust-io/agent-manifest/pull/323): Microsoft/TCG TPM reference-simulator conformance vectors. The merged change is test and fixture only, not a new verification implementation.
   - [cmcp #528](https://github.com/agentrust-io/cmcp/pull/528): delegate TDX quote signature parsing to Agent Manifest.
   - [ca2a #120](https://github.com/agentrust-io/ca2a/pull/120): correct inbound delegation-chain verification.
   - [integrations #221](https://github.com/agentrust-io/integrations/pull/221): explicit unavailable-identity diagnostics and removal of unverified interoperability claims in Shadow AI. This does not imply direct cMCP integration exists.

2. **Published independent study:** [When Is a Screenshot Evidence?](https://github.com/devdiv07/when-is-a-screenshot-evidence) (Apache-2.0). Examines how a valid capture can fail to establish the identity of the displayed resource or actual application state. The study reports negative findings, adversarial results, limitations and reproducibility material; it does not claim complete application-state attestation.

3. **Python supply-chain research:** Reported a valid PEP 751 name-only selector bug via [Trivy Discussion #11402](https://github.com/aquasecurity/trivy/discussions/11402). A Trivy maintainer created [issue #11411](https://github.com/aquasecurity/trivy/issues/11411), assigned to a different contributor. The reported defect concerns dependency relationships, not demonstrated loss of vulnerability detection. A separate AI-assisted private research prototype (`pylock-fidelity`) remains unreleased, with no claimed external adoption.

## Three-month work plan and measurable milestones

**Month 1 — baseline and falsification.** Select a concrete correctness or evidence-provenance question grounded in active open-source agent-security tooling, considering maintainer feedback and existing functionality. Publish an accurately scoped technical note with environment, reproduction or negative result, observed behaviour, boundaries and test harness (where redistribution is permitted).

**Month 2 — upstream contribution or documented negative result.** If the evidence shows a concrete fixable issue, discuss it with maintainers and submit a narrowly scoped regression test and proposed change, or a substantive review of a related fix. If it does not, publish the results, explain why the suspected defect did not hold, and move to a bounded second target. Do not manufacture an issue or claim merges before they occur.

**Month 3 — verification and knowledge transfer.** Re-run the relevant reproductions or test cases independently where feasible, document the outcome and limitations, and publish one concise community-facing technical post, presentation or FOSS United forum update. Supply a final public report with links to issues, PRs, tests and evidence.

**Success measures within applicant control:** public research note and reproducibility artifacts; at least one informed upstream technical interaction or submitted contribution where evidence supports it; recorded verification results; public final report and community engagement. Upstream acceptance, code merge and number of discovered defects cannot be guaranteed.

## Funding use

**INR 90,000 total** to support approximately three months of part-time contributor time at **INR 30,000 per month**. This request is for sustenance and time spent researching, verifying, documenting and contributing to FOSS. It does not imply a prior award, guaranteed recurring salary or an existing paid position. Any payment documentation and bank details would be supplied privately to the funder if required; they are not part of the public manifest.

## AI assistance, authorship and limitations

AI coding assistants have been used for parts of implementation, test authoring, technical research and documentation. The applicant's role includes setting scope and acceptance criteria, directing investigations, selecting evidence and maintaining records of limitations. The private `pylock-fidelity` prototype explicitly documents AI-authored components and outstanding human code review; no claim is made that all code was independently human-authored or reviewed. During funded work, the applicant will review changes personally, follow each upstream project's AI contribution policies, and distinguish automated test success from independent correctness evidence. Public milestones will disclose material assistance and unresolved verification limits.

## Links

- GitHub profile: https://github.com/devdiv07
- Published screenshot study: https://github.com/devdiv07/when-is-a-screenshot-evidence
- Upstream merged pull requests: https://github.com/agentrust-io/agent-manifest/pull/323 · https://github.com/agentrust-io/cmcp/pull/528 · https://github.com/agentrust-io/ca2a/pull/120 · https://github.com/agentrust-io/integrations/pull/221
- Trivy discussion: https://github.com/aquasecurity/trivy/discussions/11402
- Maintainer-created issue: https://github.com/aquasecurity/trivy/issues/11411
