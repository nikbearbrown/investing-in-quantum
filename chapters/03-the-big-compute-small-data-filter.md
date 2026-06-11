# Chapter 3 — The Big Compute, Small Data Filter

*Why the shape of a problem matters more than its importance.*

Here is a thought experiment I want you to sit with for a moment before we talk about quantum computers at all.

Imagine a genius locked in a soundproof room. She can solve any puzzle you can whisper through the keyhole in the door. Whatever she works out, she whispers back — a single word, a number, a short answer. For problems of that shape, she is unbeatable. She works faster than any team you could assemble outside the room, by a margin so large it is almost meaningless to compare.

Now suppose the puzzle requires you to first shove an encyclopedia through the keyhole. Then, once she has solved it, you need to extract a full library of answers back through it. What happens? The genius is the same genius. She is thinking just as brilliantly in there. But you are no longer waiting on her thinking. You are waiting on the keyhole. And the keyhole does not care how smart she is.

The genius is a quantum processor. The keyhole is the classical-quantum interface — the bottleneck for getting data in and answers out. The puzzles she is wasted on are the data-heavy ones. Every failure case I am going to show you in this chapter is, at bottom, a story about the keyhole.

---

The reason this matters for investors is that the instinct everyone brings from the AI era is precisely backwards for quantum. In AI, big data meant big opportunity. More data meant better models, and the companies that could accumulate and process the most data held the structural advantage. Quantum computing inverts that instinct completely.

A quantum company will name a large, expensive, important problem — optimizing a global supply chain, or training the next generation of language models, or pricing a derivatives book. The importance of the problem is presented as evidence that quantum will solve it. But importance and classical difficulty are irrelevant to whether a problem is a *quantum* problem. What matters is the shape of the problem — specifically, whether it has a small mouth, a huge stomach, and a small exit. Most large, data-heavy problems have exactly the wrong shape, and this is a structural fact that no improvement in qubit quality, coherence time, or error correction will ever fix.

The filter I want to give you is three questions you can run on any quantum application claim before you open the financials. I will explain why each question matters, show you what passing and failing look like, and teach you where to look in a vendor's own materials for the assumption that makes the speedup disappear.

---

## The Filter

**Question 1: Can the problem instance be described compactly?**

Not solved compactly. Described compactly. The *input* to the computation. A few parameters, not a large dataset.

Here is why this matters. A quantum computer's exponential edge lives in its ability to *manipulate* a quantum state — to propagate interference across a superposition of exponentially many possibilities simultaneously. What it cannot do, without paying a full price, is *build* that quantum state from classical data in the first place.

That step is called state preparation, and it has a basic information-theoretic floor: preparing an arbitrary quantum state with *N* entries takes on the order of *N* operations [verify]. So if your problem requires loading a large dataset, the exponential speedup is gone in the very first step. You spent it on loading. The quantum computation that follows may be brilliant, but it is working on a state you just took *N* steps to construct, and *N* steps is exactly what a classical computer charges for the same information. The quantum computer has not yet done anything that distinguishes it.

Scott Aaronson, who is both one of the field's leading theorists and its most reliable reality-checker, made this point in a Nature Physics piece titled "Read the Fine Print." His formulation is worth sitting with: any problem "limited by accessing classical data" will be solved faster by classical computers. The quantum part of the speedup assumes the data is already there, in quantum form, waiting to be processed. For real classical datasets — price histories, logistics tables, training corpora — that assumption is not met.

A proposed escape hatch exists. It is called *QRAM*, a hypothetical quantum memory that could serve data in superposition in logarithmic time rather than linear time. If QRAM existed at fault-tolerant scale, it would reopen the door for some data-heavy applications. But building large, fault-tolerant QRAM is itself an unsolved and costly engineering problem — the speedups that assume it are conditional on a condition that is not yet achievable, and may never be achievable at the scale the applications require [contested — the question of whether fault-tolerant QRAM is buildable in principle or just infeasible in practice is genuinely open in the literature].

<!-- → [DIAGRAM: Two-column visual contrasting a compact input (a molecular formula, a large integer) on the left with a large input (a dataset of price ticks, a training corpus) on the right. The compact input passes through a narrow "state preparation" gate cheaply; the large input clogs it. Caption: "The state preparation bottleneck. The quantum speedup lives inside the processor, not in the loading step — but the loading step charges N operations for N data points, erasing the advantage before computation begins."] -->

**Question 2: Does solving it require exploring an exponentially large space?**

This is the only place a quantum computer earns its keep — the *big compute* in the middle. The hardness must be intrinsic computational or simulation hardness, meaning the problem genuinely requires traversing an exponentially large space of possibilities or quantum states. It cannot be data-movement hardness dressed up to look like computation.

Sorting a large list is hard classically because there is a lot of data. That is data hardness. Factoring a thousand-digit number is hard classically because the space of candidate factors is astronomically large even though the input is small. That is computational hardness. Simulating the electrons in a complex molecule is hard classically because the quantum state of many interacting electrons occupies a Hilbert space that grows exponentially with the number of electrons — this is the problem Richard Feynman had in mind when he proposed quantum computers in 1981, and it remains the cleanest example of a problem with the right shape.

The distinction is subtle but decisive. Data hardness does not respond to quantum parallelism. Computational hardness — the kind that emerges from an exponentially large space of states or configurations to explore — is exactly what quantum interference and superposition are designed to exploit.

**Question 3: Is the useful output small?**

Even a perfect quantum computation leaves you holding a quantum state, and the only way to learn the contents of a quantum state is to measure it. Each measurement yields a few classical bits and collapses the state. To read out an *N*-dimensional answer you generally need on the order of *N* measurements and repetitions — which means if the *answer* is large, the readout cost swamps whatever was gained in the computation [verify].

This is the exit side of the keyhole. A single number — a molecule's ground-state energy, a binding affinity, the two prime factors of a large integer — can exit the room without difficulty. A reconstructed image, a full probability distribution, a set of trained neural-network weights — these cannot, not without paying the full *N* cost that wipes out the exponential advantage.

A problem passes the filter only if it clears all three: small in, big compute, small out. Fail any one, and the application thesis is structurally weak regardless of the hardware generation.

---

## What Passes

**Integer factoring.** The input — a thousand-digit number — is a few kilobits. The space of candidate factors is astronomical. The output — two primes — is tiny. Shor's algorithm exploits a deep connection between the period of a modular function and the prime factorization of the input, running in polynomial time on a quantum computer versus sub-exponential time on the best classical algorithms. A textbook pass on all three questions.

One honesty caveat: cracking cryptographically relevant RSA keys requires millions of high-quality *logical* qubits, which in turn require hundreds of millions to perhaps billions of physical qubits with today's error rates. This is a pass on shape, not a near-term capability. Do not infer that RSA encryption is about to break.

**Molecular and quantum-chemistry simulation.** The electrons in a molecule are quantum objects. Their joint state is a superposition across all possible configurations, and the size of that superposition — the Hilbert space — grows exponentially with electron count. Classical computers approximate this, and approximation breaks down badly for transition metals, strongly correlated systems, and large active spaces. A quantum computer can represent and evolve the actual quantum state directly, without approximation.

The useful output is compact: a ground-state energy, a reaction rate, a binding affinity. The algorithm *quantum phase estimation* (QPE) extracts that energy at a cost that grows only polynomially with system size. Recent work has demonstrated QPE applied to actual molecular calculations on logical qubits — not just toy demonstrations, but computations with stated active-space sizes and accuracy targets competitive with classical benchmarks ([Phys. Rev. X, 2026](https://journals.aps.org/prx/abstract/10.1103/pb2g-j9cw); [arXiv:2312.16375](https://arxiv.org/pdf/2312.16375)). This is the application most independent forecasters expect to mature first, and the reason the most credible quantum companies have quietly narrowed their roadmaps to chemistry and materials.

<!-- → [TABLE: Three-column table — Application, Filter verdict (Pass/Fail), Killing question (N/A or Q1/Q2/Q3). Rows: integer factoring (Pass), molecular simulation (Pass), LLM training (Fail — Q1 and Q3), unstructured database search (Fail — Q1, Grover speedup only quadratic), supply-chain optimization (Fail — Q1 and Q3), financial time-series analysis (Fail — Q1). Caption: "The filter applied to six common quantum application claims. 'Killing question' names the first of the three questions that eliminates the exponential advantage."] -->

---

## What Fails

**LLM training.** Killed by Questions 1 and 3 simultaneously. The input is a training corpus: hundreds of billions of tokens, terabytes of text. The output is a set of model weights: billions of floating-point parameters. Both I/O bottlenecks fire at once. There is no proposed mechanism to load the corpus or read out the weights without paying full *N*-scale costs, and *N* is very large. This is not a timing problem. The hardware will not fix it. The thesis is structurally incoherent.

**Unstructured database search.** Killed by Question 1. Aaronson's point applies directly: any problem limited by accessing classical data will be solved faster by classical computers. Grover's algorithm offers a quadratic speedup — searching *N* items in √*N* time rather than *N* — but this is not exponential, and reading out the found item still costs roughly √*N* quantum operations. For real lookups against real databases, classical I/O infrastructure is so optimized that a quadratic quantum advantage, even in principle, is unlikely to win. This is among the most frequently cited quantum applications and among the weakest.

**Supply-chain and logistics optimization.** Killed by Questions 1 and 3. Every route, constraint, SKU count, and delivery window is input data. A complete operational schedule is large output. The hardness here is combinatorial and data-bound, not Hilbert-space-bound. There is no known exponential quantum speedup for general combinatorial optimization, and the data volume on both ends ensures the keyhole problem is severe. This is perhaps the most over-claimed category of quantum applications.

**Financial time-series analysis.** Killed by Question 1. The inputs are large — every price tick, order flow record, and macro indicator a fund would want to condition on. No proven exponential speedup exists for the analysis of classical time series, and the hardness lives in the data, not in an exponential state space that quantum interference could exploit.

A fair caveat before moving on: "quantum is useless for all optimization" goes too far. The honest claim is that there is *no proven exponential* advantage for data-heavy optimization, machine learning, or finance. Modest heuristic gains — improvements that are real but not exponential — remain an open and contested question for certain structured optimization problems [contested — see also the QAOA literature]. The filter is specifically calibrated to exponential advantage, which is what the breathless claims promise and what justifies the valuations attached to them.

---

## Finding the Hidden Assumption

The real skill in applying this filter is learning to locate the buried assumption in a vendor's own materials. It is almost always there, and it is almost always in the appendix.

Look for sentences that say the data is "assumed to already be encoded" in a quantum state, or that the analysis "assumes access to a QRAM oracle," or that the speedup holds "given efficient state preparation." These phrases are the fine print Aaronson warned about. They are not admissions of failure — they are technically accurate statements of the conditions under which the speedup holds. But those conditions are almost never met for the applications being pitched, and the gap between the condition and the real world is where the exponential advantage quietly lives and quietly dies.

When you find that sentence, you have found the point where the genius's room got sealed. Everything before it in the pitch is real. Everything after it is conditional on a keyhole that does not exist yet.

<!-- → [DIAGRAM: Annotated mock excerpt of a quantum white paper. Three sentences highlighted in sequence: (1) an introductory claim of exponential speedup; (2) a middle section describing the algorithm; (3) a footnote or appendix sentence that reads "assuming efficient QRAM access" or similar. Arrows pointing to the third sentence labeled "This is where the speedup lives." Caption: "How to read a quantum white paper. The speedup claim is usually real given the assumption. The assumption is usually unmet for real classical data."] -->

---

## What This Looks Like in Practice

Before reading any quantum company's investor materials, run its headline application through the three questions. Can the problem instance be described by a handful of parameters, not a large dataset? Does solving it require traversing an exponentially large computational or state space? Is the useful answer small — a number, a decision, a short result?

Most claimed applications fail Question 1. A few that pass Question 1 fail Question 3. The ones that pass all three — molecular simulation, certain cryptographic problems, specific combinatorial structures with compact input — are the ones worth taking seriously.

What should catch your attention as genuinely promising: application claims that name specific problem classes rather than broad sectors. "Transition-metal catalysis" rather than "quantum will transform pharma." "Nitrogen fixation reaction pathway" rather than "quantum drug discovery." Specificity suggests someone ran the filter internally. Benchmarks against real classical baselines — density functional theory, coupled-cluster methods — on named molecules with stated active-space sizes and accuracy targets. Companies that have quietly narrowed their roadmaps from "quantum AI" toward quantum chemistry or materials simulation; that pivot is a signal they understand their own hardware's constraints.

What deserves skepticism: any quantum application claim built on large datasets. Recommendation systems, quantum big data, logistics optimization promising exponential speedups, financial analytics that require ingesting tick data or market microstructure. Chemistry demonstrations on hydrogen or lithium hydride — H₂ and LiH are textbook molecules that classical methods handle trivially; such demonstrations are proof-of-concept, not proof-of-advantage.

The filter is not a guarantee of correctness in either direction. It will not tell you whether a chemistry company will succeed commercially, whether its hardware roadmap is achievable, or whether a particular molecular simulation will yield a drug worth developing. What it will tell you is whether the application is, at minimum, the right *shape* — whether the genius's room was built for this puzzle. Everything else in quantum investing sits downstream of that question.

---

## What Would Change My Mind

If fault-tolerant QRAM were demonstrated at meaningful scale, Question 1 would relax substantially. Applications that currently fail on input data loading — certain machine-learning problems with compact feature representations, structured database queries — might become genuine candidates. I do not expect this in the near term, and the engineering obstacles are severe, but the honest position is that QRAM is a live research question, not a closed one.

A demonstrated exponential quantum speedup for a combinatorial optimization problem of practical size — not a theoretical construction but a real computation beating real classical hardware on a real instance — would require me to revisit the strong version of my claim about logistics and finance. The current state of evidence does not support such a speedup, but the absence of a proof of impossibility means the door is not completely closed.

## Still Puzzling

The boundary between "data hardness" and "computational hardness" is cleaner in textbooks than in practice. Many real problems are mixtures: they have large data inputs but also contain an exponentially hard subproblem that quantum might accelerate. Whether a quantum computer could be used as a specialized subroutine — handling only the computationally hard inner loop, with classical pre- and post-processing on either side — is an active area of research, and the right answer is genuinely not yet known. The filter as stated is conservative: it treats any large I/O as fatal. A more nuanced version would ask how large the computationally hard kernel is relative to the I/O overhead, and what hybrid classical-quantum architectures might make the tradeoff favorable.

---

## Further Reading

- **Scott Aaronson, "Read the Fine Print" (Nature Physics, 2015; author copy at scottaaronson.com)** — [scottaaronson.com/papers/qml.pdf](https://www.scottaaronson.com/papers/qml.pdf). The foundational statement of the I/O and state-preparation critique; the direct source for the filter's first and third questions.
- **"Disentangling Hype from Practicality: On Realistically Achieving Quantum Advantage" (Communications of the ACM / arXiv:2307.00523, 2023)** — [arxiv.org/abs/2307.00523](https://arxiv.org/abs/2307.00523). An independent academic survey mapping which applications can realistically clear the advantage bar; the filter's verdicts argued in systematic detail.
- **Phys. Rev. X, "Fast Quantum Simulation of Electronic Structure" (2026)** — [journals.aps.org](https://journals.aps.org/prx/abstract/10.1103/pb2g-j9cw). Primary source for the strongest passing case: quantum phase estimation applied to real molecular energy calculations on logical qubits, with concrete resource numbers.

---

*This handbook is a framework document, not financial advice. Company names are illustrative examples, not recommendations, and may age quickly.*

<!-- → [INFOGRAPHIC: One-page summary visual of the full filter. Top: the "genius in a soundproof room" metaphor rendered as a simple illustration — a door with a keyhole, text flowing in (small) and out (small), with a large "thinking space" bubble inside. Middle: the three questions as a decision flowchart — Q1 (compact input?) → Q2 (exponential computation?) → Q3 (small output?) → PASS or FAIL at each branch. Bottom: two columns listing the four passing examples and four failing examples from the chapter, with the killing question labeled on each failure. Caption: "The big compute, small data filter: a one-page reference for evaluating quantum application claims."] -->
