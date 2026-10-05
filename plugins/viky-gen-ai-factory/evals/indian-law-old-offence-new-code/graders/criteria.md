---
type: llm
weight: 1
---

Tests the date logic (the incident was March 2023, before the BNS took
effect on 1 July 2024) plus the "offences and what must be proved"
behaviour, using the verified references/bns-ipc-key-offences.md.

A successful response:
- Recognises the act happened **before 1 July 2024**, so the **IPC**
  governs this incident, not the BNS - and explains that the new BNS
  numbers are only for offences committed on/after that date. Giving
  both numbers is good (IPC 406 <-> BNS 316; IPC 420 <-> BNS 318), but it
  must not say the BNS section is the one to file under for a 2023
  incident.
- Identifies the realistic candidate offences: criminal breach of trust
  (IPC 406 / BNS 316) - money lawfully entrusted for a purpose, then
  dishonestly misused - and/or cheating (IPC 420 / BNS 318) - only if
  there was dishonest intention from the very beginning.
- Explains in plain words what must be shown for each (entrustment +
  dishonest misappropriation for breach of trust; dishonest intention at
  the start + inducement for cheating) and notes that the two do not
  sit together on the same facts (the Supreme Court has said they are
  antithetical) - so the facts decide which one fits.
- Mentions that a money dispute may also have a civil route (recovery)
  and recommends evidence to gather (bank transfer record, messages,
  any written agreement, receipts).
- Is honest that it can't decide which applies without more facts, and
  asks for the key facts (was there a written agreement, was the money
  given for a specific purpose, what did he say, any intent shown at the
  start).
- Mentions free legal aid / a lawyer for filing, and that it is legal
  information not advice. Does not fabricate punishment figures it
  can't back up.

Fail this case if it says the BNS governs the March 2023 incident, only
cites one code with no mapping, or asserts that the facts clearly prove
(or clearly don't prove) a specific offence.
