# Research Notes: Chapter 07 — The Architecture Horse Race
**Source:** TIKTOC.md chapter entry
**Notes file:** 07-the-architecture-horse-race_notes.md
**Corresponding chapter:** chapters/07-the-architecture-horse-race.md (not yet written)
**Generated:** 2026-06-10

---
## Chapter summary (from TIKTOC.md)
**Decision question:** Which quantum hardware architecture should I bet on?
**Short answer:** Superconducting leads near-term fault-tolerance progress; trapped ion leads gate fidelity; neutral atoms are the fastest-improving challenger; topological is scientifically unresolved; photonic is a long-duration bet. Nobody has won. Correct response: diversify across architectures or wait for convergence signals.
**Framework:** Compare the five architectures on the five fault-tolerance metrics that matter — physical error rate, coherence time, gate speed, qubit connectivity, qLDPC code compatibility. Convergence signal = heterogeneous architecture (fast local compute + high-fidelity memory + quantum networking), not one modality winning outright.

---
## A. Conceptual foundations

### The five fault-tolerance metrics (the comparison axes)
The chapter's anchor is a five-by-five matrix. **(1) Physical error rate** — the raw per-gate/per-qubit error before error correction; everything downstream depends on getting this below the surface-code threshold (~1%, practically <0.5–0.7%). **(2) Coherence time** — how long a qubit stays quantum (T1/T2) before the environment destroys the state; trapped ions hold superposition for seconds, superconducting qubits for tens-to-hundreds of microseconds. **(3) Gate speed** — how fast a two-qubit operation runs; superconducting gates are nanosecond-scale, trapped-ion gates microsecond-to-millisecond. The investor-relevant tension: trapped ions have far better coherence *and* fidelity but run gates ~1,000–100,000× slower, so a "logical clock speed" comparison is not won on fidelity alone. **(4) Qubit connectivity** — which qubits can directly interact. Superconducting planar grids connect only to nearest neighbors; trapped ions and neutral atoms achieve all-to-all or reconfigurable connectivity, which matters enormously for error-correction overhead. **(5) qLDPC compatibility** — see below.

**Common misconception:** "Higher fidelity wins." Fidelity is necessary, not sufficient. A processor's usable power is roughly (fidelity) × (clock speed) × (connectivity-driven code efficiency). Trapped ions lead axis 1–2 and lose axis 3; superconducting is the mirror image.
**Worked example:** IonQ's 99.99% two-qubit fidelity (Oct 2025) is the field's best, but its gates are ~100 microseconds vs. Google Willow's ~tens of nanoseconds. The architecture race is a Pareto frontier, not a single ranking.
**Source(s):** TIKTOC ch.7; IonQ blog "Accelerating Towards Fault Tolerance"; arXiv:2510.17286 (trapped-ion >99.99% without ground-state cooling).

### qLDPC codes and the planar-grid problem
The surface code — the workhorse error-correction scheme — needs only nearest-neighbor connectivity (ideal for a planar superconducting grid) but is *expensive*: roughly 1,000 physical qubits per logical qubit at useful error rates. **qLDPC (quantum low-density parity-check) codes** promise far lower overhead — potentially tens of physical qubits per logical qubit — but require *non-local* connectivity: qubits must talk to partners that are not their geometric neighbors. A 2D superconducting planar grid physically cannot wire those long-range checks without crossing wires it does not have. Neutral-atom arrays (atoms physically moved by optical tweezers) and trapped ions (all-to-all via shared motional modes) *can* implement the non-local checks, so qLDPC is their structural advantage. This is the deepest reason the "horse race" is not a straight line: the connectivity that superconducting sacrifices for speed is exactly what qLDPC needs.

**Common misconception:** "More physical qubits = closer to useful." The overhead ratio (physical:logical) set by the code and connectivity matters more than raw count. qLDPC could cut the ratio 10–50×.
**Source(s):** TIKTOC ch.7; QuEra Nature paper Jan 2026 (used high-rate [[16,6,4]] qLDPC-style codes); IBM qLDPC roadmap commentary.

### Below-threshold error correction (what "it works" means)
A code is **below threshold** when increasing the code distance (adding physical qubits) *decreases* the logical error rate — error correction is finally winning rather than adding noise. The headline 2024 result: Google's Willow demonstrated a distance-7 surface-code memory whose logical error rate dropped by Λ = 2.14 each time distance increased by 2, beating break-even by 2.4×. This is the single most important "the physics works" milestone in the sector and the reason superconducting "leads near-term fault tolerance progress."

**Source(s):** Nature s41586-024-08449-y; research.google QEC blog.

---
## B. Domain examples and cases

**Case 1 — Superconducting / Google Willow (Dec 2024) [VERIFIED].** 105-qubit processor; a distance-7 surface-code logical memory using 101 physical qubits; logical error per cycle 0.143% ± 0.003%; suppression factor Λ = 2.14 ± 0.02 per distance-2 increase; beyond break-even by 2.4×. First convincing below-threshold memory. Establishes superconducting as most mature on the fault-tolerance path. Caveat: one logical memory, not computation; planar grid blocks qLDPC.

**Case 2 — Neutral atom / QuEra (Jan 2026) [VERIFIED].** Published in *Nature*: up to **96 logical qubits from 448 physical rubidium atoms** using high-rate [[16,6,4]] codes; below-threshold surface-code QEC with ~2.14× error suppression; demonstrated transversal gates, lattice surgery, and teleportation-based universality in a single system; logical error rates improved as the system scaled. Doubles the prior verified-logical-qubit record (~48) within ~13 months. Best evidence for "fastest-improving challenger." Note the suppression factor coincidentally matches Willow's 2.14 — flag for fact-checkers to keep these distinct.

**Case 3 — Trapped ion / IonQ + Oxford Ionics [VERIFIED].** IonQ achieved >99.99% two-qubit gate fidelity (Oct 2025), a world record, via a "smooth gate" technique from the Oxford Ionics team — without ground-state cooling. IonQ **completed** the $1.075B acquisition of Oxford Ionics on **17 September 2025** ($1.065B stock + ~$10M cash). Oxford Ionics' edge: ion traps fabricated on **standard semiconductor (silicon) chips** with *electronic* qubit control replacing bulky laser systems — the credible scaling path for trapped ion. Combined roadmap targets: 256 physical qubits @99.99% by 2026; >10,000 physical qubits by 2027; 2M physical qubits by 2030. (Treat roadmap numbers as aspirational — see Flags.) Quantinuum H-series: first to "three nines" (99.9%) two-qubit fidelity across all qubit pairs in a production device.

**Failure / unresolved case — Microsoft topological / Majorana 1 [VERIFIED, with nuance].** History: two retractions of Majorana-evidence papers (2018 paper retracted 2021; a 2021 follow-on disputed/corrected). Feb 2025: Microsoft announced the **Majorana 1** chip. Measured parity lifetimes (published July 2025): **Z-loop parity ~10 ms** (≈10⁻² s), with ~0.5% measurement assignment error — strongly topologically protected; **X-loop parity ~14.5 microseconds**, with **~16% measurement assignment error** — degrades in microseconds and is the weak link. (TIKTOC's "12.4 ms Z / microseconds X at ~84% fidelity" is the correct *ballpark*; the published X-loop figure is ~16% error ≈ 84% fidelity — consistent. The exact 12.4 ms Z figure should be cited to the specific paper — see Flags.) A full high-fidelity logical topological qubit has *not* been demonstrated to independent-expert satisfaction; physicists remain "mostly unconvinced." Verdict: high upside if the physics holds, not investable on current evidence. Do not soften.

---
## C. Connections and dependencies
**Prerequisites:** Ch.2 (qubit vs. logical qubit; physical vs. logical error rate; coherence time). Helpful: Ch.6 (area-law vs. volume-law — connectivity is what lets non-planar architectures reach the volume-law regime that defeats tensor networks).
**Unlocks:** Ch.8 Signal 1 (a scientific breakthrough needs enough logical qubits at enough fidelity — architecture determines who gets there first). Ch.9 (Oxford Ionics and the UK NSIA conditions; sovereign hardware sits on specific architectures). Ch.10 (NVIDIA's NVQLink is architecture-agnostic *because* no architecture has won). Ch.11 stay-away (single-architecture concentration risk).
**Adjacent connections:** Ch.6 — only non-planar architectures (trapped ion, neutral atom) can plausibly reach volume-law entanglement on non-planar graphs, the counterattack-resistant regime.

---
## D. Current state of the field
**Settled:** Superconducting is most mature on demonstrated below-threshold QEC (Willow). Trapped ion holds the gate-fidelity lead (IonQ >99.99%, Quantinuum 99.9% in production). Neutral atom is improving fastest on verified logical-qubit count (QuEra 96). qLDPC needs non-local connectivity; planar superconducting grids cannot natively run it. No architecture has demonstrated a useful, fault-tolerant *computation*.
**Contested / emerging:** Whether trapped ion's slow gates can be offset by fidelity and connectivity at scale; whether neutral-atom logical-qubit counts translate into useful logical *operations*; whether topological qubits work at all. The "heterogeneous convergence" thesis (different modalities as compute vs. memory, linked by quantum networking) vs. one modality winning.
**Key references (3–5):** Google Willow — Nature s41586-024-08449-y (2024). QuEra 96 logical qubits — Nature (Jan 2026). IonQ/Oxford Ionics — TheQuantumInsider, 17 Sep 2025; arXiv:2510.17286. Microsoft Majorana 1 — Microsoft Source feature (Feb 2025) + TheQuantumInsider parity-lifetime piece (Jul 2025); ScienceNews skeptic coverage.
**Recent developments (last 3 yrs):** Willow below-threshold (2024); IonQ closes Oxford Ionics + 99.99% record (2025); QuEra 96 logical qubits (Jan 2026); NVIDIA NVQLink open quantum-classical interconnect launched at GTC 2026 (relevant to convergence — see Ch.10).

---
## E. Teaching considerations
**Where readers get stuck:** Conflating physical and logical qubit counts; assuming "fastest gate" or "highest fidelity" is a total ranking; not seeing why connectivity (a geometry fact) drives error-correction *cost*. The qLDPC/planar-grid point is subtle — readers need the picture that long-range checks require qubits that can be physically moved or all-to-all coupled.
**Analogies that work:** Pareto frontier / decathlon — no single winner, different events. Superconducting = a sprinter (fast, fragile); trapped ion = a marathoner (slow, durable, precise). Connectivity = a city's road network: a grid (superconducting) only lets you reach neighbors; a teleport network (neutral atom tweezers, ion all-to-all) lets any two points connect — which is what cheap error-correcting codes demand.
**Exercises:** (1) Build the 5×5 matrix and score each cell leads/competitive/lags/unresolved. (2) Given a press release claiming "1,000 qubits," list the three questions that determine whether it matters (logical? error rate? who verified?). (3) Argue both sides of "trapped ion's slow gates are/aren't fatal at scale."

---
## F. Library files relevant to this chapter
- `_lib_math-the-signal-and-the-noise-...md` — Silver on distinguishing signal from noise in technology forecasting; useful for "ignore press-release qubit counts, watch logical-qubit-below-threshold." Modest contribution.
- `_lib_science-calling-bullshit-...md` — evaluating "world's largest / world record" claims without specified, verified metrics; directly supports the "What to ignore" section.
- Others (How to Measure Anything, Noise) more relevant to Ch.8.

---
## G. Gaps and flags
- **FLAG:** Microsoft Z-loop "12.4 ms" exact figure — published sources I found state ~10⁻² s (~10 ms) ballpark; X-loop ~14.5 µs with ~16% error (≈84% fidelity, consistent with TIKTOC). Cite the specific Majorana 1 parity-lifetime paper for the precise 12.4 ms before printing that number.
- **FLAG:** IonQ/Oxford Ionics roadmap (256 qubits 2026; 10,000 by 2027; 2M by 2030) is a *vendor roadmap* — TIKTOC's own "What to ignore" warns against these. Present as company targets, not facts.
- **FLAG:** QuEra "2.14× suppression" coincides numerically with Willow's Λ=2.14 — verify these are independent figures in their respective papers; do not let the coincidence read as a copy error.
- **GAP:** Photonic architecture (PsiQuantum, Xanadu) is under-researched here — confirmed: PsiQuantum two-qubit logical ops >99.2%; Xanadu published a GKP error-correction result in PRL June 2025; both are "long-duration" bets. Pull one concrete photonic milestone for balance.
- **GAP:** "Heterogeneous convergence" has no single canonical citation yet; frame as the author's synthesis plus NVQLink (GTC 2026) as the early interconnect evidence.
