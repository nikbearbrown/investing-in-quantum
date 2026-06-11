# Research Notes: Chapter 09 — Sovereign Demand: The Floor That Matters

**Source:** TIKTOC.md chapter entry
**Notes file:** 09-sovereign-demand-the-floor-that-matters_notes.md
**Corresponding chapter:** chapters/09-sovereign-demand-the-floor-that-matters.md (not yet written)
**Generated:** 2026-06-10

---

## Chapter summary (from TIKTOC.md)

**Decision question:** How do I distinguish companies with real government revenue from companies with press releases about government interest?

**Short answer:** Look for contracts with specific deliverables and multi-year terms — not MOUs, partnership announcements, or one-off research grants. The UK ProQure program is the most transparent sovereign procurement structure currently operating; use it as the template.

**Framework — two sovereign risk asymmetries:** (1) Cryptographic risk — Shor's algorithm threatens RSA/ECC; governments cannot afford to be caught unprepared regardless of timeline, and NIST post-quantum standards are already finalized, making this an *active procurement driver today*. (2) Strategic capability risk — governments are buying optionality on a technology they cannot afford to miss ("repeating semiconductor and AI mistakes"), not certainty on one they believe is ready. The investor filter: recurring procurement revenue = demand floor; grants and MOUs = noise.

---

## A. Conceptual foundations

### The demand floor concept

A "demand floor" is a source of revenue that does not depend on the technology being commercially useful yet. Most quantum hardware companies have negligible commercial revenue and burn cash; under a pure-commercial lens many should trade near zero option value. They do not, and the non-obvious reason is that governments are buying the technology for strategic reasons that are *insensitive to near-term commercial readiness*. A government does not need a quantum computer to be profitable to want a sovereign one — it needs it to exist domestically before adversaries have one. That converts a portion of demand from "depends on the product working commercially" to "depends on the geopolitics continuing," which is far more durable on a 5–10 year horizon.

**Common misconception:** "Government quantum money is just subsidy that will dry up." It behaves more like defense procurement — sticky, multi-year, and politically protected — than like a discretionary research grant. But only *some* of it is structured this way; most announced "government interest" is non-binding.

**Worked example:** A company announcing a £5M ProQure Phase 1 contract with milestone-tied payments and a testbed deliverable to the NQCC has a recurring, validated revenue line. A company announcing an "MOU to explore quantum applications" with a national lab has nothing of investment value.

**Source(s):** [UKRI ProQure opportunity](https://www.ukri.org/opportunity/contracts-for-innovation-proqure-scaling-uk-quantum-computing/); [NQCC](https://www.nqcc.ac.uk/about-us/national-quantum-strategy/)

### Cryptographic risk: the "harvest now, decrypt later" driver

Shor's algorithm, run on a sufficiently large fault-tolerant quantum computer, factors large integers efficiently — breaking RSA and elliptic-curve cryptography that secures essentially all current digital infrastructure. The threat is asymmetric in time: adversaries can *record encrypted traffic today* and decrypt it years later when hardware matures ("harvest now, decrypt later"). This makes the risk actionable *now* even though the capable machine is a decade-plus away.

NIST finalized the first three post-quantum cryptography standards in **August 2024** — FIPS 203 (ML-KEM / CRYSTALS-Kyber, key encapsulation), FIPS 204 (ML-DSA / CRYSTALS-Dilithium, signatures), and FIPS 205 (SLH-DSA / SPHINCS+, hash-based signatures). This is a concrete, dated procurement trigger: US federal agencies now have a migration mandate.

**Common misconception:** "Post-quantum crypto is a quantum *investment* thesis." It is mostly defensive IT/software spending (algorithm migration), not quantum *hardware* demand. The chapter should note this is a demand driver for the *sector's strategic salience*, not a revenue line for hardware makers. (TIKTOC's own /m3 explicitly puts "quantum cryptography as investment thesis" out of scope.)

**Source(s):** [NIST PQC announcement, Aug 2024](https://www.nist.gov/news-events/news/2024/08/nist-releases-first-3-finalized-post-quantum-encryption-standards); [Federal Register FIPS 203/204/205](https://www.federalregister.gov/documents/2024/08/14/2024-17956/announcing-issuance-of-federal-information-processing-standards-fips-fips-203-module-lattice-based)

### Strategic capability risk: optionality, not conviction

Governments fund quantum the way they hedge against any technology they cannot afford to be late on. The UK's framing is explicit: avoid "repeating semiconductor and AI mistakes" — i.e., ceding a strategic industry to other nations. The tell that this is *optionality* rather than *belief in imminent payoff*: the planning horizons are conservative (2035), and the programs are structured as multi-phase validation, not crash commercialization. A government that believed quantum arrived in 2027 would not run a four-year prototype-validation program first.

**Common misconception:** "Heavy government funding means the technology is almost ready." The opposite inference is more accurate — the *structure* of the funding (long, staged, validation-first) reveals the government's true timeline expectation, which is long.

**Source(s):** [GOV.UK National Quantum Strategy Missions](https://www.gov.uk/government/publications/national-quantum-strategy/national-quantum-strategy-missions); [Tony Blair Institute, "A New National Purpose"](https://institute.global/insights/tech-and-digitalisation/a-new-national-purpose-a-uk-quantum-strategy-for-sovereignty-and-scale)

### The contract-quality hierarchy (the core investor filter)

Rank government "involvement" by bindingness and recurrence:
1. **Multi-year procurement contract with milestone-tied payments and named deliverables** — real demand floor (e.g., ProQure Phase 1/2).
2. **Recurring procurement labeled as such in earnings** — confirms the floor is company-specific.
3. **One-off research grant** — non-recurring; signals government interest in the *field*, not commercial readiness of the *company*.
4. **MOU / Letter of Intent / "strategic partnership"** — non-binding; near-zero investment value.

**Worked example:** UK ProQure Phase 1 offers up to **£14M** across up to **10 contracts**, with technical milestone verification by the NQCC — that is tier 1. A "partnership to explore quantum chemistry" press release is tier 4.

**Source(s):** [Innovate UK Business Connect — ProQure](https://iuk-business-connect.org.uk/opportunities/contracts-for-innovation-proqure-scaling-uk-quantum-computing/)

---

## B. Domain examples and cases

### Case 1: UK ProQure as the benchmark procurement structure
ProQure ("Procurement of Quantum") is the UK's staged sovereign-procurement program run through Innovate UK's Contracts for Innovation, with the NQCC at Harwell as technical evaluator and milestone verifier. **Verified details:** the Phase 1 competition opened **27 March 2026** and closed **29 May 2026**, offering up to **£14M** to develop, build, and validate integrated quantum hardware/software, with up to **10 contracts** expected. The program is explicitly designed to inform a **future large-scale public procurement beyond 2030, with a budget of up to £1 billion**. It sits under the broader **£2.5 billion National Quantum Strategy** (published March 2023) whose Mission 1 targets UK-based quantum computers running **1 trillion operations by 2035**, with an intermediate milestone of **one million quantum operations by 2028**.
*Source:* [UKRI](https://www.ukri.org/opportunity/contracts-for-innovation-proqure-scaling-uk-quantum-computing/); [The Quantum Insider on Mission 1](https://thequantuminsider.com/2023/11/22/autumn-quantum-uks-autumn-statement-presses-for-qc-capable-of-1-trillion-operations-by-2035/)

### Case 2: NSIA interventions as credibility signals
The UK's National Security and Investment Act 2021 (NSIA) is being used to treat quantum as critical national infrastructure. **Verified:** IonQ's acquisition of **Oxford Ionics** (completed **17 September 2025**, ~**$1.075B**, mostly stock) was cleared under the NSIA *with conditions* — current and future generations of Oxford Ionics' trapped-ion hardware **must be manufactured in the UK**, and its science, engineering, infrastructure, personnel, and manufacturing capacity **must remain in the UK**. This demonstrates government conviction: a state that imposes sovereignty conditions on a quantum acquisition treats the technology as strategic supply-chain infrastructure, not a speculative commercial bet. (TIKTOC also cites an "Oxford Nanoscience / QD Oxford, December 2025" dilution-refrigerator case — see FLAG; verify the exact entity name.)
*Source:* [Slaughter and May Competition & Regulatory Newsletter, 10–23 Sept 2025](https://www.slaughterandmay.com/media/kg1aixpk/competition-regulatory-newsletter-10-23-sept-2025.pdf); [IonQ 8-K filings, FY2025](https://www.sec.gov/Archives/edgar/data/0001824920/000119312525266878/ionq-ex99_1.htm)

### Failure case: mistaking a grant or MOU for a demand floor
The recurring investor error is treating any government association as validation. A one-time research grant funds *exploration* and does not recur; an MOU commits no money. A company whose only "government revenue" is grant income has no floor — when the grant ends, so does the revenue. The discipline: read earnings for *recurring procurement* line items with deliverables, and discount everything labeled "partnership," "MOU," or "selected for a study."

---

## C. Connections and dependencies

**Prerequisites (what the reader must already know):**
- The thesis that quantum's commercial payoff is long-dated (Ch 1, Ch 12) — the floor matters precisely *because* commercial revenue is far off.
- Basic distinction between recurring and non-recurring revenue (assumed investor literacy).

**Unlocks (what this chapter makes possible):**
- Signal 3 of the four-part breakthrough signal (Ch 8) — "sustained sovereign procurement revenue" is operationalized here.
- Position-sizing weight in Ch 11 — a company with a real procurement floor can carry slightly more conviction than one without.

**Adjacent chapter connections:**
- **Chapter 8 (Four-Part Signal):** This chapter defines what Signal 3 looks like and how to verify it.
- **Chapter 10 (NVIDIA):** The same national-security apparatus (CFIUS/NSIA) that creates the demand floor also *blocks* NVIDIA from acquiring hardware companies — the floor and the acquisition barrier are two faces of the same regulatory regime.

---

## D. Current state of the field

**Settled:**
- NIST PQC standards (FIPS 203/204/205) finalized August 2024 — the cryptographic-risk procurement driver is concrete and dated.
- UK National Quantum Strategy (£2.5B, March 2023) and Mission 1 (1 trillion operations by 2035) are published government policy.
- NSIA is actively used to impose sovereignty conditions on quantum M&A (IonQ/Oxford Ionics, Sept 2025, verified).

**Contested or emerging:**
- Whether sovereign demand is large enough to be a *true* floor for individual companies, or merely sector-level support. ProQure Phase 1 (£14M / 10 contracts) is small relative to company cash burn; the floor thesis depends on Phase 2 (post-2030, up to ~£1B) and US analogues materializing.
- US procurement (DOE, DoD, national labs, National Quantum Initiative) is larger in aggregate than the UK's but far less transparent — harder to verify as recurring company revenue.

**Key references:**
1. **NIST, FIPS 203/204/205 (Aug 2024)** — the dated trigger for post-quantum migration; establishes cryptographic risk as a present-day driver.
2. **UK National Quantum Strategy (March 2023) + Quantum Missions (GOV.UK)** — the conservative-timeline planning document that reveals true government expectations.
3. **UKRI / Innovate UK ProQure competition documents (2026)** — the template for transparent, milestone-based sovereign procurement.
4. **NSIA final orders (IonQ/Oxford Ionics, 2025)** — evidence of government treating quantum as critical infrastructure.
5. **US National Quantum Initiative Act (2018) and reauthorization debates** — the US framework; useful contrast in transparency.

**Recent developments (last 3 years):**
- ProQure launched (competition opened March 2026) — first transparent staged sovereign procurement naming specific deliverables.
- NSIA conditions on quantum acquisitions (2025) — sovereignty requirements now standard.
- NIST PQC finalization (2024) — moved cryptographic risk from "future" to "active migration mandate."

---

## E. Teaching considerations

**Where readers get stuck:**
- Conflating *post-quantum cryptography* (defensive software spending) with a *quantum-hardware investment thesis*. Be explicit that PQC explains the sector's strategic salience but is not hardware revenue.
- Assuming all government money is equal. The grant-vs-procurement distinction is the chapter's most important and least intuitive point.

**Analogies that work:**
- **Defense procurement vs. research grant:** a multi-year, milestone-tied contract behaves like a defense program (sticky, protected); a grant behaves like a scholarship (one-time).
- **Insurance premium:** governments paying for quantum optionality are buying insurance against being strategically blindsided — they pay the premium whether or not they expect to "use" the technology soon.

**Exercises that build the skill:**
- Give the reader three real press releases (one ProQure-style contract, one grant, one MOU) and have them rank by investment value and justify. (Bloom: Analyze/Evaluate.)
- Have the reader find one quantum company's latest earnings and classify any "government" revenue as recurring procurement vs. grant. (Bloom: Apply.)

---

## F. Library files relevant to this chapter

- `_lib_science-calling-bullshit-the-art-of-skepticism-in-a-data-driven-world.md` — directly relevant: provides the skeptic's toolkit for distinguishing a substantive claim (binding multi-year contract) from a credibility-borrowing one (MOU, "partnership," "selected for study"). Use its "spotting bullshit" framing to structure the contract-quality hierarchy.

---

## G. Gaps and flags

- **FLAG (date discrepancy):** TIKTOC states ProQure Phase 1 runs "October 2026 – September 2028." Verified sources show the Phase 1 *competition* opened 27 March 2026 and closed 29 May 2026; the delivery/testbed window may begin later in 2026. Reconcile the application dates vs. the contract-performance dates before drafting; do not assert "October 2026" without a primary source for the performance start.
- **FLAG (Phase 2 figure):** TIKTOC cites Phase 2 "up to £75M, post-September 2028." Verified sources describe a *future large-scale procurement beyond 2030 of up to £1 billion* but I did not confirm a specific "£75M Phase 2" figure. Treat the £75M number as unverified pending a primary ProQure Phase 2 document.
- **FLAG (entity name):** TIKTOC's second NSIA case ("Oxford Nanoscience / QD Oxford, December 2025," dilution-refrigerator sovereignty) could not be verified. The likely intended company is **Oxford Instruments NanoScience** (a leading dilution-refrigerator maker); confirm the exact entity, date, and conditions before naming it.
- **FLAG (scope boundary):** Post-quantum cryptography is explicitly out of scope as an investment thesis per TIKTOC /m3. Keep PQC framed as a *strategic-salience driver*, not a hardware revenue line.
- **GAP:** US sovereign procurement (DOE/DoD/national labs) is larger but opaque — I could not source company-specific recurring US procurement revenue lines. Author should check latest 10-Ks/8-Ks of IonQ, Rigetti, D-Wave for itemized government revenue, distinguishing procurement from grants.
- **GAP:** No public data confirms any quantum company *yet* reports "sustained, multi-year sovereign procurement revenue" at the level Signal 3 (Ch 8) requires — consistent with TIKTOC's claim that the signal has not fired. State this as current status, not permanent fact.
