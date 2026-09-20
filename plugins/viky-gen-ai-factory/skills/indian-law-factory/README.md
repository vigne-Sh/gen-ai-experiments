# indian-law-factory

A Claude Code skill that explains Indian law: how to read a section, how
to read a case judgment, which law applies by date (BNS/BNSS/BSA vs.
IPC/CrPC/Evidence Act), and where to go for official sources and
Tamil Nadu grievance/legal-aid support.

Part of the [`viky-gen-ai-factory`](../..) plugin in the
[`gen-ai-experiments`](../../../..) marketplace.

## What it does

- Builds a dated timeline from documents you share (notice, FIR, court
  filings) and flags inconsistencies before giving advice.
- Picks the right law by date: offences from 1 July 2024 onward fall
  under BNS/BNSS/BSA; earlier ones under IPC/CrPC/the Evidence Act. Always
  gives both numbers, e.g. IPC 498A → BNS 85/86 — see
  [`REFERENCES.md`](REFERENCES.md) for verified citations behind mappings
  like this one.
- Explains a section's ingredients, punishment, and
  bailable/cognizable/compoundable status, and a case's holding vs.
  obiter and whether it binds.
- Points to official sources (India Code, e-Gazette, Supreme Court/High
  Court sites, eCourts) and Tamil Nadu support channels (CM Helpline,
  TNSLSA legal aid, Women Helpline 181) rather than inventing them.

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
- [`REFERENCES.md`](REFERENCES.md) — the specific section-mapping and
  case-law citations the skill relies on, each checked against a live
  source rather than taken from model memory, with the date checked.
