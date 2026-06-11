# Chapter 7 — The Architecture Horse Race

## Decision question

You have decided that quantum computing is worth a small position. Now you face the question that every brokerage screen forces on you: *which one?* IonQ and Rigetti and D-Wave are all public; Quantinuum and QuEra and PsiQuantum are circling an IPO; and behind all of them sit IBM and Google, who build quantum hardware inside companies you may already own for other reasons. They are not building the same machine. They are building five fundamentally different machines, using five different physical systems to store a qubit, and the differences are not cosmetic — they determine which company reaches a useful, error-corrected computer first, and which spends a decade stuck. This chapter answers: **which quantum hardware architecture should I bet on?**

## The short answer

Nobody has won, and betting on a single architecture today is a concentration risk disguised as conviction. Superconducting qubits lead on demonstrated error-correction progress; trapped ions lead on raw qubit quality; neutral atoms are improving fastest; topological is scientifically unresolved and not investable on current evidence; photonics is a long-duration bet. The disciplined move is to own the leaders across modalities, or wait for a convergence signal, rather than to pick the "winner" before the race has a winner.

## Why this matters

The cost of getting this wrong is not subtle. Quantum hardware companies are pre-revenue or barely-revenue option bets, and an option on the wrong technology can go to zero even if quantum computing as a field succeeds spectacularly. The history of technology is full of correct theses and wrong horses: people who believed the internet would be huge in 1999 and bought the companies that died anyway. If you concentrate in one architecture because a press release impressed you, you are exposed to a specific, physical, possibly fatal engineering risk that has nothing to do with whether quantum computing eventually matters.

The deeper reason this matters is that the architecture question is where the marketing is thickest. Every vendor ranks its own architecture first, and each can do so honestly, because each architecture genuinely leads on *some* metric. The only defense is to know which metrics actually determine who reaches fault tolerance — the point at which a machine can run a long computation without errors accumulating faster than they can be corrected — and to score every architecture on all of them at once, rather than letting a vendor pick the one axis where it wins.

## The framework

There are five metrics that decide the fault-tolerance race. A *qubit* is the quantum version of a bit; a *logical qubit* is a single reliable qubit built out of many noisy physical ones, with error correction stitching them together. Everything below is about how cheaply and quickly each architecture can build logical qubits that actually stay correct.

**1. Physical error rate.** The raw chance that a single operation goes wrong before any error correction is applied. This is the foundation: error correction only helps if the underlying error rate is below a threshold (roughly 1%, and practically you want it well under that). Lower is better. *Trapped ions lead.*

**2. Coherence time.** How long a qubit stays quantum before the surrounding environment scrambles it — the process called decoherence. Trapped ions hold their state for seconds; superconducting qubits for tens to hundreds of microseconds. Longer is better. *Trapped ions lead.*

**3. Gate speed.** How fast a two-qubit operation runs. Superconducting gates fire in nanoseconds; trapped-ion gates take microseconds to milliseconds — roughly a thousand to a hundred thousand times slower. Faster is better. *Superconducting leads.*

This is the central tension. Trapped ions have far better error rates *and* far longer coherence, but their gates are agonizingly slow. A machine's usable power is roughly its fidelity multiplied by its clock speed multiplied by how efficiently its layout lets error correction run. The race is a Pareto frontier — a set of trade-offs where no competitor dominates on every axis — not a single leaderboard. Superconducting is the sprinter: fast and fragile. Trapped ion is the marathoner: slow, durable, precise.

**4. Qubit connectivity.** Which qubits can directly talk to which. Superconducting chips are flat grids where a qubit only touches its nearest neighbors. Trapped ions can interact all-to-all through a shared vibration; neutral atoms can be physically picked up and moved by laser "tweezers" to sit next to any partner. More flexible connectivity is better, and it matters more than investors expect — because of the fifth metric.

**5. qLDPC code compatibility.** This is the subtle one, and it is where the whole race bends. The standard error-correction scheme, the *surface code*, needs only nearest-neighbor connectivity — perfect for a flat superconducting grid — but it is brutally expensive, demanding on the order of a thousand physical qubits for one good logical qubit. A newer family, *quantum low-density parity-check (qLDPC) codes*, promises to cut that overhead enormously, potentially to tens of physical qubits per logical qubit. The catch: qLDPC codes require qubits to talk to partners that are not their geometric neighbors. A flat superconducting grid physically cannot wire those long-range connections without wires it does not have. Neutral-atom arrays and trapped ions *can*, because they can reposition or all-to-all couple their qubits. So the connectivity that superconducting sacrificed for speed is exactly what the cheap codes require. *Neutral atoms lead; superconducting planar grids cannot do it natively.*

Score the five architectures across these five metrics and you get the honest matrix:

| Architecture | Physical error rate | Coherence time | Gate speed | Connectivity | qLDPC compatibility |
|---|---|---|---|---|---|
| Superconducting | Competitive | Lags | **Leads** | Lags | Lags (planar grid) |
| Trapped ion | **Leads** | **Leads** | Lags | Leads | Competitive |
| Neutral atom | Competitive | Competitive | Competitive | Leads | **Leads** |
| Topological | Unresolved | Unresolved | Unresolved | Unresolved | Unresolved |
| Photonic | Competitive | Long-duration bet | Competitive | Competitive | Emerging |

No row wins every column. That is the entire point.

## What it looks like in practice

Three verified milestones show the race as it actually stands in mid-2026.

**Superconducting — Google Willow (December 2024).** Google's 105-qubit Willow processor ran a surface-code logical memory and demonstrated something genuinely important: as they made the code bigger (adding physical qubits), the logical error rate went *down* rather than up. The technical term is *below threshold* — error correction finally winning instead of adding more noise than it removes. Each step up in code size cut the logical error rate by a factor of about 2.14, beating the break-even point by 2.4× (Google, *Nature*, 2024). This is the single most convincing "the physics actually works" result the field has produced, and it is why superconducting "leads near-term fault tolerance." The caveat: it is one logical *memory*, not a computation, and the planar grid blocks the cheaper qLDPC codes.

**Neutral atom — QuEra (January 2026).** Published in *Nature*, QuEra demonstrated up to **96 logical qubits built from 448 physical rubidium atoms**, using high-rate codes, with below-threshold error suppression — and crucially, demonstrated the operations (transversal gates, lattice surgery, teleportation) needed for universal computation in a single system, with logical error rates that improved as the system scaled. That roughly doubled the prior verified logical-qubit record in about thirteen months. This is the best single piece of evidence for neutral atoms as the fastest-improving challenger. (Note: the error-suppression factor in this work happens to be numerically close to Willow's — they are independent results, not a typo.)

**Trapped ion — IonQ and Oxford Ionics.** IonQ reported a **~99.99% two-qubit gate fidelity** in October 2025 — the best two-qubit gate result on record. Be precise about what that means: it is a *record two-qubit gate fidelity*, not a claim that an entire system runs at that fidelity at scale. The gap between "our best gate hits 99.99%" and "our whole processor runs at 99.99% across thousands of qubits" is exactly where trapped ion's scaling challenge lives, given those slow gates. IonQ **completed its acquisition of Oxford Ionics on 17 September 2025** for roughly $1.075 billion (mostly stock). Oxford Ionics' edge is that it builds ion traps on standard silicon semiconductor chips with *electronic* control replacing bulky laser systems — the most credible scaling path anyone has shown for trapped ion. (The two companies' combined roadmap targets — thousands of qubits by 2027, millions by 2030 — are *vendor roadmap* numbers. Treat them as aspirations, not facts; this book's own rule is to ignore vendor roadmaps.)

**Topological — Microsoft, the honest assessment.** This one requires no softening. Microsoft's pursuit of the topological qubit — a design that would be intrinsically protected from errors by the physics itself — has a troubled record: **two retractions of supporting papers (2021–2022)**. In February 2025 Microsoft announced its **Majorana 1** chip. The measured results are genuinely mixed: one type of parity measurement (the Z-loop) showed a long lifetime of around ten milliseconds with low error, which is encouraging, but the other (the X-loop) degrades in microseconds with roughly 16% measurement error — about 84% fidelity, the weak link [verify — exact 12.4 ms Z-loop figure should be cited to the specific Majorana 1 parity paper before printing]. The blunt assessment: **no full, high-fidelity logical topological qubit has been demonstrated to the satisfaction of independent experts**, and most physicists remain unconvinced. The upside, if the physics holds, is enormous — but on current evidence topological is **not investable.** High potential is not the same as demonstrated capability, and an investor who cannot tell them apart will lose money.

**Photonic — the long-duration bet.** PsiQuantum and Xanadu pursue qubits made of light. Photons barely decohere and move at light speed, which is attractive, but generating and entangling them reliably is hard. PsiQuantum has reported two-qubit logical operations above 99.2%, and Xanadu published an error-correction result in 2025 [verify]. These are real but early. Photonics is a credible long-horizon contender, not a near-term leader.

## What to watch for

- **IonQ's silicon-integrated trap progress.** The Oxford Ionics acquisition is a bet that electronic control on standard chips solves trapped ion's scaling problem. Demonstrated progress here — not roadmap slides — would be the most important trapped-ion signal.
- **QuEra scaling past 100 logical qubits with below-threshold error rates and useful operations.** Logical *count* is necessary but not sufficient; watch for logical *operations* at that scale.
- **Any architecture demonstrating high-connectivity, non-planar entanglement at scale** — the regime that both enables cheap qLDPC codes and resists the classical counterattack pattern (Chapter 6).
- **The convergence signal.** The likeliest endgame is not one architecture winning outright but a *heterogeneous* machine — superconducting or photonic handling fast local computation, trapped ion or neutral atom serving as high-fidelity memory, linked by quantum networking. Watch for standardized quantum interconnect protocols (NVIDIA's NVQLink, launched 2026, is early evidence of the industry building toward this). If the future is heterogeneous, owning multiple architectures is not hedging — it is owning the actual architecture.

## What to ignore

- **Press-release qubit counts.** A "1,000-qubit" announcement tells you nothing without the logical error rate and connectivity. Raw count is the most-marketed, least-meaningful number in the sector.
- **"World's largest quantum computer" claims** that do not specify *logical* qubits and *logical* error rates, verified by someone other than the vendor.
- **Vendor roadmap comparisons between architectures.** Every company's roadmap shows its own architecture winning. These are sales documents.
- **Single-metric victory laps.** "Highest fidelity" or "fastest gate" is a real fact about one column of the matrix and tells you nothing about the other four.

## The decision rule

Own the architecture leaders, not a single-architecture bet. For pure-play exposure that means spreading across modalities — trapped ion, neutral atom — rather than concentrating. For architecture-agnostic exposure, large semiconductor positions you may already hold (IBM, Google) carry quantum optionality without single-modality risk. Avoid concentration in any one architecture until a convergence signal fires. And treat Microsoft's topological program as a science story to watch, not a position to hold — high upside, but not investable on current evidence.

## Further reading

- **Sophia Chen, *Science News* coverage of Microsoft's Majorana 1 (2025)** — accessible journalism that explains the topological claim and the expert skepticism around it in plain language, the best entry point for understanding why "not investable" is the right call.
- **Google Quantum AI team, "Quantum error correction below the surface code threshold," *Nature* (2024)** — independent peer-reviewed academic source documenting the Willow below-threshold result; the foundational evidence that error correction works.
- **QuEra et al., *Nature* (January 2026), the 96-logical-qubit demonstration** — the primary source for the neutral-atom milestone, showing logical qubits, below-threshold suppression, and universal operations in one system.
