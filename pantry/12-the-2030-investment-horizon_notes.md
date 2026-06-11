# Research Notes: Chapter 12 — The 2030 Investment Horizon
**Source:** TIKTOC.md chapter entry
**Notes file:** 12-the-2030-investment-horizon_notes.md
**Corresponding chapter:** chapters/12-the-2030-investment-horizon.md (not yet written)
**Generated:** 2026-06-10

---
## Chapter summary (from TIKTOC.md)
**Decision question:** When, realistically, does quantum become investable, and what should I do in each phase? **Short answer:** Not yet on fundamentals; a phased, signal-gated plan from now to post-2035. **Framework — four phases:**
- **Phase 1 (now–2028):** hardware science + error correction; *no* commercial advantage; sovereign procurement is the revenue floor; classical AI keeps *raising the baseline* quantum must beat → action: **bookmark only**.
- **Phase 2 (2028–2032):** first credible fault-tolerant demonstrations; early chemical accuracy on small transition-metal complexes; Signals 1+2 may fire → **modest increase**.
- **Phase 3 (2032–2035):** potential first *economically important* advantage in molecular simulation; dramatic repricing *if* the four-part signal fires.
- **Phase 4 (post-2035):** counterfactual drug design, novel materials → quantum as infrastructure.
**Ethically required pessimistic scenario:** present Gil Kalai (correlated noise may prevent scalable fault tolerance) and Michel Dyakonov (continuous-parameter / analog limits) *fairly*, not as fringe — fundamental constraints might block FTQC entirely.

---
## A. Conceptual foundations

### Phasing as a signal-gated decision tree, not a forecast
The chapter's discipline is to refuse a point prediction. Instead each phase is defined by *which signals have fired*, so the investor acts on observed milestones rather than on roadmaps. The honest claim is "here is what would have to be true to move from Phase N to N+1," not "quantum arrives in year X." This protects against the prediction failures Silver catalogues — confident timelines in immature fields are usually overconfident.
**Common misconception:** that a roadmap date (IBM 2029, Google ~2030) is a *prediction*; it is a vendor's *plan*, Tier-3 evidence (Ch 13). Treat it as a hypothesis to be tested by independent milestones.
**Worked example:** IBM's public plan is **Starling (2029): ~200 logical qubits, 100M gates**, then **Blue Jay (2033+): ~2000 logical qubits, 1B gates**. Read these as the bar Phase-2/Phase-3 *demonstrations* must independently clear, not as guarantees.
**Source(s):** IBM Quantum roadmap blog; The Quantum Insider roadmap survey, 2025.

### The moving classical baseline (why "quantum advantage" recedes)
Quantum does not have to beat *yesterday's* classical computer — it must beat the best *classical method available when it ships*. Classical AI and better tensor-network / belief-propagation methods keep raising that baseline (the Flatiron classical-simulation work is the recurring example). So a milestone that looked like advantage in 2025 can be erased by a 2026 classical paper. This is why Phase 1's correct action is to wait: the target is moving in the defender's favor.
**Common misconception:** "once quantum does X faster than any 2024 computer, it's won." No — the comparison must be against the *contemporaneous* best classical method, honestly specified.
**Source(s):** Flatiron CCQ classical-algorithm work (Science, May 2026); Ch 6 notes.

### The pessimistic scenario as a live hypothesis (Kalai, Dyakonov)
**Gil Kalai (Hebrew U / NYU):** conjectures that noise in entangled systems is *correlated* in a way that scales with the computation, so error rates cannot be pushed below the fault-tolerance threshold in practice — a *complexity-theoretic* wall, not an engineering hurdle. His arguments are in arXiv:1908.02499 ("The Argument against Quantum Computers") and related papers. **Michel Dyakonov:** argues the exponential number of *continuous* parameters in a many-qubit state makes a quantum computer an irreducibly *analog* device, and analog devices have never been made fault-tolerant — a control/precision limit.
**Common misconception:** that these are "anti-science" or fringe positions. They are not — Kalai is a major mathematician and *understands fault-tolerance theory* (Aaronson has debated him respectfully for ~15 years). The chapter must present them as a minority but serious hypothesis that recent below-threshold results *pressure but have not yet refuted*.
**Worked example:** QuEra's Jan-2026 below-threshold result across 96 logical qubits is exactly the kind of evidence that *weakens* Kalai's conjecture — but Kalai's reply is that the wall appears only at larger scales/longer circuits than demonstrated so far.
**Source(s):** Kalai arXiv:1908.02499; Aaronson "Response to M. I. Dyakonov" (scottaaronson.blog); QuEra podcast with Kalai.

---
## B. Domain examples and cases

### Case 1 — Phase 1 in action (now–2028)
2025–26 milestones (>99.9% two-qubit fidelities on multiple platforms; QuEra 96 logical qubits; IBM Nighthawk + new Heron) are *scientific* progress with *no* commercial quantum advantage. Revenue that exists (IonQ $130M, D-Wave $24.6M) is hardware sales, cloud access, and sovereign/government procurement — the "revenue floor," not advantage. Correct action: bookmark (Ch 11).

### Case 2 — what a Phase-2 trigger looks like (2028–2032)
A *credible, independently reproduced* fault-tolerant demonstration plus an early chemical-accuracy result on a small transition-metal complex (e.g., a model of an active site) where the classical comparison is honestly specified and quantum wins. This would fire Signals 1 (real logical-qubit fault tolerance) and 2 (a defensible advantage in the legitimate killer app). Action: modest increase from bookmark.

### Failure case — the BCG/McKinsey forecast spread
Forecaster estimates diverge widely: industry roadmaps cluster on **2029–2030** for first-gen FTQC, while one McKinsey-cited survey has only 72% of executives expecting *commercial* FTQC by **2035**, and other segmentations push "full-scale fault tolerance" past **2040**. The spread itself is the lesson — when credible forecasters disagree by a decade, the honest investor gates on signals, not dates. (Treat specific consultancy market-size dollar figures as the least reliable input.)

---
## C. Connections and dependencies
**Prerequisites:** Ch 5 (molecular simulation = the Phase-3 economic prize), Ch 6 (classical counterattack = the moving baseline), Ch 8 (the four-part signal that gates each phase), Ch 11 (bookmark = Phase-1 action).
**Unlocks:** Ch 13 (who to trust to *adjudicate* whether a phase trigger really fired).
**Adjacent:** Ch 9 (sovereign procurement = the Phase-1 revenue floor), Ch 10 (orchestration-layer revenue accrues across all phases regardless of timing).

---
## D. Current state of the field
**Settled:** No commercial quantum advantage exists as of mid-2026; below-threshold error correction is now demonstrated on multiple platforms (a real, recent change); fault-tolerance *at useful scale* has not been shown.
**Contested / emerging:** the timeline (2029 vs. 2035 vs. 2040+); whether below-threshold results extrapolate to large circuits (the precise locus of the Kalai dispute); whether any near-term chemistry result will survive a classical counterattack.
**Key references:** IBM Quantum "large-scale FTQC" roadmap blog; Kalai, arXiv:1908.02499; Aaronson, "Response to Dyakonov" (scottaaronson.blog); McKinsey/BCG quantum outlooks; The Quantum Insider roadmap survey 2025.
**Recent developments (last 3 yrs):** Google Willow below-threshold (2024); QuEra 96 logical qubits (Jan 2026, Nature); IBM Nighthawk + Heron (Jan 2026); Flatiron classical-simulation advance (Science, May 2026); Aaronson's Dec-2025 "optimistic" post acknowledging the residual Kalai doubt.

---
## E. Teaching considerations
**Where readers get stuck:** wanting a date. The chapter must repeatedly redirect "when?" into "what would I have to *see*?"
**Analogies that work:** phases as airport boarding groups — you don't move until your group (signal) is called; the moving classical baseline as a *high-jump bar that rises every time you train*.
**Exercises:** (1) For each phase, write the *single* milestone whose independent reproduction would justify moving up. (2) Steelman Kalai in 150 words, then state the one experimental result that would refute him. (3) Plot the IBM/Google/Quantinuum roadmap dates and the McKinsey/BCG survey dates on one axis; measure the spread; argue why the spread implies signal-gating.

---
## F. Library files relevant to this chapter
- `_lib_math-the-signal-and-the-noise-why-so-many-predictions-fail-but-some-don-t.md` — **Strongly relevant.** Silver's central lessons — overconfident point forecasts in immature domains, the value of probabilistic/Bayesian updating, separating signal (reproduced milestones) from noise (vendor roadmaps, stock moves) — directly justify the phase-and-signal architecture over a single 2030 prediction. Use to frame "why we refuse a date."
- `_lib_physics-the-physics-of-wall-street-a-brief-history-of-predicting-the-unpredictable.md` — relevant for framing: the history of physics-derived market models that over-promised predictive power is a cautionary parallel for treating quantum roadmaps as forecasts. Lighter touch than Silver; use for one framing line on the seduction of mathematical timelines.

---
## G. Gaps and flags
- **FLAG — verify the exact Aaronson Dec-2025 quote.** The search returned a paraphrase: roughly "With every experimental milestone, the little voice in my head that asks 'but what if Gil Kalai turned out to be right after all?'…" — confirm exact wording and date directly from scottaaronson.blog before quoting.
- **FLAG — Dyakonov framing.** His best-known argument (continuous parameters → analog → un-correctable) should be cited to his own writing (e.g., his IEEE Spectrum piece and book *Will We Ever Have a Quantum Computer?*), not to a secondhand summary. The search did not surface a *recent* (2024–26) Dyakonov publication — note he may not have published recently; present his standing argument, not a fresh 2026 statement, unless one is found.
- **GAP — specific BCG/McKinsey dollar market-size figures** were not verified in this pass; if used, cite the exact report and year, and flag them as Tier-3 (Ch 13).
- **FLAG — phase boundary years (2028/2032/2035) are the book's own scaffold,** not consensus forecasts; present them as the author's framework, not as predictions, to stay consistent with the chapter's anti-forecast thesis.
- **GAP — "early chemical accuracy on small transition-metal complexes"** as a Phase-2 marker is plausible but no specific 2026 result meeting it was found; describe as a *target*, not an achieved milestone.
