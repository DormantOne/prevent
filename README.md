# Evidence-Based Health Plan — Prompt Builder

**A client-side tool that maps a patient's health profile against U.S. screening and prevention guidelines and generates a structured AI prompt for visit preparation.**

Works with: GPT · Claude · Gemini · Copilot · Perplexity · OpenEvidence

---

## Overview

Patients enter basic health data (age, sex, BMI, BP, smoking history, family history, labs). The tool cross-references that profile against current guideline frameworks — USPSTF, ACC/AHA, ADA, KDIGO, ACIP — and produces a prompt that, when submitted to an AI system, returns:

- Screening and prevention topics to discuss with a clinician
- Evidence-based targets (BP, lipids, A1c) individualized to comorbidities
- Recommended bloodwork to consider
- Questions to bring to the visit

**All outputs are framed as discussion topics, never directives. The clinician remains the final authority.**

## Not Medical Advice

This tool does not diagnose, prescribe, or replace clinical judgment. It prepares patients for better conversations.

## Modes

**Simple** — Age + sex → general screening prompt optimized for OpenEvidence.

**Complete** — Full profile input → deeply personalized prompt with prioritized actions, LDCT eligibility assessment, cancer screening checklist, vaccination review, and a prototype modifiable risk score (not validated).

## Output Destinations

| Destination | Use Case |
|---|---|
| **OpenEvidence** | Citation-heavy, guideline-anchored |
| **ChatGPT** | Structured reasoning and prioritization |
| **Claude** | Long-form synthesis |
| **Gemini** | Structured answers with web grounding |
| **Copilot** | Fast web-adjacent summaries |
| **Perplexity** | Source-forward research |

## Companion: Reminder Calendar

Generates `.ics` calendar reminders for eligible screenings based on the patient's profile (colonoscopy, mammogram, PSA discussion, eye exams, labs, wellness visits).

## Technical

- Pure client-side HTML/CSS/JS — single file, no build step
- No server, no database, no tracking, no data transmitted
- All computation in-browser; data leaves only when the user explicitly copies a prompt to an AI service
- Mobile responsive

## On AI Error ("Mistokens")

AI systems operating in clinical contexts will occasionally produce responses that are almost right but subtly wrong — a stale guideline, a misapplied threshold. This project uses the term **mistoken** to describe this error class.

The governance position is straightforward: a tool that surfaces a thousand missed screening conversations and occasionally produces one imprecise suggestion (caught by the clinician in the room) is safer than the alternative, which is silence.

## Governance Model

1. Discussion topics only — never directives
2. Clinician as final authority
3. Full transparency — patient and physician see all outputs
4. Open and auditable prompt structure
5. Iterates as guidelines update

## Roadmap

- [ ] Server-based architecture with direct API integration
- [ ] EHR hooks where feasible
- [ ] Primary care leadership review and governance framework
- [ ] Pilot deployment with outcome measurement

## Running

```bash
git clone https://github.com/[username]/[repo].git
open index.html
```

Or: `https://[username].github.io/[repo]/`

## Files

| File | Description |
|---|---|
| `index.html` | Prompt builder (main application) |
| `the_signal_was_there.html` | Presentation on AI governance in preventive care |

## Disclosure

This is not a commercial venture. I do not expect this to be monetizable. Any proceeds from implementation should go into further development and broader access.

## Contributing

Clinicians, informaticists, and quality improvement professionals: review the screening logic, stress-test against clinical scenarios, identify edge cases, suggest governance language. Open an issue or reach out.

## License

MIT
