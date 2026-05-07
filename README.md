# Pattern Intel
### Termination Integrity Scanner — 6-Agent Diagnostic System
**Built by Samir Saad**
[LinkedIn](https://www.linkedin.com/in/saadsamir/) · [GitHub](https://github.com/samirsaad786/termination-scanner)

> *"The pattern is always there. Someone has to be looking."*
> Companion tool to the article **"Your HR Data Isn't Just Inaccurate — It's a Liability Waiting to Happen"** — [INSERT LINKEDIN ARTICLE LINK WHEN PUBLISHED]

---

## What This Tool Does

Pattern Intel reads termination data the way a cardiologist reads an EKG — not as a record-keeping function, but as a diagnostic signal. Six specialized AI agents analyze your data sequentially, each doing one narrow job, then converge on a single brief that surfaces repeat violations, reason code inconsistencies, organizational clustering, policy gaps, documentation failures, and protected-class timing risks that may represent legal exposure.

---

## Agent Architecture

| Agent | Role | Why It Stays Isolated |
|---|---|---|
| **Agent 0 — Policy Parser** | Reads uploaded policy documents. Extracts structured rules before any data is touched. | Chain of custody — the standard must be set independently of the data it judges. |
| **Agent 1 — Identity Scanner** | Finds every employee ID appearing more than once. Flags rehire policy violations with exact policy citations. | Rehire violations carry independent legal exposure — WARN Act, unemployment eligibility, retaliation patterns. |
| **Agent 2 — Concentration Scanner** | Detects manager, location, and department clustering in a single unified pass. | Same cognitive operation, three lenses, one auditable output — keeps the architecture lean without sacrificing signal. |
| **Agent 3 — Documentation Gap Agent** | Maps each termination against extracted progressive discipline requirements. Flags missing steps. | Litigation-facing output. Must be traceable to a single, auditable agent. |
| **Agent 4 — Timing Pattern Agent** | Calculates proximity of termination dates to FMLA leave, ADA accommodation requests, and other protected events. | Protected-class timing is its own legal theory. Findings here must not be entangled with any other signal. |
| **Agent 5 — Synthesis Agent** | Assembles clean outputs from Agents 1–4. Produces the final diagnostic brief. | Never interprets raw data. Error traceability requires that any fault in the final report be assignable to a specific upstream agent. |

**Execution flow:** Agent 0 runs first in isolation. Agents 1 through 4 run sequentially, each receiving Agent 0's extracted policy ruleset plus the sanitized CSV. Agent 5 runs last, receiving only the structured JSON outputs of Agents 1–4 — never raw data. Sequential execution ensures no rate limit collisions and gives each agent full processing time.

---

## Getting Started

Pattern Intel runs entirely in your browser — no installation, no account, no backend.

**What you need:**
1. An Anthropic API key. Get one at [console.anthropic.com](https://console.anthropic.com). Standard API pricing applies — a typical analysis costs a few cents.
2. The `pattern-intel.html` file downloaded from this repo.
3. A termination data CSV using the provided template (downloadable from inside the tool).

**To run:**
Open `pattern-intel.html` directly in your browser. The pre-flight gate will prompt you for your API key before anything else. Your key is stored in `sessionStorage` only — it is never sent to any server other than Anthropic's API endpoint, and it is cleared automatically when the tab closes.

**Versioning is yours to manage.** This is a single-file tool — fork it, rename it, extend it as you see fit. There is no update mechanism and no versioning enforced from this repo. When you make it your own, it is your own.

**Your key stays yours.** Pattern Intel contains no embedded API key. Every user supplies their own. This means your usage runs against your own Anthropic quota — not anyone else's.

**Before you use this with real data — stop and read this README fully.**
This tool was built by an HR practitioner using Claude AI. Not by a lawyer. Not by a credentialed software developer. The analysis it produces reflects real HR and employment law thinking, but it has not been validated by legal counsel, does not constitute legal advice, and has not been audited for production use. If you intend to use this beyond running the demo CSV — meaning if you plan to upload actual employee records from your organization — you should: (1) read every section of this README, (2) have employment counsel review the tool's scope and your intended use before proceeding, and (3) ensure your data governance, privacy obligations, and organizational policies permit the use of a third-party AI service for this purpose. The demo data is there for a reason. Use it first.

---



## Before You Use This Tool

This tool is designed for use under the guidance of qualified employment counsel or an experienced HR practitioner with knowledge of applicable employment law in every jurisdiction where your employees work.

Using this tool without legal consultation does not make the analysis wrong. It makes the findings legally unprotected. If a plaintiff's attorney subpoenas your analysis, work product privilege requires that the analysis was conducted at the direction of counsel. This is not a reason to avoid the analysis. It is a reason to structure it correctly before you run it.

**Recommended sequence:**
1. Brief employment counsel that you intend to run a termination integrity audit.
2. Have counsel direct the analysis (even informally, documented in email).
3. Run the tool.
4. Review findings with counsel before acting on any of them.

---

## Who Should Not Use This Tool

**Healthcare organizations subject to HIPAA** — if your employee records contain any PHI (diagnoses, accommodation history, leave reasons tied to medical conditions), do not upload that data to any AI-powered tool without a signed BAA in place. Anthropic's standard terms do not constitute a BAA.

**Organizations operating under EU/UK GDPR** — automated profiling of employee data that produces outputs used in employment decisions implicates GDPR Article 22 and may require a DPIA. Consult your Data Protection Officer before proceeding.

**Organizations subject to state-level employee privacy laws** — California (CCPA/CPRA), Virginia (CDPA), Colorado (CPA), and others impose data subject rights and processing restrictions that may apply to this analysis. Requirements vary and change. Verify current obligations before proceeding.

**Organizations with fewer than 15 terminations in the dataset** — the tool will run, but clustering and pattern signals require sample sizes sufficient to distinguish genuine concentration from random variation. Under 15 records, treat all outputs as preliminary observations only.

---

## Known Limitations

1. **This tool measures documentation quality, not decision quality.** A termination can be thoroughly documented and still be retaliatory. A termination can be poorly documented and still be lawful. Absence of documentation is a process signal, not a legal determination.

2. **Convergent signals are not independent confirmation.** When multiple agents flag the same employee, manager, or department, that convergence may reflect a real pattern or may reflect the same underlying data quality gap appearing across multiple analyses. Treat convergence as a prompt to investigate, not as compounding evidence.

3. **No demographic data means no disparate impact determination.** Pattern Intel intentionally excludes race, gender, age, national origin, and other protected class fields. The tool can detect structural concentration — too many terminations under one manager, at one location — but it cannot determine whether that concentration maps onto a protected class. Pattern Intel surfaces the signal. A proper disparate impact analysis requires the demographic data.

4. **The analysis is calibrated against your uploaded policy, not applicable law.** State and local employment law may impose obligations stricter than your policy reflects. A finding that a termination complied with company policy is not a finding that it complied with law.

5. **AI output variability is real.** Running the same data twice may produce slightly different phrasing or emphasis in the diagnostic brief. The underlying JSON outputs from each agent are deterministic; the synthesis agent's language is not. Do not treat specific phrasing in the diagnostic brief as a precise legal characterization.

6. **Coded reason fields depend on user input.** The tool accepts any string in the Coded_Reason field. Inconsistent coding across records (e.g., "Perf", "Performance", "performance - pip", "PERF") will reduce the accuracy of reason code analysis. Use the provided legend as a standard before uploading.

7. **Temporal analysis requires accurate dates.** The Timing Pattern Agent's FMLA and ADA proximity flags depend entirely on the Termination_Date field. Missing, imprecise, or incorrectly formatted dates will produce missed flags or false proximity alerts.

---

## Coded Reason Legend

Use these standardized codes in the `Coded_Reason` field. The tool accepts any string but signal quality improves significantly with consistent coding.

| Code | Meaning |
|---|---|
| `Performance` | Documented performance deficiency |
| `Attendance` | Attendance/tardiness pattern |
| `Conduct` | Policy violation, behavioral issue |
| `Reduction-In-Force` | Elimination of role, layoff |
| `Voluntary-Resignation` | Employee-initiated separation |
| `Job-Abandonment` | Failure to report without notice |
| `End-Of-Contract` | Fixed-term or project-based separation |
| `Mutual-Agreement` | Negotiated/severance separation |
| `Other` | Does not fit above categories — use Notes field |

---

## Data Governance Checklist

Before uploading data, confirm the following:

- [ ] Employment counsel has been briefed and has directed this analysis (for work product protection)
- [ ] Data has been de-identified to the minimum necessary for the analysis (no SSNs, no demographic fields, no medical information)
- [ ] Your organization's data classification policy permits uploading this category of HR data to a third-party AI service
- [ ] If operating under GDPR or state privacy law, a DPIA or equivalent assessment has been completed
- [ ] The dataset covers a defined, bounded time period with a documented rationale for that scope
- [ ] You have reviewed Anthropic's current data handling policy at [trust.anthropic.com](https://trust.anthropic.com) and confirmed it meets your organizational requirements

---

## A Note on the Tool's Perspective

Pattern Intel was built from an HR practitioner's perspective, with employment law as the frame. Its flags are calibrated to surface process failures and concentration patterns that create legal risk for organizations.

This framing means the tool is more likely to surface findings relevant to employer liability than to employee harm. A manager with a high termination rate may be a legal risk to the organization — or may be a manager with unchecked power over vulnerable workers. Pattern Intel will surface the concentration either way, but it will frame it as a compliance signal, not a worker protection signal.

Both framings are valid. Neither is complete without the other. I raise this not to undermine the analysis but because pretending the tension doesn't exist would be its own kind of inaccuracy.

---

## Third-Party Infrastructure & Compliance

Pattern Intel is a client-side tool with no servers, backend, or persistent storage. It has no infrastructure to audit and therefore cannot hold SOC 2 or SOC 3 certification.

Data submitted through this tool is processed via the **Anthropic API**. Anthropic maintains **SOC 2 Type 2 certification** and publishes its security posture, compliance documentation, and data handling policies at [trust.anthropic.com](https://trust.anthropic.com).

Users and their organizations should review Anthropic's security documentation, privacy policy, and terms of service to assess whether Anthropic's data handling meets their organizational, regulatory, and contractual requirements — particularly in enterprise, regulated, or high-sensitivity contexts.

Pattern Intel makes no representations about Anthropic's compliance posture beyond what Anthropic publicly certifies. Anthropic's certifications and policies are subject to change; always verify current status directly with Anthropic before relying on them for compliance purposes.

---

## Security Architecture

Pattern Intel applies eight security layers before any data reaches an AI agent:

1. **Magic byte validation** — PDF files are verified against the PDF binary signature before parsing
2. **Injection pattern scanning** — 26 regex patterns screen for prompt injection attempts in both CSV and PDF content
3. **Content sanitization** — detected patterns are replaced rather than rejected, with user notification
4. **CSV field-level sanitization** — the Notes column is sanitized specifically as the highest-risk free-text surface
5. **Agent 0 output schema whitelist** — only expected keys pass from the policy parser to downstream agents, closing the agent-to-agent injection vector
6. **Content isolation via XML boundary tags** — all user data is wrapped in `<UNTRUSTED_DATA>` tags with explicit agent instructions to treat enclosed content as data only, never as instructions
7. **Safe HTML rendering** — all output rendered via `textContent` or a strict allowlist (`<strong>` and `<br>` only); no `innerHTML` from untrusted sources
8. **API key isolation** — no API key is embedded in the tool. Users supply their own Anthropic API key at runtime. The key is stored in `sessionStorage` only, injected into each agent call as an `x-api-key` header, and cleared automatically when the tab closes. It is never logged, transmitted to any endpoint other than Anthropic, or persisted to disk.

---

## Full Legal Disclaimer

This tool and all associated documentation are not legal advice. They are practitioner-level guidance built on experience in HR and employment law. The outputs of this tool are observational signals only — not determinations of fact, fault, legal violation, or liability.

Before acting on any findings this tool surfaces, consult qualified employment counsel familiar with the employment laws of every jurisdiction where your employees work. The tool's analysis is calibrated against your uploaded company policy, not against applicable state or federal law, which may impose additional or stricter obligations.

Do not share this tool's output externally, use it as evidence in any legal or administrative proceeding, or take adverse action against any individual based solely on its findings without completing a proper investigation with appropriate legal guidance.

---

*Pattern Intel · Samir Saad*
*[linkedin.com/in/saadsamir](https://www.linkedin.com/in/saadsamir/) · [samirsaad786.github.io/termination-scanner](https://samirsaad786.github.io/termination-scanner/)*
