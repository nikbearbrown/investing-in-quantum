# Tik TOC — Investing in Quantum
*Full command output — compiled from all phase inputs*
*Run: /g1 silent — Practitioner Handbook configuration*

---

## Document Metadata

**Book:** Investing in Quantum: A Skeptic-First Framework for the Most Overhyped and Underspecified Technology Sector of the 2020s
**Series:** Computational Skepticism · Bear Brown & Company
**Author:** Humanitarians AI · ni.brown@neu.edu · Bear Brown & Company
**Version:** 1.0
**Status:** Draft handbook — ready for chapter expansion
**Compiled:** June 2026

---

## 1. BOOK CONCEPT SUMMARY AND THESIS

### /i1 — Book Intake Summary

"This handbook teaches retail and professional investors to evaluate quantum computing investment claims rigorously — distinguishing engineered benchmark theater from genuine scientific breakthrough, identifying the narrow problem classes where quantum advantage is real, and sizing positions appropriately against a timeline that is long, uncertain, and sovereign-underwritten — by providing a set of self-contained diagnostic frameworks that can be consulted in any order, at any stage of the investment process. It succeeds if the reader can open their brokerage app after reading any single chapter and make a more defensible decision than they would have made without it."

**Logline:** Quantum computing is real, the timeline is long, and almost everything you've read about it is wrong. Here is the framework to tell the difference.

**Single biggest unresolved structural question:** Whether the handbook targets pure retail investors (bookmark-position sizing, no options) or also serves professional investors and analysts who need the technical depth of the architecture horse race and dequantization literature. The current draft serves both but may need to stratify its audience more explicitly in the introduction.

---

### /i2 — Book Type and Deployment Specification

**Primary type:** Practitioner handbook — self-contained chapters organized by decision or problem, consulted in any order, used as reference before and after investment decisions.

**Not:** A course textbook (chapters are not sequenced by prerequisite build). Not a field-defining monograph (the argument is made in the introduction; chapters provide tools, not argument). Not a trading manual (no buy/sell signals, no price targets).

**Deployment specification:**

Primary use context: An investor — retail or professional — who has seen quantum computing in their feed, on CNBC, in a portfolio recommendation, or in a company pitch. They want to know whether the claim is real before acting on it. They open the handbook at the chapter that matches their immediate question. They get a framework, a set of filters, and a clear answer about what to watch for.

Secondary use context: Financial analysts, venture investors, and technology journalists who need a rigorous, citable framework for evaluating quantum claims. Corporate strategy teams at companies whose business could be disrupted by quantum simulation (pharma, materials, energy). Policy researchers evaluating sovereign quantum investment programs.

What the handbook is NOT designed for: Day traders (no near-term price catalysts). Quantum physicists (the technical depth is investor-grade, not research-grade). Anyone seeking financial advice (explicitly disclaimed throughout).

How the chapter structure signals book type to a reader: Every chapter opens with a decision question ("Should I buy this quantum stock?" / "Is this press release real?" / "How much should I size this position?") and closes with a decision rule. A reader with five minutes can open any chapter and leave with an actionable framework.

---

### /i3 — Reader Profile and Prerequisite Map

**Primary reader:** A financially literate investor — retail or professional — who has heard that quantum computing is the next big thing, is skeptical of the hype but uncertain about the reality, and wants a framework for thinking about it that does not require a physics PhD. They have watched the AI trade run and are wondering if quantum is next. They know what a P/E ratio is. They do not know what a qubit is.

**Specific person:** A retail investor in their 40s with a technology-heavy portfolio (NVIDIA, Google, AMD) built on a "sell shovels" thesis during the AI boom. They have seen IonQ in their brokerage's "trending" section. They want to know if they should buy it, and if so, how much, and what to watch for.

**Prior knowledge assumed:** Basic investment concepts (market cap, P/E, position sizing, diversification). Familiarity with the AI investment narrative. Some awareness that quantum computing exists. Comfort with the idea that technology timelines are uncertain.

**Prior knowledge NOT assumed:** Physics or quantum mechanics. Computer science complexity theory. Options trading or derivatives. Pharmaceutical or materials science domain knowledge.

**Prior misconceptions (what they think they know that is wrong):**

1. "Quantum computing is the next AI — it will arrive suddenly and transform everything." The timeline is 2030s for narrow advantage, 2035+ for broad transformation, and possibly never for general-purpose advantage.
2. "More qubits = more powerful = better investment." Raw qubit count without logical error rates is meaningless. A 1,000-qubit noisy machine is less powerful for most real problems than a 50-qubit high-fidelity machine.
3. "Quantum will make AI faster." The quantum+LLM thesis is scientifically wrong. Dequantization literature demolished it.
4. "If a major company like Google claims quantum supremacy, it must be real." Every supremacy claim has been classically matched within 12-24 months. The classical counterattack pattern is structural, not accidental.
5. "The bookmark position is trivial." One share is an epistemic strategy, not a financial bet. The psychology of attention-stake ownership is real and deliberate.

**Motivation type:** Primarily financial (don't miss the next big thing / don't lose money on hype). Secondarily intellectual (understand what is actually going on). The handbook honors both: every chapter provides both a framework and a decision rule.

**Prerequisite map:**

| Prerequisite | Safe to assume? | If not: where addressed |
|---|---|---|
| Basic investment concepts | Yes | — |
| AI investment narrative familiarity | Probably | Chapter 1 (The Honest Starting Point) |
| Awareness that quantum computing exists | Probably | Chapter 2 (What Quantum Actually Is) |
| Physics or quantum mechanics | No | Chapter 2 — investor-grade primer only |
| Complexity theory (BQP, BPP) | No | Chapter 3 — defined at first use |
| Pharmaceutical/materials domain knowledge | No | Chapter 5 — explained for investor audience |
| Options trading | No | Excluded — not required |

**Front-loading decision:** Chapter 2 (What Quantum Actually Is) is the only prerequisite chapter. It is short, investor-grade, and explicitly frames quantum mechanics as "what the investor needs to know," not as physics instruction. All subsequent chapters reference it but do not require re-reading it.

---

### /i4 — Central Argument and Field Positioning

**Central thesis:** "This handbook argues that quantum computing is a real, long-duration option on a narrow set of application classes — primarily molecular simulation for drug discovery and materials science — with a sovereign demand floor that prevents sector collapse, a classical counterattack pattern that makes benchmark claims unreliable, and a four-part breakthrough signal that has not yet fired, which means the correct investment posture right now is a small bookmark position built on domain knowledge rather than hype, with precise criteria for when to size up."

**Thesis in decision form:** Small position now. Domain knowledge always. Wait for the four-part signal. Size up when it fires.

**Field positioning:**

This handbook has no direct competitors in the investor-facing literature. The gap it fills: most quantum investment coverage is either vendor marketing dressed as journalism, or academic physics literature inaccessible to investors. The handbook occupies the middle — rigorous enough to cite peer-reviewed literature, accessible enough that a retail investor can apply it chapter by chapter.

vs. financial press quantum coverage (Bloomberg, CNBC, Barron's): Those sources report events. This handbook provides frameworks for evaluating events. A Bloomberg article about IonQ's revenue tells you what happened. Chapter 7 of this handbook tells you whether it matters.

vs. academic quantum computing literature (Preskill, Aaronson, Flatiron): That literature is primary source material for the frameworks in this handbook. It is not written for investors. This handbook translates it.

vs. general technology investment books (Christensen, disruptive innovation literature): Those books provide frameworks for technology adoption curves. This handbook provides frameworks for evaluating whether the technology works at all — a prior question that disruptive innovation frameworks skip.

**The positioning statement:** "For investors who want to know whether quantum computing is real before deciding how much to own, *Investing in Quantum* is the practitioner handbook that translates peer-reviewed physics into investment decision frameworks — unlike financial press coverage, which reports claims without evaluating them, and unlike academic literature, which evaluates claims without translating them."

---

## 2. CHAPTER ARCHITECTURE

### /c2 — Chapter Anatomy Template

All chapters follow this structure:

1. **Decision question** — the specific investor question this chapter answers, stated in the first paragraph
2. **The short answer** — one to three sentences. The reader who needs only the conclusion gets it immediately.
3. **Why this matters** — the investment consequence of getting this wrong
4. **The framework** — the analytical tool, filter, or decision rule, explained with enough mechanism that the reader can apply it independently
5. **What it looks like in practice** — one concrete example applying the framework to a real company, claim, or event
6. **What to watch for** — specific, observable signals that change the answer
7. **What to ignore** — specific types of claims, metrics, or coverage that do not change the answer
8. **The decision rule** — one or two sentences. What to do, stated plainly.
9. **Further reading** — three sources: one accessible (journalist or blogger), one independent academic, one primary source. Each with a one-sentence annotation.

**Handbook anatomy rule:** Every chapter is self-contained. A reader who opens Chapter 6 without having read Chapters 1–5 must be able to use the framework. Cross-references to other chapters are permitted and encouraged but never load-bearing.

**Length:** 2,000–4,000 words per chapter. Long enough to be rigorous. Short enough to be read on a flight.

---

### /c1 — Chapter-by-Chapter Documentation

---

**CHAPTER 1 — The Honest Starting Point**

*When to consult this chapter:* You have just heard about quantum computing as an investment and want to know if it is real before going further.

Keyword audit: PASS — "quantum computing investment," "quantum stocks," "quantum hype" should appear in the chapter body.

One-line: Establishes the investment thesis in full — real technology, long timeline, narrow application classes, sovereign demand floor, small position now.

Decision question: Is quantum computing a real investment opportunity or pure hype?

The short answer: Both, simultaneously, for different reasons and on different timelines. The technology is real. The near-term commercial narrative is mostly wrong. The correct response is a small, knowledge-building position — not zero, not large.

Framework: The three-layer test. Layer 1 — Is the underlying physics real? (Yes, provably.) Layer 2 — Does the physics translate to commercial advantage on a relevant timeline? (Narrow and long.) Layer 3 — Is the stock pricing in reality or narrative? (Mostly narrative, which creates both risk and eventual opportunity.)

What to watch for: NVIDIA minority investment expansion. Sovereign procurement contracts translating to recurring revenue. Architecture convergence signals (one modality pulling ahead clearly).

What to ignore: Raw qubit count announcements. "Quantum supremacy" claims without Flatiron verification. Vendor roadmaps predicting commercial advantage by 2029.

Decision rule: Start a bookmark position in the strongest hardware names. Build domain knowledge. Do not size up until the four-part breakthrough signal fires (Chapter 8).

Contributor notes: This chapter is the entry point for readers who arrive from a news article or a brokerage recommendation. It must not assume any prior knowledge of quantum computing. The three-layer test should be applicable without reading any subsequent chapter.

---

**CHAPTER 2 — What Quantum Actually Is (And Isn't)**

*When to consult this chapter:* You keep seeing the words "qubit," "superposition," and "entanglement" and want to know what they mean for an investor — not a physicist.

Keyword audit: PASS — "qubit," "quantum superposition," "quantum entanglement," "BQP" should appear in the chapter body.

One-line: Investor-grade quantum mechanics primer — enough to evaluate claims, not enough to build a quantum computer.

Decision question: What do I actually need to understand about quantum physics to invest intelligently in this sector?

The short answer: Three concepts — superposition (qubits exist in multiple states until measured), entanglement (qubits can be correlated in ways classical bits cannot), and decoherence (the environment destroys quantum states, which is why error correction is hard). Everything else is detail.

Framework: The investor's quantum vocabulary. Qubit vs. logical qubit (the gap between them is the entire fault-tolerance problem). Physical error rate vs. logical error rate (the number that actually matters). BQP vs. BPP (the complexity theory that explains why quantum advantage is problem-specific, not general). Coherence time (how long a qubit stays quantum before the environment kills it).

What to watch for: Logical error rates improving toward 10^-6 or below. Coherence times extending into milliseconds across full processor arrays. Gate fidelity above 99.99% on multi-qubit systems at scale.

What to ignore: Physical qubit counts without logical error rates. "World record" announcements without specifying what was measured and by whom. Comparisons to classical computers without naming the specific problem and the specific classical baseline.

Decision rule: Learn these six terms. Apply them as filters to every quantum press release. If a claim cannot be stated in these terms, it is probably marketing.

Contributor notes: This chapter must be written for a reader who took high school physics twenty years ago. No equations. The investor vocabulary table should be a visual sidebar — six terms, plain language definitions, investment relevance of each.

---

**CHAPTER 3 — The Big Compute, Small Data Filter**

*When to consult this chapter:* A quantum company claims their technology will revolutionize [insert application]. You want to know if the claim passes basic scrutiny before you look at the financials.

Keyword audit: PASS — "quantum advantage," "quantum speedup," "state preparation," "I/O bottleneck" should appear in the chapter body.

One-line: The single most useful heuristic for evaluating quantum application claims — applied in three questions.

Decision question: How do I know if a quantum company's target application is real or invented?

The short answer: Apply the big compute, small data filter. If the problem cannot be specified compactly, requires exponential computation to solve, and returns a small classical answer — it might be a real quantum application. If it requires loading large datasets, it almost certainly is not.

Framework: Three questions for any quantum application claim. (1) Can the problem instance be described in a short specification — a handful of parameters, not a large dataset? (2) Does solving it require exploring an exponentially large computational space? (3) Is the useful output a small classical result — an energy, a decision, a binding affinity — rather than a large classical object? Problems that pass all three: molecular simulation, integer factoring, quantum phase estimation for chemistry. Problems that fail: LLM training, database search, supply chain optimization, financial time-series analysis.

What to watch for: Application claims that name specific problem classes (transition metal catalysis, nitrogen fixation, battery cathode simulation) rather than broad sectors ("quantum will transform pharma"). Computational chemistry benchmarks against DFT baselines on specific molecules.

What to ignore: Any quantum application claim involving large datasets, recommendation systems, logistics optimization, or "AI acceleration" — these fail the filter structurally.

Decision rule: Before reading a quantum company's investor materials, run their target application through the three-question filter. If it fails, the application thesis is probably wrong regardless of the hardware quality.

Contributor notes: The filter should be illustrated with a comparison table — four applications that pass vs. four that fail, with the specific filter question that kills each failure. Visual presentation strongly recommended.

---

**CHAPTER 4 — Why the Quantum + LLM Thesis Is Wrong**

*When to consult this chapter:* You have heard that quantum computing will make AI faster and are wondering whether quantum AI stocks deserve a premium for this reason.

Keyword audit: PASS — "quantum machine learning," "dequantization," "barren plateau," "QRAM," "transformer training" should appear in the chapter body.

One-line: The investment thesis that quantum will accelerate LLM training and inference is scientifically wrong, not just premature.

Decision question: Should I pay a premium for quantum companies that claim they will accelerate AI?

The short answer: No. The quantum+LLM thesis has been systematically dismantled by the dequantization literature. This is not a timing problem — the technology is not "almost there." It is a structural incompatibility between what quantum hardware does well and what LLM training requires.

Framework: Three reasons the thesis fails. (1) Dequantization — the speedups quantum ML algorithms claimed depended on unrealistic data-loading assumptions (QRAM). When classical algorithms were given comparable access, the advantage disappeared. Ewin Tang's 2018 result cascaded through eight major QML speedup claims. (2) Dense matrix multiplication — LLM training is dominated by dense matrix operations with classical input and classical output. No quantum algorithm solves this problem end-to-end. (3) Barren plateaus — variational quantum circuits cannot be trained at scale because gradient magnitudes concentrate exponentially near zero as qubit counts grow. The cure (restricting the model) eliminates the quantum advantage. It is a trap with no exit.

What to watch for: Quantum companies pivoting away from "quantum AI" toward quantum chemistry or materials simulation — a sign they understand their own hardware's constraints.

What to ignore: Any press release claiming quantum will "accelerate AI," "speed up LLMs," or "transform foundation model training." These claims are wrong. The company either does not understand the literature or is marketing to retail investors who do not.

Decision rule: Apply a discount to any quantum company whose primary revenue narrative involves LLM acceleration. The thesis is wrong and the company knows it or should. Neither is a good sign.

Contributor notes: The Ewin Tang story is the most compelling narrative hook for this chapter — an 18-year-old dismantling what the field considered proven. Lead with it. The barren plateau section needs a visual showing gradient variance vs. qubit count — the exponential collapse is the intuition pump.

---

**CHAPTER 5 — The Legitimate Killer App: Molecular Simulation**

*When to consult this chapter:* You want to understand why anyone serious believes quantum computing will eventually matter economically.

Keyword audit: PASS — "molecular simulation," "density functional theory," "DFT," "quantum chemistry," "drug discovery," "FeMoco," "transition metal" should appear in the chapter body.

One-line: The credible long-term quantum application — and why it is credible in a way no other application currently is.

Decision question: What will quantum computing actually be useful for, and when?

The short answer: Molecular simulation for drug discovery and materials science. The object being simulated is itself quantum mechanical, which means quantum computers are not fighting the problem structure — they are representing it in its native language. The timeline is 2030s for early demonstrations, 2035+ for commercial deployment.

Framework: Why classical methods fail for the hard cases. DFT (Density Functional Theory) — efficient but systematically wrong for strongly correlated electron systems, transition metals, and partially filled d- or f-orbitals. CCSD(T) — more accurate but scales as O(M^7), restricting chemical accuracy to small molecules. Molecular dynamics — cannot model chemical reactions or electronic transitions at all. The systems where classical methods fail — transition metal catalysts, FeMoco, battery cathode materials, strongly correlated oxides — are precisely the systems of highest economic value. One synthetic catalyst replicating FeMoco chemistry could disrupt the Haber-Bosch process that consumes 1-2% of global energy.

The counterfactual drug design thesis: Classical ML drug discovery is interpolative — constrained by what has been synthesized and tested before. Quantum simulation acts as an unbiased physical oracle, evaluating molecules outside the classical training distribution. The closed loop: classical generative models propose candidates; quantum simulation accurately evaluates the electron dynamics of candidates classical methods approximate poorly; accurate evaluations guide generative models into genuinely novel chemical space.

What to watch for: QPE (Quantum Phase Estimation) results on transition metal complexes with active spaces above 20 spatial orbitals, achieving chemical accuracy within 1 kcal/mol. Pharma company partnerships with quantum hardware providers structured around specific molecule classes (not general "quantum AI" agreements). UK ProQure procurement contracts naming specific molecular simulation benchmarks.

What to ignore: Quantum chemistry demonstrations on H2, LiH, or BeH2 — these are textbook molecules that classical methods handle trivially. They are proof-of-concept, not proof-of-advantage.

Decision rule: Molecular simulation is the right lens for evaluating quantum's long-term commercial value. Any quantum company with a credible molecular simulation roadmap, fault-tolerant hardware progress, and pharma or materials partnerships deserves closer attention than one making broad sector claims.

Contributor notes: The FeMoco case needs to be explained for an investor audience that has never heard of nitrogen fixation. The Haber-Bosch energy consumption fact (1-2% of global energy) is the economic hook. The counterfactual drug design section benefits from a simple diagram: classical ML confined to training distribution vs. quantum-oracle-expanded design space.

---

**CHAPTER 6 — The Classical Counterattack Pattern**

*When to consult this chapter:* A quantum company just announced a breakthrough. You want to know if it is real before the stock moves.

Keyword audit: PASS — "quantum supremacy," "classical counterattack," "tensor network," "Flatiron Institute," "random circuit sampling" should appear in the chapter body.

One-line: Every major quantum advantage claim has been classically matched within 12-24 months. This is structural, not accidental. Here is how to use it.

Decision question: How do I evaluate a quantum "breakthrough" announcement before acting on it?

The short answer: Wait 12-24 months. Apply the Flatiron test. If the Center for Computational Quantum Physics at the Flatiron Institute has not attempted to match it classically, the claim is unverified. If they have tried and failed, it might be real.

Framework: The counterattack timeline. Google 2019 "10,000 years" → matched in 17 minutes by 2025-2026. IBM 2023 "beyond classical tensor networks" → matched on a laptop within weeks (confinement phenomenon). D-Wave 2025 "1 million years on Frontier" → matched by Flatiron in May 2026 using belief-propagation tensor networks. The structural reason: physical quantum hardware on 2D grids and local 3D lattices is governed by the area law of entanglement entropy. Classical tensor networks are mathematically designed to exploit exactly this structure. The classical response is not clever accident — it is structural inevitability for most current hardware configurations.

What a counterattack-resistant result would look like: A problem of clear economic relevance (not an engineered benchmark). Comparison against best available classical methods (not brute-force baselines). Volume-law entanglement on non-planar, high-connectivity graphs (possible on trapped ion and neutral atom but not superconducting planar grids). Classical verification attempt by Flatiron or equivalent, failed, documented.

What to watch for: Quantum results on transition metal active spaces where Flatiron's classical response takes longer than 12 months. Results on non-planar graph topologies that defeat tensor network compression. Independent academic replication of results without vendor involvement.

What to ignore: "Beyond classical" claims without naming the specific classical methods compared. Claims from superconducting planar grid hardware claiming volume-law entanglement (physically impossible). Any benchmark where the problem was designed for the quantum hardware rather than the hardware tested against a pre-existing problem.

Decision rule: Do not trade on a quantum breakthrough announcement. Wait for the Flatiron response. If they cannot match it within 18 months, revisit the position sizing.

Contributor notes: The three-row comparison table (Google / IBM / D-Wave — claim, timeline, classical response, what it proved) is the anchor visual for this chapter. The structural reason (area law) needs one clear intuitive explanation — the pond metaphor (local hardware, local entanglement, local classical simulation) works for an investor audience.

---

**CHAPTER 7 — The Architecture Horse Race**

*When to consult this chapter:* You are trying to decide which quantum hardware company to own and want to understand the technical differences between them.

Keyword audit: PASS — "superconducting qubits," "trapped ion," "neutral atom," "topological qubit," "photonic quantum computing," "gate fidelity," "coherence time" should appear in the chapter body.

One-line: Five architectures, one winner eventually — here is the current state, the honest ranking, and what convergence looks like.

Decision question: Which quantum hardware architecture should I bet on?

The short answer: Superconducting leads on near-term fault tolerance progress. Trapped ion leads on gate fidelity. Neutral atoms are the fastest-improving challenger. Topological is scientifically unresolved. Photonic is long-duration. Nobody has won. The correct response is either diversification across architectures or waiting for convergence signals.

Framework: Architecture comparison on the five metrics that matter for fault tolerance. Physical error rate (lower is better — trapped ion leads). Coherence time (longer is better — trapped ion leads). Gate speed (faster is better — superconducting leads). Qubit connectivity (more flexible is better — neutral atom and trapped ion lead). qLDPC code compatibility (enables lower physical-to-logical qubit overhead — neutral atom leads, superconducting cannot do it on planar grids).

Current honest ranking for near-term fault tolerance path: Superconducting first (most mature, deepest error correction progress, Google Willow below-threshold memory). Neutral atoms most credible fast-improving challenger (QuEra 96 logical qubits from 448 physical atoms, January 2026). Trapped ion fidelity leader with scaling drag (IonQ 99.99% two-qubit fidelity, but millisecond gates vs. nanosecond superconducting). Photonics long-duration systems bet. Topological scientifically unresolved.

Microsoft topological honest assessment: Two retractions (2021-2022). 2025 Majorana hardware shows stable Z-loop parity (12.4ms lifetime) but X-loop parity degrades in microseconds at 84% fidelity. A full high-fidelity logical topological qubit has not been demonstrated to independent expert satisfaction. High upside if the physics works. Not investable on current evidence.

Architecture convergence signal: Not one modality winning. Heterogeneous architecture where superconducting or photonic handles high-speed local computation and trapped ion or neutral atom serves as high-fidelity quantum memory, connected by quantum networking protocols. Watch for standardized quantum interconnect protocols and optical-to-microwave transducers.

What to watch for: IonQ silicon-integrated trap progress (Oxford Ionics acquisition — electronic control replacing laser beams, the scaling path for trapped ion). QuEra logical qubit demonstrations scaling above 100 logical qubits with below-threshold error rates. Any architecture demonstrating volume-law entanglement on non-planar graphs at scale.

What to ignore: Press-release qubit counts. "World's largest quantum computer" announcements without specifying logical qubits and logical error rates. Vendor roadmap comparisons between architectures (every vendor ranks their own architecture first).

Decision rule: Own the architecture leaders, not a single architecture bet. IonQ (trapped ion), Quantinuum (trapped ion), QuEra (neutral atom) for pure-play exposure. IBM and Google for architecture-agnostic exposure through existing semiconductor positions. Avoid single-architecture concentration until convergence signals fire.

Contributor notes: The five-architecture comparison table is the anchor visual — rows are architectures, columns are the five metrics, cells use a simple scoring system (leads / competitive / lags / unresolved). The Microsoft topological honest assessment is politically sensitive but necessary. Do not soften it.

---

**CHAPTER 8 — The Four-Part Breakthrough Signal**

*When to consult this chapter:* You have a bookmark position and want to know when to size up.

Keyword audit: PASS — "fault-tolerant quantum computing," "quantum error correction," "chemical accuracy," "E-value," "sovereign procurement revenue," "logical qubit" should appear in the chapter body.

One-line: The specific, observable, four-part signal that changes the investment thesis from bookmark to meaningful position.

Decision question: What would make me size up my quantum position?

The short answer: All four of the following must fire simultaneously — scientific breakthrough signal, Flatiron verification, sustained sovereign procurement revenue, and NVIDIA acquisition signal. None have fired yet. The bookmark position is the correct size until they do.

Framework: The four signals in detail.

Signal 1 — Scientific breakthrough: QPE (Quantum Phase Estimation) on a transition metal complex with active space greater than 20 spatial orbitals, achieving ground-state energy prediction within 1 kcal/mol chemical accuracy, on a publicly documented instance with transparent methodology. Not H2 or LiH — those are textbook molecules. A real transition metal complex relevant to drug discovery or materials science.

Signal 2 — Flatiron verification: The result survives independent classical counterattack from the Flatiron Institute's Center for Computational Quantum Physics for 12-24 months without being neutralized. This is non-negotiable. Every previous "beyond classical" claim has been matched. The 12-24 month window is the minimum patience required.

Signal 3 — Sustained sovereign procurement revenue: At least one company demonstrates recurring, multi-year revenue from sovereign procurement programs (UK ProQure contracts, US Department of Energy or Defense agency deployments, national lab partnerships) rather than one-off grants. This confirms the demand floor is company-specific, not sector-wide.

Signal 4 — NVIDIA acquisition signal: A material acquisition (not minority venture investment) of a quantum hardware company by NVIDIA or another major classical compute incumbent. This signal means the regulatory perimeter cleared, the technology matured, and the most technically sophisticated hardware company in the world shifted from hedging to owning.

What to watch for between now and signal: NVIDIA NVentures investment expansion (they have invested in QuEra, Quantinuum, PsiQuantum — watch for deeper stakes or additional modalities). UK ProQure Phase 2 contract awards (post-September 2028 — the first scale-up from prototype). Flatiron response time to D-Wave May 2026 result (still being evaluated at time of writing — a 24-month failure to match would be significant).

What to ignore: Any single signal firing without the others. A scientific breakthrough without Flatiron verification is an unverified claim. Sovereign procurement without scientific breakthrough is government research spending, not commercial validation. NVIDIA acquisition without scientific breakthrough would be surprising and worth investigating — but it would require its own analysis.

Decision rule: Current position: bookmark. Signal firing condition: all four simultaneously. Intermediate condition: Signals 1+2 fire without 3+4 → increase position modestly, maintain watchlist intensity. Signals 3+4 fire without 1+2 → interesting but probably premature; do not size up.

Contributor notes: The four-signal framework is the book's primary decision tool. It should be presented as a visual checklist — four rows, each with the signal name, current status (not fired), what firing looks like, and what changes in the investment thesis when it fires. This visual should appear in Chapter 1 as a preview and in Chapter 8 as the full treatment.

---

**CHAPTER 9 — Sovereign Demand: The Floor That Matters**

*When to consult this chapter:* You are trying to understand why quantum companies have not gone to zero despite having no commercial revenue.

Keyword audit: PASS — "sovereign quantum investment," "UK National Quantum Strategy," "ProQure," "NSIA," "national security," "quantum cryptography" should appear in the chapter body.

One-line: Governments are not funding quantum because they believe the vendor roadmaps — they are funding it because they cannot afford to be unprepared. This creates a real demand floor for specific companies.

Decision question: How do I distinguish companies with real government revenue from companies with press releases about government interest?

The short answer: Look for contracts with specific deliverables and multi-year terms, not MOUs, partnerships announcements, or research grants. The UK ProQure program is the most transparent sovereign procurement structure currently operating. Use it as the template.

Framework: Two sovereign risk asymmetries. (1) The cryptographic risk — Shor's algorithm breaks RSA encryption. Governments cannot afford to be caught unprepared regardless of timeline uncertainty. NIST post-quantum cryptography standards are already finalized. This is not a future risk — it is an active procurement driver today. (2) The strategic capability risk — the UK parliamentary quantum report explicitly warns of "repeating semiconductor and AI mistakes." Governments are buying optionality on a technology they cannot afford to miss, not certainty on a technology they believe is ready.

UK ProQure as the benchmark: Phase 1 (up to £14M, October 2026 – September 2028) funds 10 hardware/software contracts and delivers operational testbeds to the NQCC at Harwell. Phase 2 (up to £75M, post-September 2028) scales operational systems. Quantum Mission 1 targets a general-purpose quantum computer capable of one trillion logical operations by 2035. These are not optimistic commercial timelines — they are conservative government planning horizons. A government that thought this was arriving in 2027 would not be running a four-year prototype validation program.

NSIA interventions as credibility signals: IonQ/Oxford Ionics (September 2025) — allowed only with conditions: hardware hosted in UK for independent assessment, all IP and manufacturing capacity domestic. Oxford Nanoscience/QD Oxford (December 2025) — dilution refrigerator production and servicing must remain UK-sovereign. This is not a government treating quantum as interesting commercial technology. It is a government treating it as critical national supply chain infrastructure.

What to watch for: ProQure Phase 1 contract awards (October 2026 onwards — names the specific companies embedded in UK sovereign demand). US Department of Energy quantum computing program contract awards (less transparent than UK but larger in aggregate). Multi-year recurring revenue lines in quantum company earnings reports, specifically labeled as government procurement rather than research grants.

What to ignore: MOUs with government agencies. Letters of intent. "Strategic partnerships" without contract values and deliverable milestones. Research grants (these are one-time, non-recurring, and do not indicate the government believes the technology is commercially ready).

Decision rule: A quantum company with Phase 1 ProQure contract revenue or equivalent US/EU sovereign procurement has a real demand floor. Weight it in position sizing. A company with only commercial pipeline promises has no floor.

Contributor notes: The ProQure timeline table is the anchor visual. The NSIA intervention cases need to be presented as evidence of government conviction, not just regulatory activity. The distinction between research grants (one-time) and procurement contracts (recurring) is the key investor filter in this chapter.

---

**CHAPTER 10 — NVIDIA's Position: The Sophisticated Hedge**

*When to consult this chapter:* You are wondering whether to own quantum directly or just own NVIDIA and let them figure it out.

Keyword audit: PASS — "CUDA-Q," "NVentures," "NVIDIA quantum strategy," "quantum acquisition," "CFIUS," "ecosystem integration" should appear in the chapter body.

One-line: NVIDIA is not betting on quantum. NVIDIA is becoming the indispensable layer regardless of which quantum architecture wins — and they cannot acquire hardware companies even if they wanted to.

Decision question: Does NVIDIA's quantum positioning reduce or increase my incentive to own pure-play quantum stocks?

The short answer: NVIDIA's positioning is complementary, not substitutive. They are building the orchestration layer around quantum hardware. They cannot acquire hardware companies due to CFIUS and NSIA restrictions. Owning NVIDIA gives you exposure to the quantum software and hybrid workflow layer. Owning IonQ or Quantinuum gives you exposure to the hardware layer. They are different bets.

Framework: NVIDIA's three-part quantum strategy. (1) CUDA-Q — open, QPU-agnostic hybrid programming platform integrating quantum processing units with classical GPU and CPU accelerators. Architecture-neutral by design — the same move NVIDIA made with CUDA in classical AI. (2) NVentures minority investments — QuEra (neutral atom), Quantinuum (trapped ion), PsiQuantum (photonic) as of early 2025. Deliberately spanning all three leading hardware modalities. Not betting on a winner; buying exposure to all of them. (3) "Ising" AI model family (2026) — uses deep learning to accelerate QPU calibration and real-time error syndrome decoding. NVIDIA inserting itself into the hardware operational loop.

The acquisition barrier: Any NVIDIA acquisition of a major quantum hardware company would trigger CFIUS review in the US and NSIA review in the UK. Quantum hardware is classified as critical dual-use national infrastructure. The same national security apparatus that protects quantum companies from foreign acquisition protects them from NVIDIA. Ecosystem integration is therefore not just NVIDIA's strategic preference — it is currently their only legally viable strategy.

NVIDIA acquisition as signal: If NVIDIA ever makes a material acquisition of a quantum hardware company (not a minority stake), the regulatory environment must have cleared and the technology must have matured enough to justify ownership risk. That would be a significant "smart money moved" signal worth treating as the fourth breakthrough signal.

Jensen Huang's timeline: Publicly stated "15-30 years" for commercially meaningful quantum as recently as 2024, softening to a shorter estimate in 2025. The softening coincided with NVentures entering the sector. The sequence — public skepticism, then private investment — is consistent with a company that moved from observation to positioning as the technology crossed a maturity threshold. Watch the gap between what Huang says publicly and what NVentures does privately.

What to watch for: NVIDIA expanding NVentures quantum stakes from minority to majority. CUDA-Q adoption metrics (how many quantum hardware providers have integrated). NVIDIA quantum-related revenue lines appearing in earnings reports.

What to ignore: NVIDIA's public timeline statements (strategically calibrated). Analyst notes predicting NVIDIA will "dominate quantum" the same way they dominated AI (the acquisition path is blocked; the analogy breaks there).

Decision rule: Own NVIDIA for the orchestration layer. Own IonQ/Quantinuum/QuEra for the hardware layer. These are different bets on different parts of the quantum value chain. NVIDIA does not substitute for pure-play quantum exposure; it complements it.

Contributor notes: The Jensen Huang timeline softening paired with NVentures investment activity is the most interesting narrative thread in this chapter. The regulatory barrier (CFIUS + NSIA) is the non-obvious insight — most retail investors assume NVIDIA could just buy IonQ if they wanted to. The chapter should make clear that they cannot.

---

**CHAPTER 11 — The Bookmark Position: Deliberate Small Exposure**

*When to consult this chapter:* You are ready to buy something and want to know what, how much, and why.

Keyword audit: PASS — "bookmark position," "attention stake," "IonQ," "Quantinuum," "QuEra," "position sizing," "confirmation bias" should appear in the chapter body.

One-line: One share of IonQ is not a financial bet. It is an epistemic strategy. Here is why that distinction matters and how to implement it.

Decision question: What should I own right now, how much, and why?

The short answer: A minimal position — one to ten shares — in one or more of IonQ, Quantinuum (when public), or QuEra (when public), plus passive exposure through existing IBM and Google positions. Small enough that a 50% decline does not hurt. Large enough that you pay attention.

Framework: The attention-stake psychology. The purpose of the bookmark position is not return — it is attention quality. One share changes how you read earnings calls, research papers, and conference announcements. Passive watching is lazy watching. Even minimal skin in the game activates domain knowledge acquisition continuously without requiring scheduled "quantum research time." The confirmation bias constraint: the position must be small enough that a 50% decline does not generate psychological pressure to rationalize holding. If you cannot honestly say "I am fine if this goes to zero," the position is too large for the current phase of the thesis.

Companies worth bookmarking: IonQ (NYSE: IONQ) — trapped ion, public, $130M 2025 revenue, aggressive acquisition strategy (Oxford Ionics, SkyWater Technology). First quantum company to exceed $100M revenue. Quantinuum — trapped ion, IPO 2026, highest gate fidelity in the industry (99.97% two-qubit), backed by Honeywell and strategic investors. QuEra — neutral atom, NVIDIA-backed, leading logical qubit demonstrations (96 logical qubits from 448 physical atoms, January 2026), not yet public at time of writing.

Existing portfolio exposure: IBM (NYSE: IBM) — superconducting, deepest quantum software ecosystem, Heron processors, below-threshold surface code memory milestone. Google (NASDAQ: GOOGL) — superconducting, Willow chip error correction milestone, NVentures quantum investments. If you already own IBM and Google for other reasons, you already have quantum exposure.

Stay away from: Companies whose revenue narrative depends on NISQ-era commercial applications (the hardware is not ready for commercial use). Companies making LLM acceleration claims (the thesis is wrong — see Chapter 4). Companies without a coherent answer to the big compute, small data filter (see Chapter 3). Rigetti (superconducting, no clear differentiation from IBM/Google), D-Wave (annealing architecture with contested utility claims).

What to watch for in portfolio companies: Logical error rate improvement (not physical qubit count). Sovereign procurement contract awards with specific deliverable milestones. NVIDIA deepening stakes. Architecture consolidation signals.

Decision rule: Open bookmark positions now. Keep them small (one to ten shares per company, or equivalent dollar amount you are comfortable losing entirely). Do not average down on bad news unless a breakthrough signal has fired. Do not size up until all four signals fire (Chapter 8).

Contributor notes: The confirmation bias section is psychologically important and should not be shortened. The "fine if this goes to zero" test is a practical risk management tool. The stay-away list should be specific — name the companies and the specific reason each fails the filter.

---

**CHAPTER 12 — The 2030 Investment Horizon**

*When to consult this chapter:* You want to understand the timeline and what to expect at each phase.

Keyword audit: PASS — "quantum timeline," "fault-tolerant quantum computing," "quantum advantage," "2030," "molecular simulation commercial deployment" should appear in the chapter body.

One-line: An honest, phase-by-phase timeline from now to 2035+ — what is likely, what is uncertain, and what would change the forecast.

Decision question: When will quantum computing actually matter, and what does that mean for my position?

The short answer: 2028 for credible fault-tolerant demonstrations. 2032-2035 for first economically important quantum advantage in molecular simulation. Post-2035 for broad transformation if molecular simulation delivers. Possibly never for general-purpose advantage.

Framework: Four phases with distinct investment implications.

Phase 1 (Now to 2028): Hardware science and error correction progress. No commercially meaningful quantum advantage. Sovereign procurement provides revenue floor for embedded companies. Classical AI accelerates drug discovery simultaneously, raising the baseline quantum must beat. Investment implication: bookmark position appropriate. Domain knowledge building. Watch for Phase 2 entry signals.

Phase 2 (2028 to 2032): First credible fault-tolerant demonstrations. Early chemical accuracy results on small transition metal complexes. Possible first sovereign procurement scale-ups. Architecture consolidation begins. Classical counterattack timeline on chemistry results starts lengthening. Investment implication: Signals 1 and 2 (scientific breakthrough + Flatiron verification) may begin firing. Modest position increase warranted if both fire.

Phase 3 (2032 to 2035): Potential first economically important quantum advantage in molecular simulation. If the four-part signal fires here, quantum stock repricing will be dramatic and fast. Pharma and materials companies begin building hybrid quantum-classical workflows. Investment implication: If all four signals have fired, meaningful position sizing warranted. Companies with Phase 2 sovereign procurement revenue and architecture leadership will capture disproportionate value.

Phase 4 (Post-2035): If quantum simulation delivers, counterfactual drug design becomes commercially real. Novel drug classes. Battery materials. Catalyst design. Potentially the most economically significant technology transition since the internet. Investment implication: At this stage, quantum is no longer a speculative position — it is infrastructure.

The pessimistic scenario: Gil Kalai (correlated noise) and Michel Dyakonov (continuous-parameter analog limits) argue fundamental physical constraints may prevent fault-tolerant quantum computing at scale. Their arguments are not obviously wrong. There is a non-trivial probability that quantum computing delivers on molecular simulation but nothing broader, or that hardware progress stalls before fault tolerance is achieved. The bookmark position is sized correctly for this scenario — it costs little if the pessimists are right.

Decision rule: Phase 1 → bookmark. Phase 2 + Signals 1+2 → modest increase. Phase 3 + all four signals → meaningful position. Phase 4 → treat as infrastructure, not speculation.

Contributor notes: The four-phase timeline should be a visual timeline graphic — horizontal axis is years, four phases clearly delineated, investment implication stated for each phase. The pessimistic scenario section is ethically required — handbook readers deserve to understand the full range of outcomes, not just the optimistic case.

---

**CHAPTER 13 — What to Read, Who to Trust**

*When to consult this chapter:* You want to build ongoing domain knowledge and need to know which sources are credible.

Keyword audit: PASS — "Scott Aaronson," "John Preskill," "Flatiron Institute," "NQCC," "quantum hype," "vendor roadmap" should appear in the chapter body.

One-line: The credibility hierarchy for quantum information — from primary source to press release — with specific red flags for investor-grade evaluation.

Decision question: Who should I trust for quantum investing information?

The short answer: Independent academic theorists and the Flatiron Institute. Specifically Scott Aaronson, John Preskill, and the Center for Computational Quantum Physics. Everyone with a financial stake in the outcome should be read skeptically.

Framework: Four-tier credibility hierarchy.

Tier 1 (High credibility): Scott Aaronson (UT Austin) — leading complexity-theoretic authority, consistently critical of premature claims, Shtetl-Optimized blog is the best free resource for investor-grade quantum skepticism. John Preskill (Caltech) — coined "NISQ" and "quantum supremacy," rigorous assessments of fault tolerance scaling, publishes timeline estimates independent of commercial pressure. The Flatiron Institute's Center for Computational Quantum Physics — the group that keeps neutralizing benchmark claims; if Flatiron cannot classically match a result, it is worth taking seriously. The NQCC (National Quantum Computing Centre) at Harwell — independent state-backed validation, hardware-agnostic, ProQure contract evaluator.

Tier 2 (Medium credibility): Peer-reviewed papers in Physical Review Letters, Nature Physics, Science. Government national quantum strategy documents (reveal timeline expectations honestly — governments plan conservatively). Independent academic resource estimation papers.

Tier 3 (Low credibility, read with caution): Vendor roadmaps (every company claims commercial advantage by 2029). Ecosystem partners selling cloud access. Financial analyst notes on quantum stocks (most analysts cannot evaluate the physics). Press releases about "quantum utility."

Tier 4 (Red flags — apply heavy discount): "Quantum AI" as primary value proposition (almost certainly the LLM thesis, which is wrong). Raw qubit counts without logical error rates. "Beyond classical" claims without naming specific classical methods compared. Results on 2D planar superconducting grids claiming volume-law entanglement (physically impossible given architecture). Any claim that does not distinguish physical qubits from logical qubits.

Decision rule: Before acting on quantum news, check whether Aaronson or Preskill has commented on it. Check whether the Flatiron Institute has a response. If neither has addressed it, it is probably too early to act on.

Contributor notes: Aaronson's Shtetl-Optimized blog should be cited and described specifically — it is the most investor-accessible primary source in the field. The red flags section should be presented as a visual checklist that can be torn out and kept next to the brokerage app.

---

## 3. SCOPE AND MARKET

### /m3 — Out of Scope

| Topic | Reason for exclusion |
|---|---|
| Options trading on quantum stocks | Outside reader profile; requires separate financial expertise |
| Quantum cryptography as investment thesis | Post-quantum cryptography is defensive IT spending, not a quantum hardware investment thesis |
| Quantum sensing and metrology | Real application but narrow market; separate handbook warranted |
| Quantum networking / quantum internet | Too early for investor-grade analysis; no commercial timeline |
| Specific price targets or buy/sell recommendations | This is a framework handbook, not financial advice |
| Quantum computing academic research funding | Government research grants ≠ commercial procurement; excluded to maintain investment focus |
| Detailed quantum error correction mathematics | Investor-grade description sufficient; full mathematics belongs in a physics text |

**Coherence check:** The excluded topics, taken together, are either too specialized (sensing, networking), too early (quantum internet), or outside the handbook's scope (financial advice, academic funding). No excluded topic implies a second book from this author except quantum sensing — which is a natural companion volume when the sensing market matures.

---

### /m4 — Adoption Risk Register

| # | Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|---|
| 1 | Timeline ages badly if quantum accelerates | Medium | Medium | "Currently" qualifier throughout; annual review recommended |
| 2 | Specific company mentions become stale | High | Low | Company names as examples, not recommendations; disclaimer in introduction |
| 3 | Four-part signal fires before second edition | Low | Low | Signal framework remains valid; specific thresholds may need updating |
| 4 | NVIDIA acquisition changes the thesis | Low | High | Chapter 10 explicitly addresses acquisition as a signal change |
| 5 | Pessimists (Kalai, Dyakonov) proven right | Low | Medium | Chapter 12 explicitly includes the pessimistic scenario |
| 6 | Reader expects financial advice | Medium | Medium | Disclaimer prominent in introduction and every chapter footer |
| 7 | Quantum+LLM thesis rehabilitated | Low | High | Chapter 4 is the most aging-risk chapter; annual review required |

**Top 3 risks:**

Risk 2 (specific company names aging) is the highest-frequency risk. The handbook should be positioned as a framework document — companies are illustrative examples, not recommendations. This must be stated clearly in the introduction and reinforced in Chapter 11.

Risk 1 (timeline ages badly) is managed by the "currently" qualifier throughout and the explicit phase-based timeline in Chapter 12. The framework survives timeline acceleration — the signals remain valid, only the timing changes.

Risk 7 (quantum+LLM thesis rehabilitated) is the highest-impact risk. If a genuine quantum speedup for dense matrix operations is demonstrated and survives Flatiron scrutiny, Chapter 4 requires a rewrite. Annual review of the dequantization literature is the mitigation.

---

## 4. COMPILED TOC OVERVIEW

### /g1 — Full TOC at a Glance

**PART ONE — FOUNDATIONS**
*What quantum is, what it is not, and the two filters that cut through the hype.*

- Chapter 1 — The Honest Starting Point
- Chapter 2 — What Quantum Actually Is (And Isn't)
- Chapter 3 — The Big Compute, Small Data Filter
- Chapter 4 — Why the Quantum + LLM Thesis Is Wrong

**PART TWO — THE THESIS**
*Where quantum advantage is real, how the classical response works, and which hardware is worth owning.*

- Chapter 5 — The Legitimate Killer App: Molecular Simulation
- Chapter 6 — The Classical Counterattack Pattern
- Chapter 7 — The Architecture Horse Race

**PART THREE — THE INVESTMENT FRAMEWORK**
*When to size up, what the demand floor actually is, and what NVIDIA's moves tell you.*

- Chapter 8 — The Four-Part Breakthrough Signal
- Chapter 9 — Sovereign Demand: The Floor That Matters
- Chapter 10 — NVIDIA's Position: The Sophisticated Hedge
- Chapter 11 — The Bookmark Position: Deliberate Small Exposure

**PART FOUR — THE HORIZON**
*The honest timeline, the range of outcomes, and who to trust.*

- Chapter 12 — The 2030 Investment Horizon
- Chapter 13 — What to Read, Who to Trust

---

## 5. AUDIT

### /g2 — TOC Audit Against the 7 Adoption Failure Modes

**Failure Mode 1 — The Author-Centered TOC:** ABSENT. Chapter order is organized around the reader's decision sequence, not the author's expertise. Chapters 1-4 answer "is this real?" Chapters 5-7 answer "what is the actual thesis?" Chapters 8-11 answer "what do I do?" Chapters 12-13 answer "what happens next and who do I trust?" A reader with a specific question can open any chapter and leave with an answer.

**Failure Mode 2 — The Topic List Disguised as a TOC:** ABSENT. Every chapter is named by the investor decision it serves, not the topic it covers. "The Big Compute, Small Data Filter" is a tool, not a topic. "The Four-Part Breakthrough Signal" is a decision framework, not a subject area. "The Bookmark Position: Deliberate Small Exposure" is an action prescription, not a financial concept.

**Failure Mode 3 — The Fat Middle:** ABSENT for a handbook. Practitioner handbooks are not subject to the fat middle failure mode — readers do not read sequentially. Every chapter must stand alone, and every chapter has an immediate practical payoff. The decision question and decision rule at the start and end of every chapter enforce this.

**Failure Mode 4 — The Coverage Trap:** PARTIAL. Chapter 2 (What Quantum Actually Is) is the coverage chapter most at risk. Its primary function is vocabulary alignment, not decision support. It earns its place — the investor vocabulary table is genuinely necessary — but it should be the shortest chapter in the book and should be explicitly labeled "read this once, refer back as needed" rather than treated as a required sequential read.

**Failure Mode 5 — The Aging Problem:** PRESENT (managed). Three high-aging-risk elements: specific company names and valuations (Chapter 11), the quantum+LLM thesis (Chapter 4 — if dequantization is reversed), and the classical counterattack timeline (Chapter 6 — ongoing as new results arrive). All three are flagged in the risk register with annual review recommendations. The framework chapters (Chapters 3, 8, 12) are low-aging-risk because they describe structural dynamics, not current states.

**Failure Mode 6 — The Unadoptable Structure:** ABSENT. Practitioner handbook chapters are self-contained by design. A reader can open any chapter without reading the others. The decision question / short answer / decision rule structure ensures every chapter delivers value in under five minutes if the reader needs only the conclusion.

**Failure Mode 7 — The Thesis-Free Book:** ABSENT. The thesis is stated explicitly in Chapter 1 and reinforced in every chapter's decision rule: small bookmark position now, domain knowledge always, wait for the four-part signal, size up when it fires. Every chapter serves this thesis — either by establishing what quantum is (Chapters 1-4), by explaining why the thesis is correct (Chapters 5-7), by operationalizing the thesis into decisions (Chapters 8-11), or by extending the thesis across time (Chapters 12-13).

**Priority fix:** Chapter 2 is the weakest chapter by the practitioner handbook standard — it is explanatory rather than decisional. The fix: add a decision rule to Chapter 2 that is specific to the vocabulary it introduces. Candidate: "If a quantum press release cannot be stated using these six terms, it is probably marketing. Use this chapter as a filter, not just a primer." This elevates the chapter from vocabulary instruction to a practical screening tool.

---

### /g3 — One-Page Book Pitch Summary

**Investing in Quantum: A Skeptic-First Framework for the Most Overhyped and Underspecified Technology Sector of the 2020s**

*A practitioner handbook for investors who want to know what is real before deciding how much to own.*

**Logline:** Quantum computing is real, the timeline is long, and almost everything you've read about it is wrong. Here is the framework.

**Thesis:** Quantum computing is a long-duration option on a narrow set of application classes — primarily molecular simulation — with a sovereign demand floor, a classical counterattack pattern that makes benchmark claims unreliable, and a four-part breakthrough signal that has not yet fired. The correct position size right now is small.

**Target reader:** A financially literate retail or professional investor with a technology-heavy portfolio, familiar with the AI investment narrative, skeptical of quantum hype, and wanting a rigorous framework that does not require a physics PhD.

**TOC at a glance:**

Part One — Foundations: The Honest Starting Point · What Quantum Actually Is · The Big Compute, Small Data Filter · Why the Quantum + LLM Thesis Is Wrong

Part Two — The Thesis: The Legitimate Killer App: Molecular Simulation · The Classical Counterattack Pattern · The Architecture Horse Race

Part Three — The Investment Framework: The Four-Part Breakthrough Signal · Sovereign Demand: The Floor That Matters · NVIDIA's Position: The Sophisticated Hedge · The Bookmark Position: Deliberate Small Exposure

Part Four — The Horizon: The 2030 Investment Horizon · What to Read, Who to Trust

**What this book is not:** Financial advice. A physics textbook. A trading manual. A bull case for quantum stocks. A bear case for quantum stocks.

**How it differs from existing coverage:** Financial press reports quantum events without evaluating them. Academic literature evaluates quantum claims without translating them for investors. This handbook translates peer-reviewed physics — specifically the dequantization literature, the classical counterattack pattern, the architecture horse race, and the sovereign procurement dynamics — into investor decision frameworks applicable without a physics background.

**Format:** 13 self-contained chapters, 2,000–4,000 words each. Every chapter opens with a decision question and closes with a decision rule. Readable in any order. Designed for investors who want to consult a specific question, not read cover to cover.

**Author:** Nik Bear Brown, PhD, MBA. Associate Teaching Professor, Northeastern University College of Engineering. Founder, Humanitarians AI. Semiconductor and quantum portfolio holder. Author of 150+ technical books. The Computational Skepticism Substack series provides ongoing updates to the frameworks in this handbook.

---

*Full TOC Draft v1.0 — compiled from all phase inputs*
*All phases complete: Vision (/i1–/i4), Chapter Architecture (/c1–/c2), Scope & Market (/m3–/m4), Build (/g1–/g3)*
*No blockers. Ready for chapter drafting.*
