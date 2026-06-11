# Chapter 6 — The Classical Counterattack Pattern

*How to read a quantum breakthrough before the correction arrives.*

In October 2019, Google published a paper in *Nature* claiming that its 53-qubit Sycamore processor had performed a computation that would take the world's best supercomputer approximately ten thousand years. The stock moved. The headlines ran. Physicists debated. And then, over the following years, the classical counterattack arrived — a sequence of improving algorithms and tensor-network methods that progressively eroded the ten-thousand-year estimate toward something measured in hours. The original result was not fraudulent. The hardware really did do what it did. But the gap between "what the quantum processor did" and "what the best classical method could match" turned out to be far smaller than the paper had implied, because the comparison had been made against a weak classical baseline, not the best one available.

Four years later, in 2023, IBM published its own headline result — a 127-qubit processor running quantum dynamics that the paper framed as "beyond brute-force classical methods." The counterattack arrived within *weeks*. Researchers at the Flatiron Institute reproduced IBM's results using a classical tensor-network method running on a laptop. Not approximate results. In some respects, *more accurate* results.

I am going to explain why this keeps happening, why it is structural rather than accidental, and what it tells you about how to evaluate the next announcement before you move money.

---

The first thing to understand is that three different bars get blurred into one in quantum computing announcements, and marketing has strong incentives to keep them blurred.

The lowest bar is *supremacy* — John Preskill's term for a quantum device performing *some* task, possibly contrived and useless, beyond any feasible classical computer. Google's 2019 claim was a supremacy claim. The task — sampling from a hard probability distribution — produced no useful output whatsoever. It was an engineered benchmark, designed to be hard for classical computers and easy for the specific quantum hardware. The output was uninterpretable noise from the perspective of anything you might want to compute.

The middle bar is *utility* — IBM's softer framing for useful computation at a scale where exact classical methods struggle, before full fault tolerance. IBM's 2023 claim was a utility claim. The dynamics it simulated were physically motivated — kicked-Ising models are real physics — but whether the results were genuinely beyond-classical depended entirely on which classical methods you compared against.

The highest bar is *commercial value* — a quantum computer solving a problem that matters economically, solving it better than any classical alternative, and doing so in a way that justifies the infrastructure cost. No claim to date has cleared this bar.

A press release that achieves the first bar will describe itself using the language of the third. The discipline you need is to read the words "beyond classical" and immediately ask: *beyond which classical methods, run by whom, with how much engineering effort?*

<!-- → [DIAGRAM: Three horizontal bars stacked vertically, labeled "Supremacy (any task, including contrived)" at bottom, "Utility (useful task, noisy hardware)" in middle, "Commercial value (economically relevant, cost-competitive)" at top. A large arrow on the left labeled "What is claimed" points to the top bar. A smaller arrow on the right labeled "What was demonstrated" points to the bottom or middle bar. Caption: "The three-bar problem. Announcements routinely use the language of the highest bar to describe results at the lowest. The investor's first move is to identify which bar was actually cleared."] -->

---

Now the structural reason the classical side keeps winning. This is the load-bearing idea, and I want to build it carefully because once you have it, the pattern stops being surprising.

Drop a stone into a still pond. The ripples spread outward from the impact point — locally, neighbor to neighbor. At any given moment, the part of the pond that is actively disturbed is the *front* of the ripple, not the whole pond. To describe the state of the water, you only have to track what is happening at the front. The interior, behind the front, has already settled; the exterior, ahead of it, has not yet been touched. The description stays manageable because the relevant boundary stays bounded.

Now imagine a pond where every drop of water is connected to every other drop simultaneously — where touching one drop instantaneously disturbs all of them with equal intensity, regardless of distance. There is no clean front to track. Everything is correlated with everything else at once. To describe that system you would need to track the whole thing simultaneously, and the cost explodes.

These two regimes are not just a metaphor. They correspond precisely to two mathematical regimes of quantum entanglement that determine whether a quantum system is classically simulable.

*Entanglement entropy* measures how strongly one region of qubits is correlated with the rest of the system. In the first regime — called an *area law* — the entanglement of a region grows with its boundary (its surface), not its total volume. This is characteristic of the ground states and short-time dynamics of local quantum systems on low-dimensional grids. Qubits interacting primarily with their immediate neighbors tend to obey it. In the second regime — a *volume law* — entanglement grows with the full interior of the region. This happens in highly connected, long-time-evolved, or otherwise scrambled quantum states.

Classical *tensor networks* are computational methods built specifically to exploit the first regime. An MPS (matrix product state) in one dimension, or a PEPS in two dimensions, can represent an area-law state with a cost controlled by a quantity called the *bond dimension* — and as long as entanglement stays in the area-law regime, the bond dimension stays bounded and the simulation stays tractable. When entanglement crosses into the volume-law regime, bond dimension explodes, tensor networks fail, and the quantum computer genuinely has no classical competition.

Here is the punchline: today's leading hardware — superconducting processors on flat two-dimensional chips — runs its benchmark problems on *local, low-dimensional lattices*. That geometry is exactly what tensor networks were designed to crush. The hardware's own physical layout hands the classical competitor the mathematical structure it knows how to exploit most efficiently.

This is not bad luck for quantum computing. It is not classical researchers finding clever tricks. It is the direct consequence of a hardware geometry that was optimized for qubit quality and control fidelity, not for entanglement complexity. The supremacy benchmarks were designed to be hard for *general-purpose* classical computers — and they are. They were not designed to be hard for *specialized* classical methods that exploit the specific geometry of the quantum hardware — and those methods keep winning.

<!-- → [DIAGRAM: Two panels side by side. Left panel: a 2D grid of qubits with arrows showing only nearest-neighbor interactions. Below it, a ripple diagram showing a bounded entanglement front spreading outward. Label: "Area-law regime — tensor networks tractable." Right panel: the same grid of qubits but with arrows connecting every qubit to every other qubit. Below it, a fully correlated, no-clear-front diagram. Label: "Volume-law regime — tensor networks fail." Caption: "Why today's superconducting hardware is classically simulable. The two-dimensional planar geometry produces local entanglement — exactly the structure classical tensor networks were built to exploit."] -->

---

The framework for evaluating any specific claim follows from this structure, and it reduces to three steps.

**Separate the bars.** Is this a supremacy claim (any task, useful or not), a utility claim (useful task, compared against a specific classical baseline), or something between? What was the baseline? Was it brute-force simulation, or the best available specialized method?

**Wait for the independent response.** The Flatiron Institute's Center for Computational Quantum Physics in New York is the most reliable independent group for this work. It is funded by the Simons Foundation, not by any hardware vendor, and it has no stake in the outcome. When the IBM utility result appeared in 2023, it was Flatiron researchers — Tindall, Fishman, Stoudenmire, and Sels — who produced the classical match within weeks (arXiv:2306.14887). When D-Wave's spin-glass result appeared in 2025, it was again Flatiron researchers, with collaborators at EPFL, who produced the fastest classical response (arXiv:2503.05693). A claim that Flatiron has not yet attempted to match is unverified, not vindicated.

**Apply the twelve-to-twenty-four-month window.** If a Flatiron-caliber group has attempted to match the claim and *failed* over that window, the claim earns credibility. If it falls in weeks, it was a weak baseline problem. If it falls in months, it was a moderately hard problem that the right classical method eventually solved. If it has not fallen in a year or more and the attempt has been serious, you have something worth examining more carefully.

<!-- → [TABLE: Four-column table — Claim, Hardware, Classical response time, Outcome. Rows: Google Sycamore random circuit sampling 2019 (superconducting, multi-year erosion, classically matched and eroded); IBM Eagle kicked-Ising 2023 (superconducting, weeks, matched by Flatiron tensor networks); D-Wave Advantage2 spin-glass 2025 (annealer, months — ongoing, partially matched, hardest instances unresolved as of mid-2026). Caption: "Three claims, three response patterns. The response time is itself information: faster collapse indicates the problem stayed firmly in the area-law regime; longer resistance suggests the dynamics approached or touched the volume-law boundary."] -->

---

Now I want to walk through each case in the detail it deserves, because the three together tell a richer story than the pattern alone.

**Google Sycamore, 2019.** The task was random circuit sampling: apply a random sequence of quantum gates to 53 qubits, then collect the resulting probability distribution over outputs. Google estimated that the best classical supercomputer would need roughly ten thousand years. This estimate compared against brute-force simulation — full state-vector simulation of 53 qubits, which requires storing $2^{53}$ complex numbers and scales catastrophically with qubit count.

The classical counterattack was not a single paper. It was a multi-year sequence of improvements. Researchers showed that tensor-network methods — not brute force — could exploit the two-dimensional planar structure of Sycamore's qubit layout and compress the simulation dramatically. Work on China's Sunway supercomputer, and subsequent algorithmic refinements, progressively reduced the effective classical cost. The robust conclusion is that the result was classically matched and eroded over several years; the exact numbers depend on which simulation method and which metric you use, so be cautious about citing a single dramatic figure [verify]. What the whole arc proved was that the "ten thousand years" claim rested on a strawman baseline, not the best available classical competition.

**IBM Eagle, 2023.** The 127-qubit Eagle processor ran kicked-Ising dynamics — a well-defined physical model where qubits are periodically kicked and the magnetization of the system evolves over time. IBM used an error-mitigation technique called probabilistic error cancellation to extract cleaner signals from noisy hardware, and compared the results against exact classical simulation (again, brute force) which fails at 127 qubits.

The Flatiron response used *belief-propagation tensor networks* — a method that exploits the structure of the specific dynamics rather than attempting full-state simulation. It reproduced IBM's observables, and in some parameter regimes produced more accurate values than the quantum device, within weeks of the *Nature* paper appearing. The dynamics had remained in a regime where entanglement stayed tractable — the kicked-Ising model on a two-dimensional grid, run for the circuit depths IBM tested, did not generate enough entanglement to defeat tensor-network compression. The classical method won because the problem never left the area-law pond.

One precision note: "on a laptop" is roughly accurate for the specific observables and circuit depths reported, but verify the exact hardware configuration before stating it flatly. The important point is not the specific hardware but the *speed* and *accessibility* of the classical match — an independent group reproduced a "utility" headline result in weeks, without a quantum computer.

**D-Wave Advantage2, 2025 — the unresolved case.** D-Wave's annealer simulated the real-time dynamics of disordered quantum spin glasses on various lattice geometries, with a claim that matching the largest, hardest instances classically would require roughly a million years on the Frontier supercomputer. In March 2025 — not May 2026, which you may see in some secondary sources — Tindall and colleagues at Flatiron, with collaborators at EPFL, published a classical response using belief-propagation tensor networks that matched certain lattice geometries and parameter regimes with modest computational resources (arXiv:2503.05693, later published in *Science*). D-Wave issued a formal response: "the quantum supremacy result stands." Their argument is that the Flatiron work matched only a subset of geometries and a subset of parameter regimes — the hard core of the demonstration, the largest and most disordered instances, remained unmatched.

This dispute is **[HYPOTHESIS — genuinely contested and unresolved as of mid-2026]**. Both sides have published. No consensus exists.

What I want you to notice is what this does *for* the framework rather than *against* it. A classical response that has been serious and sustained for more than a year and still has not closed the case is, by the chapter's own logic, a weak credibility signal in D-Wave's favor. That is what the framework predicts: if Flatiron tries and cannot fully match, over the twelve-to-twenty-four-month window, you are looking at something that might be real. The intellectually honest move is to say so clearly, not to declare victory for the classical side.

There is also a reason the spin-glass result resists longer than the IBM one did. Annealing dynamics of a disordered spin glass can push closer to the volume-law regime than IBM's confined kicked-Ising dynamics. The correlations in a disordered system spread less neatly across the lattice. The entanglement front is harder to track, the bond dimension grows faster, and tensor-network compression becomes more expensive — not necessarily infeasible, but harder. The response time is longer because the problem is genuinely harder for the classical side, which is exactly what you would predict from the entanglement structure argument. The lesson for an investor is the relationship between geometry and response time: the messier the entanglement, the longer the classical side takes, and the longer it takes without a clean match, the more seriously the claim deserves to be examined.

---

A result that would genuinely resist the classical counterattack would need four features, none of which any claim to date fully clears simultaneously.

First: an economically relevant problem, not a benchmark engineered for the hardware. Random circuit sampling was designed to be hard for general-purpose classical simulation and easy for the quantum device; that design is a red flag, not a feature.

Second: comparison against the *best* available classical methods, not a brute-force strawman. Any claim that does not name the specific classical methods it was compared against should be treated as unverified until the comparison is made explicit.

Third: volume-law entanglement on non-planar, high-connectivity graphs. This is the regime where tensor networks genuinely fail — where there is no clean boundary to track, no bounded bond dimension, no polynomial-cost classical approximation. Trapped-ion and neutral-atom architectures, which support higher-connectivity graphs, are better positioned to generate this regime than planar superconducting grids. A result from hardware capable of non-planar connectivity, on a problem that requires it, would be much harder for the classical side to match.

Fourth: a documented, *failed* attempt at classical replication by a Flatiron-caliber independent group, after a serious effort over twelve months or more.

The D-Wave case, as of mid-2026, has something like the fourth feature — the classical response has been sustained and has not fully closed — but it lacks the first. The problem is not economically relevant in its current form; it is a physics benchmark. What would a version of this test look like if it were? That is the question worth tracking.

<!-- → [INFOGRAPHIC: Checklist format. Title: "What a counterattack-resistant result looks like." Four items, each with a checkbox: (1) Economically relevant problem — not an engineered benchmark. (2) Compared against best available classical methods, explicitly named. (3) Non-planar, high-connectivity topology producing volume-law entanglement. (4) Independent Flatiron-caliber group attempted classical match and failed, over 12–24 months. Below the checklist, a status column for each of the three historical cases: Google Sycamore (0/4 — fails all), IBM Eagle (0/4 — fails all), D-Wave 2025 (partial credit on item 4, 0 on items 1–3). Caption: "No claim to date has cleared all four. Item 4 is the most important signal for an investor watching in real time."] -->

---

The sociological half of this pattern is worth naming explicitly, because it explains why the correction mechanism is slow even when it works.

Stuart Ritchie's *Science Fictions* documents a consistent dynamic across all of science: when a press release exaggerates a causal claim, news coverage is roughly twenty times more likely to repeat the exaggeration than to note the caveats. Positive results get amplified; corrections appear in specialist venues, cited by specialists, invisible to everyone else. The quantum computing version of this is unusually legible because the correction mechanism — a specific independent group, working with a specific class of methods, motivated by a clear physical argument — is unusually fast and public. But the asymmetry in amplification is exactly the same. Google's 2019 result became the founding myth of the quantum decade. The multi-year erosion of its claimed advantage is known to specialists and almost nobody else.

The practical implication: a peer-reviewed paper in *Nature* or *Science* does not settle a quantum-advantage claim. These journals published both the IBM utility claim and the Flatiron rebuttal. The publication is the beginning of the evaluation, not the end. An investor who acts on the initial publication and ignores the subsequent technical literature is not making an investment decision; they are making a PR decision.

---

## What Would Change My Mind

If a quantum device demonstrated genuine volume-law entanglement on a non-planar graph at a scale where classical tensor networks had been shown to fail — not expected to fail, but actually attempted and failed by an independent group — I would revise the framework substantially. The current pattern holds specifically because current hardware lives in a geometry that tensor networks exploit. New hardware architectures, particularly those with higher qubit connectivity and lower error rates on non-planar graphs, could exit that regime.

I would also revise if the classical simulation methods themselves hit a scaling wall — if the bond dimension required to match a growing class of experiments grows in a way that eventually defeats even the best tensor-network algorithms. That could happen. The boundary between what tensor networks can and cannot handle is an active research question, not a closed one.

## Still Puzzling

The entanglement entropy argument explains why the classical side wins on today's hardware. It does not explain exactly where the boundary is. At what circuit depth, connectivity, and qubit count does a superconducting processor exit the area-law regime and enter one that tensor networks genuinely cannot handle? That boundary has not been precisely mapped experimentally. The D-Wave spin-glass case may be probing it, but from a geometry — a disordered annealing problem — that is unusual enough to make generalization difficult. The most interesting experiment in near-term quantum computing might be one designed specifically to find and characterize that boundary, rather than to claim advantage on one side of it.

---

## Further Reading

- **Stuart Ritchie, *Science Fictions: How Fraud, Bias, Negligence, and Hype Undermine the Search for Truth* (2020).** The accessible account of why splashy claims outrun their corrections in all of science — the sociological grounding for why this pattern is structural rather than specific to quantum computing.
- **Joseph Tindall, Matthew Fishman, Miles Stoudenmire, Dries Sels, "Efficient tensor network simulation of IBM's Eagle kicked Ising experiment," arXiv:2306.14887 (2023).** The primary source for the IBM counterattack — clean, fast, and the best illustration of how the pattern works when the dynamics stay firmly in the area-law regime.
- **D-Wave Quantum Inc., the 2025 *Science* spin-glass paper, the Tindall et al. classical response (arXiv:2503.05693), and D-Wave's "Quantum Supremacy Result Stands" reply.** Read all three documents together to see the contest as it actually stands — the only currently unresolved case, and the one that may tell us most about where the real boundary lies.

---

*This handbook is a framework document, not financial advice. Company names are illustrative examples, not recommendations, and may age quickly.*
