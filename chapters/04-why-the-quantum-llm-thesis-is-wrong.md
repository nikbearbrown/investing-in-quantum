# Chapter 4 — Why the Quantum + LLM Thesis Is Wrong

## Decision question

You have heard, probably more than once, that quantum computing will supercharge artificial intelligence — that the two great technology stories of the decade are about to merge, and that the companies sitting at the intersection deserve a premium. Should you pay extra for a quantum company whose pitch is that it will accelerate AI, train large language models faster, or unlock "quantum machine learning"?

## The short answer

No. The thesis that quantum computers will accelerate large language models is not merely early — it is structurally wrong. The headline speedups that quantum machine learning once claimed were quietly dismantled by a body of work called the dequantization literature, beginning with a result by an undergraduate in 2018. On top of that, the core arithmetic of training a language model is the exact shape quantum computers are bad at, and the most promising "quantum neural network" designs run into a trainability wall that has no known exit. Any one of these would be fatal. Together they make the quantum + LLM story a dead end, and a company that leads with it either does not understand its own hardware or is counting on you not to.

## Why this matters

The AI trade taught a generation of investors a reflex: when a technology is clearly transformative, find the layer that everyone will need and own it. Quantum companies have noticed this reflex and learned to trigger it. "Quantum AI" is the phrase that does it. It bundles the one technology you already believe in (AI) with the one you are uncertain about (quantum), and invites you to assume the uncertain one inherits the momentum of the certain one.

If you pay a premium for that bundle, you are paying for a synergy that does not exist. This is not a timing risk, where you are early and patient money eventually wins. It is a category error. When the premium unwinds — and it will, because the underlying claim cannot be delivered — there is no later date at which the thesis comes good. You will not have been early. You will have been wrong.

The cost of getting this right, by contrast, is almost nothing. You learn three structural objections, apply them as a filter, and discount accordingly. The reflex from the AI trade is a good reflex. It is just pointed at the wrong target.

## The framework

There are three independent reasons the quantum + LLM thesis fails. Independent is the operative word: you do not need all three to be true. Any single one sinks the thesis. The fact that all three hold simultaneously is what makes this a structural conclusion rather than a guess about timelines.

**Objection 1 — Dequantization.** A quantum machine learning algorithm is "dequantized" when someone writes an ordinary classical algorithm that, given the same kind of access to the data, runs only a little slower — slowly enough to destroy the claimed *exponential* advantage. The pattern matters because most of the early quantum machine learning speedups quietly assumed a special way of feeding data into the quantum computer, called QRAM (quantum random-access memory), a hypothetical device that loads a huge classical dataset into a quantum state almost instantly. No scalable QRAM has ever been built, and the deeper problem is that the speedup lived in that assumption rather than in the computation. When the classical competitor is granted a comparably strong way to sample the data, the advantage tends to evaporate.

The story begins in 2018. Ewin Tang, then roughly eighteen and an undergraduate at the University of Texas at Austin, was given a problem by her advisor, the complexity theorist Scott Aaronson. The problem was the quantum recommendation-systems algorithm of Kerenidis and Prakash — at the time one of the strongest candidates for a provable exponential quantum speedup on a real-world task (the Netflix-style problem of predicting what a user will like). Aaronson expected her to prove the speedup was genuine. Instead she refuted it, producing a purely classical algorithm that did essentially the same job only polynomially slower (Tang, *A quantum-inspired classical algorithm for recommendation systems*, arXiv:1807.04271, 2018). The supposed quantum advantage had been an artifact of the data-loading model, not the algorithm.

The result did not stay contained. Tang and collaborators built a general toolkit — a sampling-based framework for low-rank matrix problems — and used it to dequantize a series of the genre's flagship claims: quantum principal component analysis, quantum support vector machines, low-rank linear systems, clustering (Chia, Gilyén, Li, Lin, Tang, Wang, arXiv:1910.06151, 2019). I write "a series" deliberately; you will sometimes see a specific count like "eight," but the precise tally depends on how you bundle the algorithms, so do not anchor on a number. The point is that the original refutation was not a one-off. It exposed a systematic flaw running through an entire category of quantum machine learning speedups.

What dequantization does *not* show is also important. It does not prove quantum computers are useless for machine learning in general. It proves that a specific class of claimed *exponential* speedups — the ones built on loading ordinary classical data through QRAM — was illusory. Problems with genuinely quantum data are untouched by it, and modest polynomial speedups might survive. Keep the scope tight; overclaiming here is its own error.

**Objection 2 — Dense matrix multiplication with classical input and output.** Training a language model is, overwhelmingly, dense matrix multiplication: enormous grids of numbers multiplied together, billions of times, with classical data going in (tokens of text) and classical data coming out (the model's weights). Quantum computers have no end-to-end speedup for this shape. The quantum linear-algebra tricks that exist are for *sparse* or *low-rank* structured problems that return a *small* classical summary — an energy, a single number, a yes/no. Training is the opposite on every axis: dense, not sparse; huge output, not small. You pay an enormous cost to load the data in (no QRAM), and another enormous cost to read the full result out (quantum measurement extracts information one slow piece at a time). Both costs swamp any speedup you might find in the middle. "Quantum is good at linear algebra" is true only for a narrow, structured slice of linear algebra. Dense matmul with full readout is not that slice.

**Objection 3 — Barren plateaus.** The other route people propose is the "variational quantum circuit," sometimes marketed as a quantum neural network: a quantum circuit with tunable knobs that you train the way you train a neural network, by nudging the knobs to reduce error. In 2018, McClean and colleagues at Google proved a result that has held up since (McClean, Boixo, Smelyanskiy, Babbush, Neven, *Barren plateaus in quantum neural network training landscapes*, *Nature Communications* 9, 4812, 2018). For sufficiently expressive random circuits, the *variance* of the training gradient shrinks exponentially as you add qubits.

That precise phrasing matters, so let me be careful: it is not that every gradient is literally zero. It is that the gradient's variance — the spread of useful signal you have to work with — collapses exponentially with qubit count. The optimizer finds itself on a landscape so flat that the direction it should move is drowned in measurement noise. The intuition is a salt flat the size of a continent: every direction reads as flat, and your altimeter shows only static. Plotted on a logarithmic axis, gradient variance against qubit count is roughly a straight downward line — the signal you need to train the machine vanishes exactly as the machine gets big enough to be interesting.

Here is the trap. The known fixes — using simpler "local" cost functions, shallow or carefully structured circuits, clever initializations — all work by *restricting* the circuit, dialing back its expressiveness or its entanglement. And a strong, recent line of theory argues that the same structure that frees a circuit from barren plateaus often also makes it *classically simulable*: once a laptop can reproduce it, the quantum advantage is gone (this is an active claim from roughly 2023–2025; cite the specific recent papers, and treat it as strong-but-still-developing rather than fully settled [verify]). So you face a fork with no good branch. Either the circuit is expressive enough to be interesting and cannot be trained, or it is trainable and offers nothing a classical computer couldn't already do. There is no free lunch.

## What it looks like in practice

Return to the 2018 recommendation-systems result, because it is the cleanest illustration and the most honest narrative the field has.

The quantum claim was an exponentially faster way to do low-rank matrix completion — the math under a recommendation engine. The hidden assumption was QRAM: instant superposition access to the entire ratings matrix. Tang's move was not to build a better quantum computer. It was to notice that if you grant a *classical* algorithm an analogous strong sampling access to the same matrix, it nearly matches the quantum runtime. The "exponential speedup" was therefore a property of the assumed input device, not of quantum mechanics. The race had been staged with the quantum runner already ninety meters down a hundred-meter track; let the classical runner start there too, and the finish is a tie.

The investor lesson is not about recommendation engines specifically. It is about what happened next: the refutation cascaded through the whole low-rank quantum-machine-learning genre, which is most of what "quantum AI" pointed to at the time. An undergraduate, working a single problem, exposed the genre's load-bearing assumption. That is what a structural flaw looks like from the outside.

There is also a tell worth watching in the companies themselves. Several quantum firms that once led with "quantum AI" have quietly pivoted their public emphasis toward quantum chemistry and materials simulation (the subject of Chapter 5). Read that pivot as a credibility signal: it usually means the people inside the company understand their hardware's actual constraints. A *fresh* LLM-acceleration claim in 2026 points the other way.

## What to watch for

- Companies moving their primary narrative *away* from "quantum AI" and toward molecular simulation or materials. This is a sign of technical literacy, not weakness.
- Honest, scoped claims: "polynomial speedup on a structured problem with small output," not "exponential speedup for AI." A claim that names its data-access assumptions out loud is being made by people who have read the literature.
- Whether independent theorists — Aaronson's blog is the most accessible — have commented. If a quantum-machine-learning claim is real, the dequantization community will say so; their silence on a "speedup" usually means it isn't one.

## What to ignore

- Any press release claiming quantum will "accelerate AI," "speed up LLM training," "transform foundation models," or deliver "quantum AI" as the headline product. These run straight into all three objections.
- "Quantum neural network" demonstrations on tiny problems presented as a path to scale. The barren-plateau wall is on that path, and it gets worse, not better, as you scale.
- Speedup claims that do not state how data gets into the machine. The data-loading assumption is where the magic usually hides; if it is unstated, assume it is doing the work.

## The decision rule

Apply a discount to any quantum company whose primary revenue story is AI or LLM acceleration. The thesis is structurally wrong, not early — and the company either knows it (and is marketing to you anyway) or doesn't (and shouldn't be trusted with your capital). Neither is a reason to pay a premium.

## Further reading

- **Scott Aaronson, "Customers who liked this quantum recommendation engine might also like its dequantization," Shtetl-Optimized blog (scottaaronson.blog/?p=3880).** The advisor's own plain-language account of how his student demolished the result he expected her to confirm — the most accessible entry point to the whole story.
- **Jarrod McClean et al., "Barren plateaus in quantum neural network training landscapes," *Nature Communications* 9, 4812 (2018).** The independent, peer-reviewed result establishing why expressive variational quantum circuits cannot be trained at scale.
- **Ewin Tang, "A quantum-inspired classical algorithm for recommendation systems," arXiv:1807.04271 (2018).** The primary source: the original dequantization, written by the person who did it.
