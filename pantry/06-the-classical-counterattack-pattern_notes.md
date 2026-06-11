# Research Notes: Chapter 06 — The Classical Counterattack Pattern
**Source:** TIKTOC.md chapter entry
**Notes file:** 06-the-classical-counterattack-pattern_notes.md
**Corresponding chapter:** chapters/06-the-classical-counterattack-pattern.md (not yet written)
**Generated:** 2026-06-10

---
## Chapter summary (from TIKTOC.md)
**Decision question:** How do I evaluate a quantum "breakthrough" announcement before acting on it?
**Short answer:** Wait 12–24 months and apply the "Flatiron test." Every major quantum-advantage claim so far has been classically matched or substantially eroded within that window. This is structural, not accidental — current hardware lives on geometries that classical tensor-network methods are purpose-built to exploit.
**Framework:** The counterattack timeline (Google 2019 → IBM 2023 → D-Wave 2025), the structural reason (area-law entanglement on local lattices ⇄ tensor-network compression), and the profile of a counterattack-*resistant* result. Decision rule: don't trade on the announcement; wait for the classical response.

---
## A. Conceptual foundations

### Quantum advantage / "supremacy" vs. utility
"Quantum supremacy" (Preskill's term) means a quantum device performs *some* task — possibly contrived — beyond any feasible classical computer. "Quantum utility" (IBM's framing) softens this to *useful* computation at a scale where exact classical methods struggle, even before fault tolerance. The investor-relevant point: both are benchmark claims, and benchmarks can be designed to favor the quantum device. A claim only matters if (a) the problem is economically relevant, not engineered for the hardware, and (b) it is compared against the *best* classical method, not a brute-force strawman.

**Common misconception:** "Supremacy = useful." No. Random circuit sampling (Google) produces no useful output; it samples from a hard distribution. Utility ≠ supremacy ≠ commercial value — three different bars.
**Source(s):** Preskill, "Quantum computing in the NISQ era and beyond"; review arXiv:2412.14703.

### Area-law vs. volume-law entanglement (the structural crux)
Entanglement entropy measures how strongly a region of qubits is correlated with the rest. **Area law:** entanglement of a region scales with its *boundary* (surface), not its size — typical of ground states and short-time dynamics of *local* Hamiltonians on low-dimensional lattices. **Volume law:** entanglement scales with the region's *volume* — typical of highly entangled, long-time, or high-connectivity states. Classical **tensor networks** (MPS in 1D, PEPS in 2D, tree tensor networks) represent area-law states *efficiently* — their cost is controlled by the "bond dimension," which stays bounded when entanglement obeys an area law. Volume-law states blow up the bond dimension exponentially and defeat tensor networks.

The punchline: today's leading hardware (superconducting planar grids, near-term annealers) runs problems on **2D / local lattices** that tend to obey (or only mildly violate) the area law — *precisely the regime tensor networks were built to crush.* So the classical counterattack is not luck; it is the hardware handing the classical competitor exactly the structure it exploits.

**Common misconception:** "Entanglement-scaling arguments are asymptotic, so they don't apply at 100–300 qubits." Partly true — at supremacy scales (≈50–300 qubits) the asymptotics are a guide, not a proof, which is why some claims survive *longer* than others. But the geometry of correlations is still the right lens.
**Worked example / visual (TIKTOC):** The "pond metaphor" — drop a stone (local interaction) in a pond; ripples (entanglement) spread locally. A classical tensor network only has to track the ripple *front* (the boundary), not the whole pond — cheap. A non-planar, all-to-all "pond" has no clean front — expensive. Anchor visual: three-row table (Google / IBM / D-Wave) × columns {claim, classical response, time-to-response, what it proved}.
**Source(s):** arXiv:2603.18825 "Quantum Advantage: a Tensor Network Perspective"; arXiv:0903.5017 (tree tensor networks exploit area law); area-law/volume-law standard literature.

### The Flatiron Institute / Center for Computational Quantum Physics (CCQP)
The Flatiron Institute (Simons Foundation, NYC) hosts the Center for Computational Quantum Physics — a leading independent group in classical simulation of quantum systems (tensor networks, belief propagation, Monte Carlo). They are *not* a hardware vendor, so they have no stake in inflating quantum claims; they repeatedly produce the classical method that matches a "beyond-classical" result. Hence the "Flatiron test": if CCQP (or an equivalent independent group) has not tried to match a claim, it is unverified; if they tried and *failed* over 12–24 months, the claim gains credibility.

**Source(s):** Tindall et al. 2025 (below); Flatiron CCQP public profile.

---
## B. Domain examples and cases

**Case 1 — Google Sycamore (2019).** 53-qubit superconducting processor; random circuit sampling; claimed ~10,000 years for the best classical supercomputer (Summit). Classical counterattack: a sequence of tensor-network and algorithmic results (2021 onward) — notably a Chinese group using ~60–512 GPUs / Sunway supercomputer reproduced the sampling task at higher fidelity; by 2022 exact-amplitude verification (arXiv:2111.03011, 2103.03074, 2212.04749). Net: the "10,000 years" estimate collapsed to hours/minutes on classical hardware over ~2–5 years. **What it proved:** an engineered sampling benchmark, eventually classically matched — the original gap was an artifact of a weak classical baseline.

**Case 2 — IBM "utility" (2023).** 127-qubit Eagle processor, kicked-Ising dynamics with error mitigation, published in *Nature* ("Evidence for the utility of quantum computing before fault tolerance"). IBM framed it as beyond brute-force classical. Classical counterattack within **weeks**: Tindall, Fishman, Stoudenmire, Sels (Flatiron) used belief-propagation-contracted tensor networks (arXiv:2306.14887) to reproduce the observables *more* accurately than the quantum device; others used sparse Pauli dynamics / light-cone-confinement arguments (arXiv:2306.16372). **What it proved:** the dynamics stayed in a low-entanglement (confined) regime — area-law-friendly — so tensor networks won fast.

**Case 3 — D-Wave magnetic-materials (March 2025).** D-Wave's Advantage2 annealer simulated real-time dynamics of disordered quantum spin glasses on various lattices; *Science* paper; claimed roughly **1 million years on Frontier** to match with classical MPS on the largest systems. **Classical counterattack (also March 2025, same window):** Tindall et al. (Flatiron) + EPFL, "Dynamics of disordered quantum systems with two- and three-dimensional tensor networks" (arXiv:2503.05693, later in *Science*), used belief-propagation tensor networks to reach state-of-the-art accuracy on systems of **300+ qubits** with modest resources — and time-dependent variational Monte Carlo from related groups. **D-Wave's rebuttal:** Flatiron matched only a *subset* of lattice geometries / parameter regimes; the hardest, largest instances and the full demonstration scope were *not* fully reproduced; the 1-million-year figure stands for those.

**Status as of June 2026 (VERIFIED — IMPORTANT):** The D-Wave vs. Flatiron/EPFL dispute is **CONTESTED and UNRESOLVED**, not cleanly "matched." Both sides published; D-Wave issued a formal "Quantum Supremacy Result Stands" response arguing the classical work is a partial, isolated advance rather than a holistic replication. There is *no* clean, consensus classical refutation of the full D-Wave dataset as of this writing. The TIKTOC draft's phrasing "matched by Flatiron in May 2026" overstates settlement — see Gaps/Flags.

**Profile of a counterattack-RESISTANT result (TIKTOC):** (1) economically relevant problem, not an engineered benchmark; (2) compared against *best* classical methods, not brute force; (3) **volume-law entanglement on non-planar, high-connectivity graphs** (feasible on trapped-ion / neutral-atom, hard on planar superconducting grids); (4) an independent classical attempt (Flatiron-class) that *failed*, documented. No claim to date clears all four.

**Watch (TIKTOC):** results where the classical response takes **>12 months**; non-planar / high-connectivity topologies; independent academic replication with no vendor involvement.

---
## C. Connections and dependencies
**Prerequisites:** Chapter 2 (entanglement); helpful: Chapter 3 (engineered-benchmark sniff test).
**Unlocks:** Chapter 8 Signal 2 (Flatiron verification — result survives 12–24 months); Chapter 11 stay-away (D-Wave's contested utility); Chapter 13 Tier-1 credibility (Flatiron, Aaronson, Preskill).
**Adjacent connections:** Chapter 5 — even a real chemistry advantage must clear this test; the "fix removes the advantage" logic in Chapter 4 (barren plateaus) rhymes with "the geometry that runs on hardware is the geometry classical methods exploit." Chapter 7 — architecture matters here: only non-planar architectures (trapped ion, neutral atom) can plausibly reach the volume-law regime that defeats tensor networks.

---
## D. Current state of the field
**Settled:** Google 2019 and IBM 2023 were substantially classically matched (2019 over a few years; 2023 within weeks). Area-law ⇄ tensor-network-simulability is well-established theory. The pattern — engineered benchmark, then classical erosion — is real and repeated.
**Contested / emerging:** D-Wave 2025 — genuinely unresolved as of June 2026 (partial classical matches vs. D-Wave's defense of the hardest instances). Whether *any* near-term hardware can demonstrate a durable, useful, counterattack-resistant advantage. How far the asymptotic area-law argument extends at 100–300 qubit scales.
**Key references (3–5):** (1) Tindall, Fishman, Stoudenmire, Sels, arXiv:2306.14887 (IBM Eagle rebuttal). (2) Tindall et al., arXiv:2503.05693 → *Science* (D-Wave rebuttal). (3) D-Wave, *Science* 2025 spin-glass paper + "Quantum Supremacy Result Stands" response. (4) Sycamore classical-simulation line: arXiv:2111.03011, 2212.04749. (5) arXiv:2603.18825 "Quantum Advantage: a Tensor Network Perspective."
**Recent developments (last 3 yrs):** Belief-propagation tensor-network contraction matured into the default classical counterattack tool (2023→); explicit "evaluating classical simulations with a quantum processor" work (arXiv:2508.15759) reframing the contest as a moving boundary rather than a one-time line.

---
## E. Teaching considerations
**Where readers get stuck:** (1) Thinking "supremacy" means "useful." (2) Not grasping why *geometry* (planar vs. non-planar) decides who wins. (3) Assuming a *Nature*/*Science* paper settles it — these claims are routinely rebutted *in* the same venues. (4) Treating the D-Wave dispute as resolved (it is not).
**Analogies that work:** Pond/ripple (above). Also: tensor networks as "lossy compression tuned to exactly the kind of correlation local hardware produces" — like a codec optimized for one camera. Counterattack-resistance = "a problem whose correlations don't compress" (non-planar, volume-law).
**Exercises:** (a) Given a benchmark claim, run the four-part counterattack-resistance checklist and score it. (b) Classify Google/IBM/D-Wave by area-law vs. volume-law and predict (then check) the classical response time. (c) Find a 2026 "beyond classical" press release and locate (or note the absence of) an independent classical response.

---
## F. Library files relevant to this chapter
- `_lib_science-science-fictions-how-fraud-bias-negligence-and-hype-undermine-the-search-for.md` — **Strongly relevant.** Ritchie's *Science Fictions* supplies the hype/benchmark-theater framing: the "natural selection of bad science" (incentives reward attention-grabbing positive results), the hype-pipeline statistics (press releases exaggerate; 20× more likely to be echoed by news), and the NASA "arsenic life" case as a template for a splashy claim quietly walked back. Use it to argue the classical-counterattack pattern is a *specific instance* of a general scientific-hype dynamic — and to motivate "organized skepticism / nullius in verba" as the investor's stance. Pair Ritchie's incentive analysis with the structural (area-law) argument so the chapter has *both* a sociological and a physical reason the pattern recurs.
- `_lib_science-calling-bullshit...` (if present) — adjacent, optional, for the benchmark-rhetoric framing.

---
## G. Gaps and flags
- **FLAG (most important) — TIKTOC overstates the D-Wave resolution.** The draft says D-Wave's 2025 claim was "matched by Flatiron in May 2026 using belief-propagation tensor networks." VERIFIED status (June 2026): the Flatiron/EPFL work appeared in **March 2025** (arXiv:2503.05693), not May 2026, and matches only a *subset* of instances; D-Wave formally contests it and maintains the claim "stands." Correct the date and reframe as **contested/partial**, not settled. This is exactly the chapter's own thesis in action — a >12-month, still-unresolved classical response is itself a (weak) credibility signal for D-Wave, which the chapter should acknowledge honestly rather than declaring victory for the classical side.
- FLAG — Google "matched in 17 minutes by 2025-2026" (TIKTOC): the dramatic time figures vary by which simulation and metric; cite the specific paper for any quoted runtime rather than a single headline number. The robust claim is "classically matched/eroded over 2021–2025," not a single clean "17 minutes."
- FLAG — IBM "matched on a laptop within weeks": "within weeks" is correct; "on a laptop" is roughly true for the Flatiron belief-propagation result on the specific observables but verify the exact hardware claim before stating it flatly.
- GAP — Did not fetch the full D-Wave "Quantum Supremacy Result Stands" rebuttal text or the final published *Science* version of Tindall 2025 this pass; pull both before drafting to get authors/dates exact and to characterize precisely *which* instances remain unmatched.
- FLAG — Area-law argument is asymptotic; note explicitly that at 50–300 qubits it is a strong heuristic, not a theorem, which is *why* response times vary (weeks for IBM, years and counting for D-Wave's hardest instances).
