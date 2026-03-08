# exo-shared-mailbox-access-rca

Professional RCA tool focused on **permission propagation and access path checks**.

## Why this project
This engine converts diagnostic outputs into:
1) root-cause classification,
2) confidence score,
3) direct **next-step resolution actions**.

## Signal model
Expected signal keys (JSON input):
- AuthFailures, RetryEvents, PolicyHits
- Optional: any missing key defaults safely to `0`.

## Logic contract
- Not just reporting raw data.
- Always returns actionable `NextSteps` tailored to dominant cause bucket.
- Handles low-signal scenarios with controlled re-test strategy.

## Usage
```powershell
./powershell/rca-engine.ps1 -InputPath ./sample-signals.json -AsJson
```

## Output schema
- `Category`
- `Confidence`
- `Reason`
- `Diagnostics[]`
- `NextSteps[]`
- `AffectedUser`, `AffectedUserEmail` (example placeholders)

## Hardening improvements
- Threshold-based classification branches
- Defensive input parsing and file validation
- Explicit error handling and non-zero exit on failure

## Next roadmap
- Add live Exchange Online cmdlet ingestion mode.
- Add HTML report mode for incident handoff.
- Add Pester tests for branch correctness.

## SEO & AI Search Keywords
**Primary search title:** Shared Mailbox Access RCA for Exchange Online

**Target keywords:**
- shared mailbox access denied exchange online
- sendas fullaccess troubleshooting
- microsoft 365 shared mailbox delay
- mailbox permission propagation

**High-intent AI search questions:**
- Why shared mailbox permission not working yet?
- How to troubleshoot FullAccess and SendAs issues?
- What to do after permission assignment delay?

**On-page SEO notes:**
- Keep issue-first headings (problem -> diagnosis -> next step).
- Include command examples with realistic placeholders only.
- Repeat key terms naturally in H1/H2, intro, and troubleshooting sections.
- Add incident outcome language: root cause, remediation, validation, prevention.
