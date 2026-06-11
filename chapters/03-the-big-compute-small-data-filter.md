# Chapter 3 — The Big Compute, Small Data Filter

## Decision question

A quantum company has just told you its technology will "revolutionize" something — drug discovery, logistics, finance, artificial intelligence, your particular industry. Before you open the financials, before you weigh the management team, you want a fast, physics-grounded screen for one question: **How do I tell whether a quantum company's target application is real or invented?**

## The short answer

Apply the big compute, small data filter — three questions you can run without a physics degree. A problem is a *candidate* for genuine quantum advantage only if (1) it can be specified compactly, by a handful of parameters rather than a large dataset; (2) solving it requires exploring an exponentially large computational space; and (3) the useful answer is small — a number, a decision, a short result. Problems that pass all three (molecular simulation, integer factoring) might be real quantum applications. Problems that require loading or returning large amounts of data (LLM training, database search, supply-chain optimization, financial time-series) almost certainly are not, and they fail *structurally* — not because the hardware is immature, but because of a limit no future hardware removes.

## Why this matters

The instinct every investor brings from the AI era is "big data means big opportunity." Quantum computing inverts that instinct, and getting the inversion wrong is how you buy the wrong thesis at any price.

Here is the trap. A quantum company names a large, expensive, important problem — optimizing a global supply chain, say, or pricing a derivatives book — and the importance of the problem is presented as evidence that quantum will solve it. But importance and classical difficulty are *irrelevant* to whether a problem is a quantum problem. What matters is the *shape* of the problem, and most large, data-heavy problems have exactly the wrong shape. An investor who cannot run this filter will fund application theses that were never physically plausible, no matter how good the qubits get. The hardware quality is a separate question; if the application fails the filter, excellent hardware does not save it.

The filter is also the practical face of a deep result. As Chapter 2 noted, only a structured minority of problems sit in the believed gap where quantum computers help. This chapter gives you a field-usable proxy for "does this problem have that structure — *and* is it free of the data-movement penalties that erase the gain?"

A note on provenance: the three-question form is **this handbook's own synthesis**. A single citable source stating the filter in exactly these three questions does not exist; the construction is built on Scott Aaronson's I/O critique and the BQP/BPP structure argument, and is supported by — not lifted from — the literature cited below. Present it, and use it, as the author's framework.

## The framework

The pattern quantum computers genuinely accelerate has a memorable shape: **a small mouth and a huge stomach.** A small specification goes in, an exponentially large amount of computation happens inside, and a small answer comes out. Three questions test for it.

**Question 1 — Can the problem instance be described compactly?** A few parameters, not a large dataset. *This is the input half of the I/O bottleneck.* A quantum computer's exponential edge is in *manipulating* a quantum state, not in *building* one from classical data. To act on classical data you must first encode it into a quantum state — a step called *state preparation*. And here is Aaronson's "fine print": a basic information-theoretic bound says that preparing an arbitrary state with *N* entries takes on the order of *N* operations. So if your problem requires loading a large dataset, the exponential speedup is gone *in the very first step* — you spend it all on loading ([Aaronson, "Read the Fine Print"](https://www.scottaaronson.com/papers/qml.pdf)). Proposed escape hatches exist — *QRAM*, a hypothetical quantum memory that serves data in superposition in logarithmic time — but building large, fault-tolerant QRAM is itself an unsolved and costly problem. The advertised speedups are *conditional* on that access model, and the condition is rarely met for real classical data [contested — see pantry flag: whether QRAM is ever buildable at fault-tolerant scale is open].

**Question 2 — Does solving it require exploring an exponentially large space?** This is the *big compute* in the middle — the only place a quantum computer earns its keep. The hardness must be *intrinsic computational or simulation hardness* (an exponentially large space of possibilities or quantum states to explore), not data-movement hardness dressed up to look like computation. Factoring a large number, or simulating the electrons in a molecule, has this kind of intrinsic hardness. Sorting a list, serving a web page, or shuffling a big dataset does not.

**Question 3 — Is the useful output small?** *This is the readout half of the I/O bottleneck.* Even a perfect quantum computation leaves you holding a quantum *state*, and the only way to learn its contents is to *measure* — which yields a few classical bits per run and collapses the state. To read out an *N*-dimensional answer you generally need on the order of *N* measurements and repetitions, which destroys any exponential speedup if the *answer* is large. A single number (a molecule's ground-state energy), a yes/no, a short list of prime factors — fine. A reconstructed image, a full probability distribution, a set of trained model weights — not fine; the readout cost swamps the gain ([Aaronson, lecture notes](https://www.scottaaronson.com/qisii.pdf)).

A problem passes only if it clears all three: small in, big compute, small out. Fail any one — usually by being data-heavy on either end — and the application thesis is structurally weak regardless of the hardware.

A useful mental image holds the whole filter together: picture a genius locked in a soundproof room. She can solve any puzzle you can whisper through the keyhole, and whose answer is a single word she can whisper back. For problems of that shape she is unbeatable. But if solving the puzzle requires you to shove an entire encyclopedia through the keyhole first, and then to extract a full library of answers back through it, the keyhole — not the genius — becomes the bottleneck, and you would have been faster doing the work yourself outside the room. The genius is the quantum processor; the keyhole is the I/O channel; the puzzles she is wasted on are the data-heavy ones. The speedup, when it exists, is in the *thinking* — never in the *reading and writing*. Every failure case below is really a story about the keyhole.

## What it looks like in practice

Set four passing applications beside four failing ones, and name the question that kills each failure.

**Passes:**

- **Integer factoring (Shor's algorithm).** The input — the number to factor — is a few thousand bits (tiny). The search space — its possible factors — is astronomical (big compute). The output — two primes — is tiny. A textbook pass on *structure*. The honesty caveat: cryptographically relevant factoring needs *millions* of high-quality physical qubits and deep fault tolerance, so this is a pass on shape, *not* a near-term capability. Do not infer that RSA is about to break.
- **Molecular / quantum-chemistry simulation.** The electrons in a molecule occupy a state space that grows exponentially with electron count — precisely the regime classical computers struggle with and the one Richard Feynman proposed quantum computers for in 1981. The input (a molecular description) is compact; the useful output (a ground-state energy, a binding affinity) is a single number. The engine, *quantum phase estimation* (QPE), extracts that energy at a cost that grows only polynomially in system size. Recent work has combined QPE with *logical* qubits to compute molecular energies — a real milestone toward chemistry advantage ([Phys. Rev. X, 2026](https://journals.aps.org/prx/abstract/10.1103/pb2g-j9cw); [arXiv:2312.16375](https://arxiv.org/pdf/2312.16375)). This is the application most independent forecasters expect to mature first.

**Fails:**

- **LLM training.** Killed by Questions 1 *and* 3 at once: terabytes of input, billions of output parameters. Both I/O bottlenecks fire simultaneously, with no proposed route to load the corpus or read out the weights without paying full *N*-scale costs.
- **Database / unstructured search.** Killed by Question 1. Aaronson's point is blunt: any problem "limited by accessing classical data... will be solved faster by classical computers." Grover's algorithm offers only a *quadratic* (√N) speedup, and reading out the found item still costs ~√N — useful in principle, never exponential, and beaten by classical I/O for real lookups.
- **Supply-chain / logistics optimization.** Killed by Questions 1 and 3. Every route, SKU, and constraint is a large input; a full schedule is a large output; the hardness is combinatorial and data-bound, not Hilbert-space-bound. This is among the most over-claimed quantum applications.
- **Financial time-series analysis.** Killed by Question 1. Large data inputs (every price tick), no proven exponential speedup, hardness that lives in the data rather than in an exponential state space.

A fair qualification, in the interest of not overstating the case: "quantum is useless for all optimization" goes too far. The honest claim is that there is *no proven exponential* advantage for data-heavy optimization, ML, or finance; modest *heuristic* (non-exponential) gains remain an open and contested question [contested — see pantry flag]. Keep the filter focused on *exponential* advantage, which is what the breathless claims promise and what justifies the valuations.

The real skill in applying this filter well is learning to find the *buried assumption* in a vendor's own materials. In a vendor white paper claiming an exponential speedup for a data-heavy task, locate the sentence — usually deep in the appendix — that quietly assumes the data is "already loaded" into a quantum state, or that an idealized QRAM exists. That assumption is Aaronson's fine print, and it is where the speedup secretly went.

## What to watch for

- **Application claims that name specific problem classes** — transition-metal catalysis, nitrogen fixation, battery-cathode simulation — rather than broad sectors ("quantum will transform pharma"). Specificity is a sign someone ran the filter internally.
- **Computational-chemistry benchmarks against real classical baselines** (such as density functional theory) on *named* molecules, with the active-space size and accuracy target stated.
- **Companies quietly pivoting away from "quantum AI" toward quantum chemistry or materials** — a sign they understand their own hardware's constraints.

## What to ignore

- **Any quantum application claim built on large datasets** — recommendation systems, "quantum big data," logistics optimization, financial analytics promising exponential speedups. These fail the filter structurally.
- **"AI acceleration" claims.** The thesis that quantum will speed up LLM training or inference fails Questions 1 and 3 at once; it is not a timing problem but a structural one.
- **Chemistry demonstrations on textbook molecules** — H₂, LiH, BeH₂. Classical methods handle these trivially; such demos are proof-of-concept, not proof-of-advantage.

## The decision rule

Before reading any quantum company's investor materials, run its headline application through the three questions — small specification in, exponentially large computation, small classical answer out. If it fails (almost always by being data-heavy on the input or output), the application thesis is structurally weak no matter how good the hardware, and you should weight the rest of the pitch accordingly.

## Further reading

- **Scott Aaronson, "Read the Fine Print" (Nature Physics, 2015; author copy at scottaaronson.com)** — [scottaaronson.com/papers/qml.pdf](https://www.scottaaronson.com/papers/qml.pdf). The foundational, accessible statement of the I/O / state-preparation critique that the whole filter rests on; written by the field's leading skeptic-insider.
- **"Disentangling Hype from Practicality: On Realistically Achieving Quantum Advantage" (Communications of the ACM / arXiv:2307.00523, 2023)** — [arxiv.org/abs/2307.00523](https://arxiv.org/abs/2307.00523). An independent academic survey mapping which applications can realistically clear the advantage bar and which cannot — the filter's verdicts, argued in detail.
- **Phys. Rev. X, "Fast Quantum Simulation of Electronic Structure" (2026)** — [journals.aps.org](https://journals.aps.org/prx/abstract/10.1103/pb2g-j9cw). A primary source for the strongest "pass" case: quantum phase estimation applied to real molecular energy calculations, with concrete resource numbers.

*This handbook is a framework document, not financial advice. Company names are illustrative examples, not recommendations, and may age quickly.*
