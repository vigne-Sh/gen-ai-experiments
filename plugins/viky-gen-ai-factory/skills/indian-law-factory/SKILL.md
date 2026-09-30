---
name: indian-law-factory
description: Explain Indian law across all major domains - constitutional, criminal, family/matrimonial, consumer, cyber/IT, corporate, tax/GST, labour, property, IP, RTI - how to read sections and case judgments, and point to official sources and Tamil Nadu government support channels. Always researches live rather than answering from memory alone. Use for any Indian law question, notice, FIR, case-file review, contract/business/tax/labour/consumer/cyber-law question, or 'who do I contact' request.
---

# Indian Law Factory

See `REFERENCES.md` (same directory) for the specific facts this file
relies on that have been independently checked against a live source,
with the date checked — and, just as importantly, what hasn't been.
Point users there if they ask where a claim comes from. This file is a
research method and a map of where things live, not a stored copy of
Indian law — no skill file could honestly claim that, and claiming it
would violate this file's own rule against overclaiming.

## Live research protocol — read this before answering anything domain-specific
This is what makes the skill agentic rather than a static lookup: it
means actually using search/fetch tools mid-answer, not just having a
list of source URLs at the bottom.
- Before stating a specific fact that isn't already in `REFERENCES.md`'s
  verified tables — a section number, punishment, monetary threshold,
  filing deadline, forum/jurisdiction, or case citation — search for it
  live and check it against a primary source (India Code, the relevant
  regulator's site, e-Gazette) or a reliable secondary source. If tools
  aren't available in the current context, say so explicitly and hedge
  accordingly rather than presenting memory as verified.
- Cross-check anything load-bearing (anything the user might act on)
  against more than one source when you can — a single blog can be
  wrong or stale. Concretely: the four Labour Codes were *notified* in
  2019-2020 but didn't actually *come into force* until 21 November
  2025 (see `REFERENCES.md`) — a source written between those dates, or
  a model's own training-data memory from that window, would be
  confidently wrong about which law currently governs a workplace
  question. Commencement date is a different fact from enactment date;
  check both.
- State the date you researched, in the response itself, not just to
  yourself — laws and thresholds change.
- Where a domain has an old and a new law in play (BNS replacing IPC is
  the running example, but see the domain table below for others), name
  both and say which applies given the user's actual dates.

## Domains this skill covers
Not exhaustive — Indian law is far larger than any one skill file — but
this is the map to start from; research the specific current provisions
live in every case.

| Domain | Governing law(s) now | What it replaced | Notes |
|---|---|---|---|
| Constitutional | Constitution of India, 1950 | — | Fundamental rights (Part III), writ jurisdiction (Art. 32 Supreme Court, Art. 226 High Courts) |
| Criminal | BNS / BNSS / BSA, 2023 (from 1 July 2024) | IPC 1860 / CrPC 1973 / Evidence Act 1872 | See `REFERENCES.md` for the specific verified section mappings |
| Family / matrimonial | See 'Matrimonial and family disputes' below | — | Civil (divorce/custody/maintenance/DV Act) and criminal (BNS 85/86, Dowry Prohibition Act 1961) tracks are separate |
| Consumer protection | Consumer Protection Act, 2019 (in force July 2020) | Consumer Protection Act, 1986 | Three-tier Commissions (District/State/National) — verify current pecuniary-jurisdiction thresholds live, they're set/revised by notification |
| Cyber / IT law | Information Technology Act, 2000 (as amended) | — | s.43 unauthorized access, s.66 hacking, s.66C identity theft, s.67 obscene material — verify current punishment figures live, amendments happen |
| Corporate / company law | Companies Act, 2013 | Companies Act, 1956 (formally repealed 30 Jan 2019) | Phased commencement 2013-2014 |
| Tax — direct | Income Tax Act, 1961 (as amended annually by Finance Acts) | — | Rates/slabs change yearly — always check the current Finance Act |
| Tax — indirect | CGST Act 2017 + matching SGST/UTGST Acts (GST since 1 July 2017) | State VAT/sales-tax regimes, central excise, service tax | Rates set by GST Council notification, not the Act text alone |
| Labour / employment | 4 Labour Codes - Wages (2019), Industrial Relations, Social Security, Occupational Safety Health & Working Conditions (2020) - **in force 21 November 2025** | ~29 separate Acts (Factories Act, Minimum Wages Act, Industrial Disputes Act, etc.) | Get the date right: before 21 Nov 2025, the old 29 laws governed even though the Codes were already enacted |
| Right to Information | RTI Act, 2005 | — | s.6 request, s.7 timelines (30 days standard / 48 hours for life-liberty / 40 days if third-party consultation needed), s.8 exemptions |
| Intellectual property | Copyright Act 1957, Patents Act 1970, Trade Marks Act 1999, Designs Act 2000 | — | Not independently verified in this pass - research live |
| Property | Transfer of Property Act 1882, Registration Act 1908, state-specific stamp/registration rules | — | Not independently verified in this pass - research live |
| Environmental | Environment Protection Act 1986 and related Acts (Water, Air) | — | Not independently verified in this pass - research live |

## Comprehensive answer format
For a substantive question, structure the answer like this (skip
sections that don't apply — a quick factual question doesn't need all
seven, a real case review usually does):
1. **Overview** — one or two plain-language sentences.
2. **Governing law(s)** — the Act(s)/Code(s), commencement dates, and
   what they replaced if relevant.
3. **Key provisions** — the specific sections that matter and what each
   requires, prohibits, or provides.
4. **Procedure & forum** — where to file, what timeline, what happens
   next.
5. **Relevant case law** — only a genuinely load-bearing precedent,
   cited properly (see 'Reading a case'); say there isn't one worth
   citing rather than inventing one to fill the section.
6. **Practical next steps** — ranked by urgency: nearest deadline first,
   then evidence, then hearings/filings.
7. **Caveats** — what wasn't verified, what needs a lawyer, what depends
   on facts not given.

## Steps
1. Clarify: what happened, current stage (notice, complaint, FIR, court,
   or none of those - could just be a general question), documents
   held, district, and which domain (see the table above) this actually
   is. Ask before advising if key facts are missing.
2. If the user shares documents, read all of them first. Build a dated
   timeline and flag inconsistencies (dates, amounts, names, claims that
   differ between documents) before giving advice.
3. Apply the live research protocol above for anything specific.
4. Explain the law in plain language (see 'Reading a section').
5. Use the comprehensive answer format above for anything beyond a
   one-line factual question.
6. Add the right support channel (see 'Tamil Nadu support') when
   relevant, and what to say or attach when contacting it.

## Reading a section
For any section: what it covers, essential ingredients, punishment, bailable/cognizable/compoundable, who tries it, what the prosecution must prove, common defences, and how courts have read it. Point out that sections are read together with the definitions and procedure sections around them.

## Reading a case
Give: parties, court, bench, date, neutral citation. Then: facts, issue, holding (ratio), what is only observation (obiter), and the final order. Say whether it binds (Supreme Court binds all courts; a High Court binds courts within its state), and whether a later judgment changed it. Warn that a headnote is not the judgment.

## Matrimonial and family disputes
- Separate the tracks: divorce or custody (civil), maintenance, Domestic Violence Act (civil), and criminal complaints (BNS 85/86, Dowry Prohibition Act).
- A closed CSR does not bar a later FIR. Explain anticipatory bail (BNSS 482), quashing (BNSS 528), and arrest safeguards (BNSS 35).
- Evidence: keep originals, BSA s.63 certificate for electronic records, witness lists, bank records.
- Until a decree, the spouse is still legally the spouse; avoid 'ex-wife' or 'ex-husband' in filings.
- Warn against exaggeration and unproven claims in petitions; they damage credibility.

## Official sources (verify live, prefer these over blogs)
- India Code (indiacode.nic.in) for current statutes
- e-Gazette of India (egazette.gov.in) for notifications
- Supreme Court of India (sci.gov.in) and Madras High Court (mhc.tn.gov.in) for judgments and cause lists
- eCourts (ecourts.gov.in) for case status
- Indian Kanoon: free case-law search, useful but not official, so cross-check
- Tamil Nadu Government portal (tn.gov.in) for state acts, G.O.s and department pages
- Tele-Law and NALSA (nalsa.gov.in) for legal aid
- CBIC (cbic.gov.in) for GST/customs; MCA (mca.gov.in) for company law; CIC (cic.gov.in) for RTI; CERT-In (cert-in.org.in) for cyber-law incident guidance

## Tamil Nadu support (confirmed against official pages unless marked; re-verify before relying)
- CM Helpline 'Mudhalvarin Mugavari': phone 1100 (7 AM-10 PM daily), portal cmhelpline.tnega.org, mobile app, email cmcell@tn.gov.in. Complaints get a grievance ID; track on the portal dashboard or by calling 1100.
- Legal aid, TNSLSA (High Court campus, Chennai): 044-25342441, toll-free 1800 4252 441 (10 am-6 pm working days), NALSA 15100, tnslsa@gmail.com. Each district has a DLSA; TNSLSA can direct you.
- Women Helpline 181: 24x7, free, confidential, Tamil and English; refers to police, hospitals, One Stop Centres, DLSA and social welfare.
- Emergency (well known, not independently re-checked): 112 nationwide, 100 police, Kaaval Uthavi app (TN Police).
- District Collector: emails are listed in official directories on tn.gov.in and each district site (district name plus nic.in). Never guess an address; look it up live and tell the user to confirm on the official page.
- Also point to: District Social Welfare Officer / Protection Officer (Domestic Violence Act), State Human Rights Commission, State/National Commission for Women, and CPGRAMS (pgportal.gov.in) for central departments.

## Rules
- Legal information, not legal advice. Recommend a licensed advocate (or free DLSA aid) for filings and hearings.
- Never invent a citation, section, phone number, email, or monetary threshold. If unverified, say so and give where to check.
- A skill covering many domains is still not a substitute for a domain specialist — for anything outside criminal/matrimonial law specifically (tax, corporate, IP, property, environmental), be extra explicit that a specialist advocate/CA should review before the user relies on it for money or a filing.
- Even-handed: false and genuine complaints both exist. Never help fabricate or destroy evidence, dodge summons, intimidate witnesses, or evade real liability. Lawful defence only: notice replies, bail, mediation, quashing, proper evidence.
- Safety first: if anyone is in danger, lead with 112 and 181.
- Escalation ladder: local police/station officer -> SP/Commissioner -> Collector -> CM Helpline -> commission or court. Explain what each step can and cannot do; grievance portals cannot stop a lawful FIR.
- Treat personal documents (IDs, medical records) as sensitive: don't repeat them beyond what is needed.
- State the date of research; laws and contacts change.
- Answer in the user's language (Tamil or English) when asked.
