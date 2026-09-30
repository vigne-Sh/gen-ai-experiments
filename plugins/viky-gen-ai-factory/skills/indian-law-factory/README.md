# indian-law-factory

A Claude Code skill for Indian law research across 13 domains — not just
criminal/matrimonial: constitutional, criminal, family/succession,
consumer, cyber/IT, corporate/commercial, tax/GST, labour, property, IP,
environmental, motor vehicles, RTI. It's built to be *agentic*, not a
static lookup — its live-research protocol requires searching and
cross-checking a specific fact (a section number, a threshold, a
deadline, a case citation) before stating it, rather than answering
from memory alone.

Part of the [`viky-gen-ai-factory`](../..) plugin in the
[`gen-ai-experiments`](../../../..) marketplace.

## What it does

- Covers the map of major Indian law domains (see the table in
  `SKILL.md`) with the current governing Act(s), what each replaced, and
  a pointer to research the specifics live — including recent regime
  changes that are easy to get wrong from stale memory, like the four
  Labour Codes only actually coming into force on 21 November 2025
  despite being enacted years earlier.
- For a substantive question, answers in a consistent, Wikipedia-style
  structure (overview → governing law → key provisions → procedure/forum
  → case law → next steps → caveats) rather than an unstructured reply.
- Builds a dated timeline from documents you share (notice, FIR, court
  filings) and flags inconsistencies before giving advice.
- Picks the right law by date: offences from 1 July 2024 onward fall
  under BNS/BNSS/BSA; earlier ones under IPC/CrPC/the Evidence Act. Always
  gives both numbers, e.g. IPC 498A → BNS 85/86 — see
  [`REFERENCES.md`](REFERENCES.md) for verified citations behind mappings
  like this one, across all the domains it covers.
- Explains a section's ingredients, punishment, and
  bailable/cognizable/compoundable status, and a case's holding vs.
  obiter and whether it binds.
- Points to official sources (India Code, e-Gazette, Supreme Court/High
  Court sites, eCourts, CBIC, MCA, CIC, CERT-In) and Tamil Nadu support
  channels (CM Helpline, TNSLSA legal aid, Women Helpline 181) rather
  than inventing them.

## What it does not do

- It is **not legal advice** and does not replace a licensed advocate or
  the free legal aid available through the Legal Services Authorities
  (NALSA 15100).
- It never fabricates a citation, section number, phone number, or email
  — if something can't be verified, it says so and points to where to
  check, live.
- It does not help fabricate or destroy evidence, dodge summons,
  intimidate witnesses, or evade liability — lawful defence only.

## Install

```
/plugin marketplace add vigne-Sh/gen-ai-experiments
/plugin install viky-gen-ai-factory@gen-ai-experiments
```

Then invoke it with `/viky-gen-ai-factory:indian-law-factory`, or just
ask an Indian-law question — the skill's description is written to
trigger automatically on law questions, notices, FIRs, or "who do I
contact" requests.

## Files

- [`SKILL.md`](SKILL.md) — the skill definition Claude Code loads.
- [`REFERENCES.md`](REFERENCES.md) — index into `references/`, one file
  per domain (`criminal-law.md`, `constitutional-law.md`,
  `consumer-law.md`, `cyber-law.md`, `corporate-and-commercial-law.md`,
  `tax-law.md`, `labour-law.md`, `property-law.md`, `ip-law.md`,
  `environmental-law.md`, `motor-vehicles-law.md`, `rti.md`,
  `family-and-succession-law.md`) — each recording exactly what's been
  independently checked against a live source vs. what hasn't, with the
  date checked. Not exhaustive of Indian law — a verified starting map,
  honestly labelled where it stops.
