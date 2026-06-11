# Chapter 6 — The Classical Counterattack Pattern

## Decision question

A quantum company has just announced a breakthrough — a result "beyond classical," a task that would take a supercomputer thousands of years, a new milestone in *Nature* or *Science*. The stock is moving. Should you act on the announcement, and if not, what should you wait for?

## The short answer

Wait twelve to twenty-four months, and apply the Flatiron test. Nearly every major "quantum advantage" claim to date has been classically matched or substantially eroded within that window — Google's 2019 result over a few years, IBM's 2023 result within weeks. This is not bad luck or sour grapes from classical computer scientists. It is structural: today's leading hardware runs problems on geometries that classical methods called tensor networks are purpose-built to exploit. The one current case that is genuinely *unresolved* — D-Wave's 2025 spin-glass result — is the exception that proves how to read the pattern, not a refutation of it.

## Why this matters

The single most expensive mistake an investor can make in this sector is to trade on a breakthrough headline. The headlines are engineered — not necessarily dishonestly, but in a system whose incentives reward the splashy positive claim and barely reward the quiet correction. Stuart Ritchie's *Science Fictions* documents this dynamic across all of science: when a press release exaggerates a causal claim, news coverage is roughly twenty times more likely to repeat the exaggeration; positive results get published and amplified while the walk-backs disappear into specialist venues. The classical counterattack pattern in quantum computing is a specific instance of this general hype dynamic — except that here, unlike in much of science, there is a fast, independent, and physically motivated correction mechanism. The discipline is simply to wait for it before you move money.

If you internalize one thing from this chapter, make it this: a peer-reviewed paper in *Nature* or *Science* does not settle a quantum-advantage claim. These claims are routinely rebutted *in the same journals* within months. The publication is the beginning of the evaluation, not the end.

## The framework

**First, separate three bars that marketing blurs together.** "Quantum supremacy" (John Preskill's term) means a quantum device performs *some* task — possibly contrived and useless — beyond any feasible classical computer. "Quantum utility" (IBM's softer framing) means *useful* computation at a scale where exact classical methods struggle, even before full fault tolerance. Neither is the same as *commercial value*. Google's 2019 task produced no useful output whatsoever; it sampled from a hard probability distribution and nothing more. Supremacy, utility, and commercial value are three different bars, and a claim that clears the lowest one is often sold as if it cleared the highest.

**Second, understand the structural reason the classical side keeps winning: entanglement geometry.** This is the load-bearing idea, so I will build it carefully.

Entanglement entropy measures how strongly one region of qubits is correlated with the rest. There are two regimes. Under an *area law*, the entanglement of a region grows with its *boundary* — its surface — not its total size. This is typical of the ground states and short-time behavior of *local* systems on low-dimensional grids. Under a *volume law*, entanglement grows with the region's whole *volume*; this happens in highly entangled, long-time, or high-connectivity states.

Now the pond. Drop a stone into a still pond — that is a local interaction, like one qubit nudging its neighbor. Ripples spread outward, but they spread *locally*, neighbor to neighbor. To describe the state of the pond, a classical method only has to track the ripple *front* — the boundary — not every drop of water at once. That is cheap. This is exactly what classical *tensor networks* (called MPS in one dimension, PEPS in two) are built to do: they represent area-law states efficiently, with a cost controlled by a quantity called the bond dimension that stays bounded as long as entanglement obeys an area law. Now imagine a pond where every drop is connected to every other drop at once — an all-to-all, non-planar pond. There is no clean ripple front to track. The bond dimension explodes, and tensor networks fail. That is volume-law entanglement.

The punchline: today's leading hardware — superconducting processors laid out on flat two-dimensional grids, and near-term annealers — runs problems on *local, low-dimensional lattices* that tend to obey, or only mildly violate, the area law. That is precisely the regime tensor networks were designed to crush. So the classical counterattack is not a lucky accident. The hardware's own geometry hands the classical competitor exactly the structure it knows how to exploit.

One honest caveat: this argument is asymptotic. At the 50-to-300-qubit scale of current supremacy claims, it is a strong heuristic, not a theorem — which is *why* some claims fall in weeks and others resist for years.

**Third, the Flatiron test.** The Flatiron Institute's Center for Computational Quantum Physics (in New York, funded by the Simons Foundation) is a leading independent group in the classical simulation of quantum systems. Crucially, it is not a hardware vendor — it has no stake in inflating quantum claims, and it repeatedly produces the classical method that matches a "beyond-classical" result. Hence the test: if Flatiron (or an equivalent independent group) has not tried to match a claim, the claim is unverified. If they have tried and *failed* over twelve to twenty-four months, the claim earns credibility.

## What it looks like in practice

Three cases, in order.

**Google Sycamore (2019).** A 53-qubit superconducting processor performed random circuit sampling and Google claimed the result would take the best classical supercomputer roughly 10,000 years. The classical counterattack arrived not as a single knockout but as a multi-year sequence of improving tensor-network and algorithmic results from 2021 onward, including work on China's Sunway supercomputer that reproduced the sampling task. Over 2021–2025 the "10,000 years" estimate collapsed toward hours and less on classical hardware. Resist quoting a single dramatic figure like "17 minutes" — the exact number depends on which simulation and which metric, so the robust statement is "classically matched and eroded over several years" rather than one clean headline [verify]. What it proved: an engineered sampling benchmark whose original gap rested on a weak classical baseline.

**IBM "utility" (2023).** A 127-qubit Eagle processor ran kicked-Ising dynamics with error mitigation, published as "Evidence for the utility of quantum computing before fault tolerance" (*Nature*, 2023), framed as beyond brute-force classical methods. The counterattack came within *weeks*: Tindall, Fishman, Stoudenmire, and Sels at Flatiron used belief-propagation-contracted tensor networks to reproduce the observables — and in places more accurately than the quantum device (arXiv:2306.14887, 2023). The "on a laptop" shorthand you may see is roughly true for the specific observables, but verify the exact hardware before stating it flatly. What it proved: the dynamics stayed in a low-entanglement, area-law-friendly regime, so tensor networks won fast.

**D-Wave magnetic materials (2025) — the contested case.** D-Wave's Advantage2 annealer simulated the real-time dynamics of disordered quantum spin glasses on various lattices, published in *Science*, with a claim that matching the largest systems classically would take on the order of a million years on the Frontier supercomputer. The classical response appeared in the *same window* — March 2025, not the "May 2026" you may see in some summaries, which is simply wrong. Tindall and colleagues at Flatiron, with collaborators at EPFL, used belief-propagation tensor networks to reach state-of-the-art accuracy on systems of several hundred qubits with modest resources (arXiv:2503.05693, March 2025, later in *Science*).

Here is where honesty matters most. This dispute is **[contested — see pantry flag] and unresolved as of mid-2026.** The classical work matched only a *subset* of lattice geometries and parameter regimes; the hardest, largest instances and the full scope of the demonstration were not cleanly reproduced. D-Wave issued a formal response — "the quantum supremacy result stands" — arguing that the classical work is a partial, isolated advance rather than a holistic replication, and that the million-year figure holds for the instances that were not matched. Both sides have published. There is no consensus classical refutation of the full dataset.

Notice what this does to the framework rather than to it. A classical response that takes more than twelve months and still has not fully landed is, by the chapter's own logic, a *weak credibility signal in D-Wave's favor* — exactly the thing the framework tells you to wait for. The intellectually honest move is to say so, not to declare victory for the classical side. The D-Wave case is the live edge of the contest, and it remains open.

There is also a reason the spin-glass result resists longer than the IBM one did, and it is worth understanding. Annealing dynamics of a disordered system can push closer to the volume-law regime than IBM's confined kicked-Ising dynamics did — the correlations spread less neatly, so the classical front is harder to track. That does not make D-Wave's claim correct; it makes it a harder target, which is why the response time is measured in more than a year rather than weeks. The lesson for an investor is the relationship between geometry and response time: the messier the entanglement, the longer the classical side takes, and the longer it takes, the more seriously the claim deserves to be taken — *up to the point* where the hardest instances are actually matched. Until that point arrives, the verdict is open, not decided.

**What a counterattack-*resistant* result would look like.** Four features, none of which any claim to date fully clears: (1) an economically relevant problem, not a benchmark engineered for the hardware; (2) comparison against the *best* available classical methods, not a brute-force strawman; (3) volume-law entanglement on non-planar, high-connectivity graphs — feasible on trapped-ion and neutral-atom machines, very hard on planar superconducting grids; and (4) a documented, *failed* attempt at classical replication by an independent group of Flatiron's caliber.

## What to watch for

- Results where the independent classical response takes longer than twelve months — and especially results on non-planar, high-connectivity topologies that defeat tensor-network compression.
- Independent academic replication with *no vendor involvement*. A result confirmed by people with nothing to sell is worth far more than one confirmed by the seller.
- The eventual resolution of the D-Wave dispute, either way. A clean classical match of the hardest instances would close it; a sustained failure to match them would be the first real crack in the pattern.

## What to ignore

- "Beyond classical" claims that do not name the *specific* classical methods they were compared against. If the baseline is unnamed, assume it is a strawman.
- Claims of volume-law entanglement from planar superconducting grids. The architecture makes that physically implausible; the geometry is wrong for it.
- Any benchmark where the problem was clearly designed around the quantum hardware rather than the hardware being tested against a pre-existing, independently motivated problem.
- The publication venue as proof. *Nature* and *Science* publish these claims *and* their rebuttals; the journal name settles nothing.

## The decision rule

Do not trade on a quantum breakthrough announcement; wait for the independent classical response, and treat a claim as credible only if a Flatiron-caliber group has tried to match it and failed over twelve to twenty-four months.

## Further reading

- **Stuart Ritchie, *Science Fictions: How Fraud, Bias, Negligence, and Hype Undermine the Search for Truth* (2020).** The accessible account of why splashy claims outrun their corrections across all of science — the sociological half of why this pattern recurs, and the case for "organized skepticism" as the investor's stance.
- **Joseph Tindall, Matthew Fishman, Miles Stoudenmire, Dries Sels, "Efficient tensor network simulation of IBM's Eagle kicked Ising experiment," arXiv:2306.14887 (2023).** The independent academic counterattack that matched IBM's 2023 "utility" claim within weeks — the cleanest illustration of the pattern.
- **D-Wave Quantum Inc., the 2025 *Science* spin-glass paper and its companion "Quantum Supremacy Result Stands" response (with the rebutting classical work, Tindall et al., arXiv:2503.05693).** The primary sources for the one genuinely unresolved case — read both sides to see the contest as it actually stands.
