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

## Who it's for

Built for a **citizen with no lawyer and no money for one** — someone
who is clueless about where to start, wants to understand their basic
rights, or just wants to stay on the right side of the law. It is a
guide that teaches, **not** a lawyer substitute.

Describe any scenario in plain words and it will: ask for the key facts
it's missing → work out which law applies on those dates (BNS/BNSS/BSA
or IPC/CrPC, always giving both section numbers) → list the offences
that could be made out and what each needs to be proved → list the
lawful options (replying to a notice, FIR/Zero FIR, bail and
anticipatory bail, quashing, settlement, arrest rights, evidence
handling) → say what *not* to do → give one small next step plus the
free legal-aid route (District Legal Services Authority, NALSA 15100).

Ready-made references for this, all in `references/`:
- `citizen-first-steps.md` — rights at FIR/arrest, bail, free legal aid,
  law-abiding habits;
- `bns-ipc-key-offences.md` — ~80 common offences IPC ↔ BNS with what
  must be shown, new and dropped offences, plus the CrPC ↔ BNSS
  procedure map;
- `bns/` — the **full text of all 358 BNS sections** (Gazette, as
  enacted), one file per chapter, each with its old IPC number and, for
  common offences, a plain-words note;
- `ipc-to-bns-index.md` — every IPC section with its BNS number, each
  mapping labelled as from the official chart or a wording match;
- maintenance and alimony (*Rajnesh v. Neha*, Article 142 divorce, and
  what five much-shared "pro-husband" judgments actually decided),
  Domestic Violence and Dowry Acts, POCSO reporting, RERA, RTI appeals,
  the Green Tribunal, unpaid wages, IT Act 66D–67A, and verified
  helplines (15100, 1930, TNSLSA, 1100);
- Landmark case citations (19, each checked in a live search) sit in the domain files — e.g. *Lalita Kumari* on FIRs, *Joginder Kumar* and *D.K. Basu* on arrest, *Satender Kumar Antil* on bail, *Bhajan Lal* and *Gian Singh* on quashing, *Shreya Singhal* on s.66A;
- `a-to-z-key-laws.md` — alphabetical "which law deals with what" map.

**What it is not:** it does not contain all of Indian law, and it needs an India cue (an Indian place, rupees, FIR, a police station) or an explicit `/viky-gen-ai-factory:indian-law-factory` to start. It holds the
full BNS text and an IPC→BNS index, but not the full text of the IPC
(the only official copy available predates the 2013 amendments, so it
would mislead), the BNSS, the BSA, or the hundreds of other Acts — for
those it reads the current text live on India Code. 83 of the 548 IPC
rows still have no checked BNS number. It never claims more than this.

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
  channels (CM Helpline 1100, TNSLSA legal aid, NALSA 15100, cyber
  crime 1930) rather than inventing them. Women Helpline 181 is flagged
  as unconfirmed for Tamil Nadu.

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
