# Research Notes: Chapter 03 — The Big Compute, Small Data Filter
**Source:** TIKTOC.md chapter entry
**Notes file:** 03-the-big-compute-small-data-filter_notes.md
**Corresponding chapter:** chapters/03-the-big-compute-small-data-filter.md (not yet written)
**Generated:** 2026-06-10

---
## Chapter summary (from TIKTOC.md)
A heuristic for evaluating quantum *application* claims via three questions: (1) Can the problem be specified **compactly** — a few parameters, not a big dataset? (2) Does solving it require exploring an **exponentially large space**? (3) Is the useful output a **small classical result**? **Passes:** molecular simulation, integer factoring, quantum phase estimation for chemistry. **Fails:** LLM training, database search, supply-chain/logistics optimization, financial time-series. **Key concepts:** the state-preparation problem, the I/O bottleneck, and why data-loading kills most claimed speedups. **Research targets:** the I/O / state-preparation bottleneck literature, real vs invented application claims, Aaronson on the topic.

---
## A. Conceptual foundations

### The filter itself: big compute, small data
The chapter's core tool is a three-part screen that an investor can run on any "quantum will revolutionize X" claim *without* a physics degree. The pattern that quantum computers genuinely accelerate is: a problem described by a *small* number of parameters (small *in*), whose answer requires searching or simulating an *exponentially large* space of possibilities (*big compute*), and whose useful answer is *small* (small *out*). The reason this exact shape matters is the I/O bottleneck (below): if either the input or the output is large, the cost of moving classical data in and out of the quantum state swamps any speedup the quantum core might have provided. The slogan: quantum is for problems with a *small mouth and a huge stomach*.

**Common misconception:** "Quantum computers are great at anything involving lots of data." The opposite is closer to true — *lots of data* is usually disqualifying, because loading it dominates the runtime.
**Worked example:** Factoring a 2,048-bit RSA key: the input (the number) is a few thousand bits — tiny; the search space (its factors) is astronomically large; the output (two primes) is tiny. Textbook pass.
**Source(s):** Scott Aaronson, *Quantum Machine Learning Algorithms: Read the Fine Print* (https://www.scottaaronson.com/papers/qml.pdf); Aaronson, *Quantum Computing: Between Hope and Hype* (https://scottaaronson.blog/?p=8329)

### The I/O bottleneck (the input half)
A quantum computer's exponential edge is in *manipulating* a state, not in *building* it. To act on classical data you must first encode it into a quantum state — *state preparation*. Aaronson's "fine print": if preparing the state takes time proportional to the data size N (or worse), then the exponential speedup is gone *in the very first step*. A basic information-theoretic bound says the circuit that prepares an arbitrary N-entry state needs on the order of N gates — so no exponential advantage in preparation is even possible for generic data. Proposed shortcuts (QRAM — quantum RAM) assume hardware that can serve data in superposition in logarithmic time, but building large, fault-tolerant QRAM is itself an unsolved, costly problem; the speedup is *conditional on the access model*, and that condition usually isn't met for real classical datasets.

**Common misconception:** "We'll just load the dataset into the quantum computer." Loading is the expensive part; for big data it can cost more than the classical computation you were trying to beat.
**Worked example:** A quantum linear-algebra routine (HHL-style) advertised as exponentially fast for solving Ax=b assumes you can *already* load A and b into states cheaply and *read out* only a summary statistic. Drop either assumption — which real data forces you to — and the exponential speedup collapses.
**Source(s):** Aaronson, *Read the Fine Print* (link above); Aaronson on the "imminent" debate (https://scottaaronson.blog/?p=9425)

### The readout bottleneck (the output half)
Symmetrically, even a perfect quantum computation gives you a *quantum state*, and you can only learn about it by *measuring* — which yields a few classical bits per run and collapses the state. To read out an N-dimensional answer you generally need ~N measurements (and repetitions), which destroys any exponential speedup if the *useful answer is large*. This is why the third filter question insists the output be small: a single number (a molecule's ground-state energy), a yes/no, a short factor — fine. A reconstructed N-pixel image, a full probability distribution, a trained model's weights — not fine.

**Common misconception:** "The quantum computer finds the answer instantly." It finds a *state* that encodes the answer; extracting a large answer from that state is itself an N-scale (or √N, for Grover) cost.
**Worked example:** Grover search gives a quadratic (√N) speedup for unstructured search, but reading out a specific found item still costs ~√N — useful, never exponential, and beaten by classical I/O for genuine database lookups.
**Source(s):** Aaronson, *Read the Fine Print*; Wikipedia/standard treatment of measurement and Holevo bound (referenced via Aaronson lecture notes, https://www.scottaaronson.com/qisii.pdf)

### Why advantage is problem-specific (the BQP/BPP root)
The filter is the practical face of the complexity-theory fact from Chapter 2: only a structured minority of problems sit in the believed gap between BQP and BPP. The three questions are a field-usable proxy for "does this problem have the structure that lets quantum interference help, *and* is it free of the I/O penalties that erase the gain?" Problems pass when the hardness is *intrinsic computational/simulation hardness* (exploring an exponential Hilbert space), and fail when the hardness is really *data movement* dressed up as computation.

**Common misconception:** that a hard, important, expensive problem is therefore a quantum problem. Importance and classical difficulty are irrelevant; only the *shape* (small-in, big-compute, small-out, right structure) qualifies it.
**Worked example:** Simulating a catalyst molecule's electronic structure is intrinsically quantum-hard (electrons live in an exponential space) — passes. Optimizing a delivery fleet is hard but is *data-heavy combinatorial optimization* with large inputs and outputs — fails the I/O test despite being valuable.
**Source(s):** Aaronson, *How Much Structure Is Needed for Huge Quantum Speedups?* (https://www.scottaaronson.com/papers/aarsolvay.pdf); "Disentangling Hype from Practicality: On Realistically Achieving Quantum Advantage" (https://arxiv.org/abs/2307.00523)

---
## B. Domain examples and cases

### Pass — Case 1: Molecular / quantum-chemistry simulation
Electrons in a molecule occupy a state space that grows exponentially with the number of electrons — exactly what classical computers struggle to simulate and what quantum computers were conceived (Feynman, 1981) to do. The input (a molecular Hamiltonian) is compact; the useful output (a ground-state energy, a binding affinity) is a single number. *Quantum phase estimation (QPE)* extracts that energy at polynomial cost in system size, an exponential improvement over exact classical methods. This is the application most forecasters (BCG, McKinsey) expect to mature first. Recent work combined QPE with *logical* qubits for molecular energy calculations — a milestone toward chemistry advantage.
**Source(s):** Phys. Rev. X, *Fast Quantum Simulation of Electronic Structure* (https://journals.aps.org/prx/abstract/10.1103/pb2g-j9cw); arXiv workflow paper on QPE for benzene (https://arxiv.org/pdf/2312.16375)

### Pass — Case 2: Integer factoring (Shor) and quantum phase estimation
Factoring is the canonical small-in/big-compute/small-out problem and the clearest BQP-outside-BPP example. QPE (the same primitive behind chemistry) is the engine. The output — the prime factors — is tiny. Caveat for honesty: cryptographically relevant factoring needs *millions* of high-quality physical qubits and deep fault tolerance, so this "pass" is a pass on *structure*, not on *near-term feasibility*.

### Fail — Case 1: LLM training and database search
LLM training is the archetypal big-data/big-output problem: terabytes of input, billions of output parameters. Both I/O bottlenecks fire at once — there is no proposed route to load the corpus or read out the weights without paying N-scale costs. Database/unstructured search likewise: Aaronson notes any problem "limited by accessing classical data... will be solved faster by classical computers." Grover's √N is the best on offer and is dominated by classical I/O in practice.

### Fail — Case 2: Supply-chain / logistics optimization and financial time-series
These are the most over-claimed "quantum advantage" applications. They have large data inputs (every route, SKU, price tick), often large outputs (a full schedule), and no proven exponential quantum speedup — the hardness is combinatorial and data-bound, not Hilbert-space-bound. Quantum/quantum-inspired heuristics may give modest gains, but the breathless "quantum will optimize the global supply chain" claim fails all three filter questions. Aaronson explicitly warns against the popular belief that quantum computers "will exponentially speed up every problem in optimization and machine learning and finance."
**Source(s):** Aaronson, *Read the Fine Print*; *Disentangling Hype from Practicality* (arXiv:2307.00523)

---
## C. Connections and dependencies
**Prerequisites:** Chapter 2's BQP-vs-BPP idea ("advantage is problem-specific") and the superposition/measurement mechanics that make I/O costly. Chapter 1's Layer 2 ("does it translate to commercial advantage?") — this filter *is* the Layer-2 tool.
**Unlocks:** The pass/fail verdicts feed the application-thesis chapters (the book's later treatments of molecular simulation as the most credible near-term use case, and the dismissal of LLM/logistics quantum claims).
**Adjacent chapter connections:** Chapter 2 (vocabulary/complexity foundation) ← → later chapters on specific application theses (chemistry good, LLM-training bad).

---
## D. Current state of the field
**Settled:** State-preparation and readout bottlenecks are well-established, peer-reviewed limits — not contrarian opinions. Chemistry/materials simulation is the consensus best-fit application; data-heavy optimization/ML are consensus poor fits for *exponential* speedup.
**Contested or emerging:** Whether QRAM can ever be built at fault-tolerant scale (would loosen the input bottleneck for some ML claims); whether *heuristic* (non-exponential) speedups in optimization are commercially meaningful even without provable advantage; exact qubit/runtime thresholds for chemistry advantage.
**Key references:**
1. Scott Aaronson, *Quantum Machine Learning Algorithms: Read the Fine Print* — the foundational statement of the I/O / state-prep critique; essential.
2. *Disentangling Hype from Practicality: On Realistically Achieving Quantum Advantage* (arXiv:2307.00523) — survey mapping which applications can realistically clear the bar.
3. Aaronson, *How Much Structure Is Needed for Huge Quantum Speedups?* (Solvay) — the structure-vs-speedup principle behind the filter.
4. QPE-for-chemistry papers (PRX 2026; arXiv:2312.16375) — concrete "pass" cases with real numbers.
**Recent developments (last 3 years):** First combination of QPE with logical qubits for molecular energies; continued QRAM proposals (incl. reported Chinese QRAM advances) that remain far from fault-tolerant scale; growing arXiv literature explicitly "disentangling hype from practicality" (2023–2026).

---
## E. Teaching considerations
**Where readers get stuck:** The counterintuitive core — that *more data hurts*. Readers' instinct (from the AI era) is "big data → big opportunity"; this chapter must invert that instinct for quantum specifically.
**Analogies that work:** The "small mouth, huge stomach" image. Or a *genius locked in a soundproof room* — brilliant at any puzzle you can whisper through the keyhole and whose answer is a single word, useless if you must shove an encyclopedia in and pull a library out. Or "the speedup is in the *thinking*, not the *reading and writing*."
**Exercises that build the skill:** Give 8–10 real and invented application claims; have students run the three questions and verdict each. Have them locate, in a vendor white paper, the (usually buried) assumption about how data gets loaded — Aaronson's "fine print."

---
## F. Library files relevant to this chapter
- `_lib_physics-quantum-physics-for-beginners-into-the-light-...md` — indirect: its treatment of measurement/collapse (Copenhagen interpretation, Heisenberg uncertainty) is the physics root of the *readout* bottleneck — you only get one classical outcome per measurement. Use lightly; the file is pop-science and does not address algorithms or I/O.
- `_lib_physics-the-physics-of-wall-street-...md` — tangential; could supply cautionary framing for the financial-time-series *failure* case (a domain with a long history of overconfident physics-style modeling).

---
## G. Gaps and flags
- FLAG: The factoring "pass" is structural, not practical — always pair it with the millions-of-qubits caveat so readers don't infer near-term RSA-breaking.
- FLAG: "Quantum is useless for all optimization" would overstate the case. The honest claim is "no *proven exponential* advantage for data-heavy optimization/finance"; modest heuristic gains are an open, contested question. Keep the filter about *exponential* speedup.
- GAP: A clean, citable single source that states the three filter questions in exactly this form was not found — the heuristic appears to be the book's own synthesis of Aaronson's I/O critique plus the BQP/BPP structure argument. Present it as the author's framework, supported by (not lifted from) the cited literature.
