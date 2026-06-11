# Research Notes: Chapter 13 — What to Read, Who to Trust
**Source:** TIKTOC.md chapter entry
**Notes file:** 13-what-to-read-who-to-trust_notes.md
**Corresponding chapter:** chapters/13-what-to-read-who-to-trust.md (not yet written)
**Generated:** 2026-06-10

---
## Chapter summary (from TIKTOC.md)
**Decision question:** When a quantum headline hits, whose interpretation should I trust before I act? **Short answer:** Use a four-tier credibility hierarchy and a simple decision rule. **Framework — four tiers:**
- **Tier 1 (high):** independent academic skeptics with no equity stake — Scott Aaronson (UT Austin; Shtetl-Optimized blog), John Preskill (Caltech; coined "NISQ" and "quantum supremacy"), the Flatiron Institute's Center for Computational Quantum Physics (classical-simulation reality check), NQCC Harwell (UK national lab).
- **Tier 2 (medium):** peer-reviewed PRL / Nature Physics / Science; government national-quantum-strategy documents; independent resource-estimation papers.
- **Tier 3 (low, caution):** vendor roadmaps, ecosystem cloud-access "partner" announcements, financial-analyst notes, "quantum utility" press releases.
- **Tier 4 (red flags):** "Quantum AI" as primary value prop; raw qubit counts with no logical error rate; "beyond classical" without naming the classical method compared; 2D planar superconducting grids claiming volume-law entanglement (physically impossible); claims that don't distinguish physical vs. logical qubits.
**Decision rule:** before acting on quantum news, check whether Aaronson or Preskill commented, and whether Flatiron has a classical-simulation response.

---
## A. Conceptual foundations

### Independence as the credibility axis (not credentials alone)
The tiers sort primarily by *incentive*, then by *evidentiary standard*. A vendor's CSO may be brilliant and still Tier-3 because equity creates a structural reason to frame results favorably. An academic with no stake who *also* has the technical standing to be wrong publicly (Aaronson, Preskill) is Tier-1 precisely because their incentive is reputation-for-accuracy, not share price. The hierarchy is a tool for discounting *motivated* framing, not for dismissing expertise.
**Common misconception:** "The company built the machine, so they understand it best." True about the engineering; false about the *significance claim*, where their incentive is compromised.
**Worked example:** A "we achieved quantum advantage" press release (Tier 3) should not move you until you see whether Flatiron or an independent group can reproduce the task classically (the D-Wave/Flatiron episode is the template).
**Source(s):** chapter framework; calling-bullshit reasoning.

### The decision rule as a cheap, repeatable filter
The operational genius is reducing "should I believe this?" to two lookups: (1) Did a Tier-1 independent (Aaronson/Preskill) comment? (2) Did Flatiron post a classical-simulation response? If a splashy claim survives both, it is worth attention; if either knocks it down, stand down. This is fast, public, and free.
**Common misconception:** that you need to evaluate the physics yourself. You don't — you need to know whose evaluation to read.
**Source(s):** Aaronson blog cadence; Flatiron CCQ output.

### The Tier-4 red flags are *physics* tells, not vibes
Several red flags are specific and checkable. "Logical vs. physical qubit" conflation is the most common inflation. "Beyond classical" with no named classical baseline is unfalsifiable marketing (Ch 6). The "2D planar grid claiming volume-law entanglement" flag points at an *area-law* constraint: a shallow circuit on a 2D nearest-neighbor lattice cannot generate volume-law entanglement, so such a claim is physically suspect on its face.
**Common misconception:** that big qubit counts are progress. A 1,000-physical-qubit chip with no logical error-rate disclosure is *less* informative than a 96-logical-qubit result with below-threshold data (QuEra, Jan 2026).
**Source(s):** Preskill on NISQ/supremacy terminology; area-law literature (Ch 3/6 notes).

---
## B. Domain examples and cases

### Case 1 — Scott Aaronson (Tier 1) (VERIFIED, 2026)
Schlumberger Centennial Chair of CS, **UT Austin**, founding director of its Quantum Information Center; runs **Shtetl-Optimized** (now also on Substack), the field's central public forum. Active through 2026 (commentary on QIP'2026 in Riga, STOC'2026, and ongoing quantum-hardware assessments; received Open Philanthropy funding for an AI-alignment-motivated TCS group). His function for the reader: the highest-signal independent "is this real?" voice. Note he is scrupulous about his own uncertainty (his 2025 posts openly weigh the Kalai possibility) — a feature, not a bug.

### Case 2 — John Preskill (Tier 1) and the vocabulary he gave the field
Caltech (Richard P. Feynman Professor of Theoretical Physics; director of IQIM). **Coined "NISQ" (Noisy Intermediate-Scale Quantum, 2018) and popularized "quantum supremacy."** His framing disciplines the whole debate — "NISQ" is itself the admission that current machines are *not* fault-tolerant. The chapter should use Preskill's own terminology as a Tier-1 filter: if a claim ignores the NISQ/FTQC distinction, downgrade it.

### Case 3 — Flatiron Institute CCQ (Tier 1, the classical reality check) (VERIFIED)
Simons Foundation's **Center for Computational Quantum Physics**, directed by Antoine Georges (co-director Andrew Millis). Its role in this book is the *classical defender*: in **May 2026 (Science)** CCQ + Boston University published a classical algorithm efficiently simulating large-scale quantum-annealing dynamics — the work widely read as overturning/erasing a D-Wave "quantum supremacy" claim. This is the institution the decision rule names: "has Flatiron responded?"

### Case 4 — NQCC Harwell (Tier 1, UK national lab) (VERIFIED)
**National Quantum Computing Centre**, opened on the Harwell Campus (STFC Rutherford Appleton Laboratory) in 2024, ~£93M facility. A government, non-commercial benchmarking/evaluation body — useful as an independent, non-equity source for "does the hardware do what's claimed."

### Failure case — the Tier-3/Tier-4 press release
A "quantum utility" or "quantum AI breakthrough" release with a raw qubit count, no logical error rate, and a "beyond classical" claim naming no classical method. Run the decision rule: no Aaronson/Preskill endorsement + Flatiron silence-or-rebuttal ⇒ ignore. The 2026 D-Wave episode is the canonical worked example.

---
## C. Connections and dependencies
**Prerequisites:** Ch 6 (classical counterattack — why "name the classical baseline" is a hard rule), Ch 8 (the four-part signal — Tier-1 commentary is how you confirm a signal fired), Ch 3 (area law — the physics behind the volume-law red flag).
**Unlocks:** the *meta-skill* for every other chapter — how to adjudicate any future claim.
**Adjacent:** Ch 10 (NVIDIA's own timeline statements = Tier-3 vendor source, discount them), Ch 11/12 (read IonQ/Quantinuum disclosures and roadmaps as Tier-3 inputs needing Tier-1 adjudication).

---
## D. Current state of the field
**Settled:** Aaronson, Preskill, Flatiron CCQ, and NQCC are real, active, independent, and non-equity; the physical-vs-logical-qubit distinction and the "name the classical baseline" demand are mainstream methodological hygiene.
**Contested / emerging:** how much weight to give *fast-moving* below-threshold results vs. skeptics; whether any vendor "advantage" claim of 2024–26 survives classical reproduction (mostly they have not).
**Key references:** scottaaronson.blog (Shtetl-Optimized); Preskill, "Quantum Computing in the NISQ era and beyond," *Quantum* (2018); Flatiron CCQ (simonsfoundation.org) + Quantum Computing Report on the May-2026 Science paper; NQCC (nqcc.ac.uk); Wikipedia "Scott Aaronson" for current role.
**Recent developments (last 3 yrs):** Flatiron classical-annealing-dynamics result (Science, May 2026); Aaronson's 2025–26 quantum-hardware assessments and Kalai commentary; QIP'2026 (Riga); NQCC facility fully operational post-2024 opening.

---
## E. Teaching considerations
**Where readers get stuck:** wanting to evaluate the science themselves, or over-trusting credentialed *company* spokespeople. Re-anchor on *incentive*, not title.
**Analogies that work:** Tier hierarchy as a *recusal rule* — you don't ask the defendant's lawyer whether the defendant is guilty; Flatiron as the *opposing counsel* whose job is to break the claim classically; Aaronson/Preskill as the *expert witnesses with no stake*.
**Exercises:** (1) Take a real 2024–26 quantum press release and tier every claim in it. (2) Run the two-lookup decision rule on a current headline and record the outcome. (3) Find one Tier-4 red flag (logical/physical conflation or unnamed classical baseline) in a vendor's own materials.

---
## F. Library files relevant to this chapter
- `_lib_science-calling-bullshit-the-art-of-skepticism-in-a-data-driven-world.md` — **Strongly relevant (core).** Bergstrom & West's toolkit *is* this chapter's method: spotting unfalsifiable claims ("beyond classical" with no baseline), the "if it sounds too good to be true" heuristic, asking *who benefits* (the incentive axis behind the tiers), and demanding the comparison group (the named classical method). Map their "calling bullshit on big data" moves directly onto the Tier-4 red-flag list and the two-lookup decision rule. This is the chapter's primary library anchor.

---
## G. Gaps and flags
- **FLAG — verify Preskill's exact current title and the NISQ citation year.** Confirm "Richard P. Feynman Professor" and IQIM directorship are current (2026), and cite Preskill 2018 *Quantum* journal paper for "NISQ." "Quantum supremacy" he coined earlier (~2012 talk); state coinage carefully.
- **FLAG — Flatiron "overturned D-Wave" wording.** The Quantum Computing Report headline frames the May-2026 Science paper as overturning a D-Wave supremacy claim; D-Wave contests such classical results (see Ch 6 notes, which flag a *partial*/contested match). Present Flatiron's result as a *strong, peer-reviewed classical response*, and note D-Wave's contestation — do not overstate as total refutation.
- **GAP — Aaronson moved to UT Austin in 2016**, not MIT (one stale search snippet called him an "MIT associate professor" — that is outdated; current affiliation is UT Austin). Use UT Austin.
- **GAP — NQCC's specific evaluation outputs** (benchmarking reports) were not pulled in this pass; if the chapter cites a specific NQCC assessment, fetch it from nqcc.ac.uk first.
- **FLAG — the "2D planar grid / volume-law" red flag** is a strong physics claim; cite the area-law reasoning (Ch 3) rather than asserting it bare, so a technical reader can check it.
