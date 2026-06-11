# Chapter 4 — Why the Quantum + LLM Thesis Is Wrong

*Three independent reasons a compelling story cannot be delivered.*

In 2018, Scott Aaronson gave his undergraduate student a problem he expected her to solve in one direction. The problem was a quantum algorithm for recommendation systems — the mathematics under a Netflix-style engine that predicts what you will want to watch next. Kerenidis and Prakash had shown, a few years earlier, that a quantum computer could solve this problem exponentially faster than any known classical method. Aaronson's student, Ewin Tang, was eighteen. Her job was to confirm the speedup was real.

She refuted it instead.

Tang produced a purely classical algorithm that accomplished essentially the same task only polynomially slower — not exponentially slower, polynomially. In algorithmic complexity, "polynomial" and "exponential" are not just quantitatively different; they are qualitatively different. A polynomial gap is negotiable. An exponential gap is what makes quantum computers theoretically interesting. Tang's result meant the supposed quantum advantage had never been a property of quantum mechanics at all. It had been an artifact of an assumption buried in how the data got loaded into the machine. Strip the assumption, grant the classical algorithm the same kind of data access, and the race ends in a tie.

The result cascaded. Tang and collaborators built a general toolkit from her approach and used it to dismantle a series of the genre's flagship speedup claims — quantum principal component analysis, quantum support vector machines, low-rank linear systems, clustering. One undergraduate, one problem, one structural flaw exposed — and then that flaw turned out to run through an entire category of quantum machine learning algorithms.

I am starting here because the story is the cleanest illustration of what this chapter is actually about: not a timeline risk, not an "it's too early" argument, but a structural failure. The quantum-plus-LLM thesis — the claim that quantum computing will accelerate large language models, supercharge AI training, and deliver "quantum AI" as a commercial product — fails for three independent reasons. Independent is the operative word. You do not need all three to be true. Any single one sinks the thesis. The fact that all three hold simultaneously is what makes this a structural conclusion rather than a prediction about timing.

<!-- → [DIAGRAM: Three parallel vertical columns, each labeled with one objection — "Dequantization," "Dense matmul mismatch," "Barren plateaus" — with a horizontal bar at top labeled "Quantum + LLM thesis fails if ANY ONE holds." Caption: "Three independent structural objections. Any single one is fatal."] -->

---

The first objection is dequantization, and Tang's result is its founding case.

To understand why it matters, you need to understand what quantum machine learning was actually claiming and where the claim lived.

The quantum recommendation-systems algorithm of Kerenidis and Prakash worked roughly like this. You have an enormous matrix — rows are users, columns are films, entries are ratings. Most entries are missing; you want to fill them in by finding the low-rank structure hiding in the data. Classically, this is hard because the matrix is huge: reading it takes time proportional to its size. The quantum algorithm seemed to beat this by loading the entire matrix into a quantum superposition almost instantly, using a hypothetical device called quantum random-access memory, or QRAM. From superposition, the algorithm could then manipulate the data quantumly and extract a recommendation in time that depended only on the matrix's rank, not its full dimensions.

The speedup was exponential. It was also housed entirely in that loading step.

Tang's insight was precise: the QRAM assumption granted the quantum algorithm a superposition over the entire matrix, which is a very powerful form of data access. What if you granted a classical algorithm comparably powerful, but classically feasible, sampling access to the same data? Could a classical algorithm exploit that access to nearly match the quantum runtime? Yes. That is what she proved. The quantum runner had been given a ninety-meter head start in a hundred-meter race. Let the classical runner start there too, and the finish is a tie.

The moment you see this, the dequantization of other algorithms becomes almost inevitable. The entire genre of quantum machine learning speedups had been built on the same hidden scaffold: assume QRAM loads classical data into superposition for free, derive an exponential advantage, call it quantum. If the advantage lived in the loading assumption rather than in the quantum computation, then any algorithm in the genre was a candidate for the same treatment. Tang and collaborators found that many were. The precise tally depends on how you bundle the algorithms, so I will not anchor you on a number; what matters is that the refutation was not a one-off. It was a systematic exposure of a load-bearing assumption that the field had not examined.

What dequantization does not show is equally important to carry forward. It does not prove quantum computers are useless for machine learning in general. It proves that a specific class of claimed exponential speedups — those built on loading ordinary classical data through QRAM — was illusory. Problems with genuinely quantum data, problems that do not require loading a classical dataset, are untouched by this. Modest polynomial speedups on structured problems might survive. The scope is precise; overclaiming in either direction is its own error.

But the scope covers most of what "quantum AI" pointed to at the time. And a fresh LLM-acceleration claim in 2026 is making it again.

<!-- → [DIAGRAM: Flowchart — "Claimed quantum ML speedup" → "Where does the advantage live?" → two branches: "In the QRAM loading assumption" (leads to "Classical algorithm can match it: dequantized") and "In the quantum computation itself" (leads to "Speedup may survive: verify scope and data type"). Caption: "The diagnostic question for any quantum ML speedup: where does the advantage actually live?"] -->

---

The second objection is simpler and more brutal, because it does not depend on any theoretical subtlety. It depends on what training a language model actually is.

Training a large language model is, overwhelmingly, dense matrix multiplication. Not sparse. Not low-rank. Dense: enormous grids of numbers, mostly non-zero, multiplied together billions of times. The data going in is classical — tokens of text, encoded as numerical vectors. The data coming out is classical — billions of weights that represent everything the model has learned. The computation in the middle is a long chain of matmul operations, and the chain is not low-rank enough, not structured enough, and not small enough for any known quantum linear algebra trick to apply.

Quantum linear algebra does exist. It is a real family of techniques. But it applies to a narrow and specific slice of linear algebra: sparse or low-rank structured problems that return a small classical output — a single number, an energy, a yes/no answer. The quantum linear systems algorithm of Harrow, Hassidim, and Lloyd, for example, solves a linear system exponentially faster than classical methods — but only if the matrix is sparse, the condition number is small, and you only want a quantum state representing the solution (not the actual solution vector). Reading out the full solution vector classically is slow enough to erase the speedup. That last condition is not a technicality. It is the nature of quantum measurement: you cannot read out a quantum state without collapsing it, and extracting n bits of classical information from an n-qubit state takes n measurements. Full readout is expensive by design.

Training a language model fails the narrow-slice test on every axis simultaneously. The matrices are dense, not sparse. The output is enormous — billions of weights — not a small summary. The data starts classical and ends classical, which means you pay the full cost of loading it in and reading it out, and both costs swamp any speedup you might find in the quantum middle.

<!-- → [TABLE: Three-column table — "Dimension" | "What quantum linear algebra requires" | "What LLM training is" — rows: Sparsity | sparse or low-rank structured | dense; Output size | small classical summary | billions of weights; Data type | quantum-native or structured | classical tokens in, classical weights out; End-to-end cost | affordable | loading + readout swamp any middle speedup. Caption: "LLM training fails the narrow-slice test on every axis."] -->

"Quantum is good at linear algebra" is a true statement about a narrow, structured problem family. Dense matrix multiplication with full classical readout is not that family. The mismatch is not a matter of hardware immaturity. It is a matter of what quantum computation is fundamentally suited to do.

---

The third objection addresses the route that survives the first two: if you cannot use quantum linear algebra to speed up classical training, perhaps you build a quantum model directly — a circuit with tunable parameters that you train the way you train a neural network, by adjusting the knobs to reduce error. This is the variational quantum circuit, sometimes marketed under the phrase "quantum neural network." The 2018 result by McClean and colleagues at Google established why this route has a wall on it.

Let me set up the wall carefully, because the imprecise version of the argument is both common and misleading.

When you train a neural network, you compute the gradient of the loss function with respect to the network's parameters — the direction each parameter should move to reduce the error. Gradient descent works because the gradient carries useful signal: it tells you which direction is downhill, and how steep the slope is. For gradient descent to train a model, the gradient must have nonzero variance. If every measurement of the gradient comes back near zero with nearly no spread, you cannot distinguish the true gradient from noise. You do not know which direction is downhill. You are stuck.

McClean and colleagues proved that for variational quantum circuits with a sufficiently expressive structure — specifically, random circuits with many entangling layers — the variance of the gradient shrinks exponentially with qubit count. Not the gradient itself, necessarily; the variance of the gradient. The signal collapses as the machine gets large. On a logarithmic axis, gradient variance plotted against qubit count falls as a roughly straight line downward. This is the barren plateau: not a literal flat landscape, but one whose informative topography is buried under exponential noise. The machine gets interesting — big enough to do something classically intractable — precisely as it becomes impossible to train.

<!-- → [CHART: Log-scale line chart — x-axis: qubit count (8, 12, 16, 20, 24); y-axis: log(gradient variance). Single downward line labeled "expressive random circuit." Horizontal dashed line labeled "noise floor." Lines converge well before 30 qubits. Caption: "Gradient variance falls exponentially with qubit count. The trainability problem is not a hardware problem — it is structural."] -->

The known fixes are real, and they deserve to be stated honestly. You can use simpler "local" cost functions that only look at a few qubits at a time. You can use shallow or carefully structured circuits. You can choose careful initializations. These strategies do reduce or eliminate barren plateaus in specific architectures. But they work by restricting the circuit — dialing back its expressiveness or its entanglement. And a strong recent line of theory, running roughly from 2023 to 2025, argues that the same structural simplifications that free a circuit from barren plateaus tend to make it classically simulable: once a laptop can reproduce it, the quantum advantage is gone [verify current state of this result before citing; treat as strong-but-still-developing]. You face a fork with no good branch. Either the circuit is expressive enough to be interesting and cannot be trained, or it is trainable and a classical computer can already do it. There is no known middle path through.

The three objections are now on the table: dequantization, dense matmul mismatch, barren plateaus. They arrive from different corners of theory. They point at different parts of the proposed mechanism. Any one of them is fatal. The structure of the quantum + LLM thesis is therefore not "overhyped but promising" — it is "wrong at the level of mechanism."

---

There is a tell worth watching in the companies themselves, and it is more useful than any financial metric for this particular question.

Several quantum firms that once led their investor narrative with "quantum AI" have quietly shifted their public emphasis toward quantum chemistry and materials simulation — the subject of the next chapter. Read that pivot as a credibility signal. It usually means the people running the technical side of the company understand their hardware's actual constraints and have stopped making a claim they cannot defend. The pivot is not an admission of defeat; molecular simulation is a genuinely promising application for near-term quantum hardware, and a company that lands there is showing you it can read its own literature.

The inverse signal is just as clear. A company leading with LLM acceleration in 2026, after the dequantization literature, after the barren plateau result, after the dense matmul analysis is publicly available — that company is either uninformed or choosing to market to an audience it hopes is uninformed. Neither is an endorsement.

The reflex the AI trade taught — find the layer everyone will need and own it — is a good reflex. It is pointed at the wrong target. "Quantum AI" bundles the technology you already believe in with the technology you are uncertain about, and invites you to assume the uncertain one inherits the momentum of the certain one. What you pay for when you buy that bundle is a synergy that does not exist. When the premium unwinds — and it will, because the underlying claim cannot be delivered — there is no later date at which the thesis comes good. You will not have been early. You will have been wrong.

The three-layer test from Chapter 1 handles this cleanly. The quantum + LLM pitch is a Layer-3 premium built on a Layer-2 claim that fails Layer-1 analysis. Check each layer in order, and the premium evaporates before you pay it.

---

## Further Reading

- **Scott Aaronson, "Customers who liked this quantum recommendation engine might also like its dequantization," Shtetl-Optimized blog** — [scottaaronson.blog/?p=3880](https://scottaaronson.blog/?p=3880). The advisor's own plain-language account of how his student demolished the result he expected her to confirm. The most accessible entry point to the whole dequantization story.
- **Ewin Tang, "A quantum-inspired classical algorithm for recommendation systems," arXiv:1807.04271 (2018)** — The primary source: the original dequantization, written by the person who did it.
- **Jarrod McClean et al., "Barren plateaus in quantum neural network training landscapes," *Nature Communications* 9, 4812 (2018)** — The peer-reviewed result establishing why expressive variational quantum circuits cannot be trained at scale. Read the abstract and Figure 1; both are accessible without specialist background.

---

## Exercises

**Warm-up**

1. *(Basic recall)* What is QRAM, and why did its assumed properties matter so much to the quantum machine learning algorithms that dequantization later refuted? *What this tests: whether you can identify where the speedup claim actually lived.*

2. *(Basic recall)* What does it mean to say the variance of a gradient collapses exponentially with qubit count? In one or two sentences, explain why this makes a variational quantum circuit untrainable at scale. *What this tests: whether you have the barren plateau argument in your own words.*

3. *(Basic recall)* Name the two axes on which LLM training fails the "narrow slice" test for quantum linear algebra — sparsity and output size are the answers; explain why each matters. *What this tests: whether you can articulate the dense matmul mismatch concretely.*

**Application**

4. *(Translation)* A startup's investor deck reads: "Our quantum neural network achieves 94% accuracy on MNIST, outperforming classical baselines on small-scale tests, with a clear path to scale." Which of the three objections applies most directly, and what question would you ask management before taking the benchmark seriously? *What this tests: applying the objections as a filter to a real-world claim.*

5. *(Translation)* A quantum company's press release announces: "Our platform accelerates transformer inference by 40× on benchmark tasks." List the information you would need to evaluate whether this survives the dequantization and dense matmul objections. *What this tests: distinguishing what a headline says from what you need to know.*

6. *(Translation)* A company that previously led its narrative with "quantum AI" pivots its investor pitch to emphasize quantum chemistry simulation. Using the chapter's argument, explain why this pivot should raise, not lower, your assessment of management's technical credibility. *What this tests: reading credibility signals in company behavior.*

**Synthesis**

7. *(Cross-chapter)* Apply the three-layer test from Chapter 1 to a quantum company whose primary pitch is LLM acceleration. At which layer does the pitch fail, and what is the nature of the failure — is it a Layer-2 timing problem or a Layer-1 structural problem? Why does the distinction matter for how you price the equity? *What this tests: connecting the structural objections to the investment framework.*

8. *(Cross-chapter)* The chapter argues the quantum + LLM thesis is "wrong at the level of mechanism," not merely early. Explain what distinguishes a timing risk from a mechanism failure, using one of the three objections as your example. *What this tests: precision about the type of risk, which determines the appropriate investment posture.*

**Challenge**

9. *(Open-ended)* The barren plateau fixes — local cost functions, shallow circuits, careful initialization — are real. Construct the strongest version of the counterargument: is there a scenario in which one of these fixes, or a future fix not yet discovered, could break the fork and deliver a trainable, non-classically-simulable quantum neural network? What would that require, and what would constitute genuine evidence that the fork had been broken rather than just moved? *What this tests: the ability to engage seriously with the strongest version of the opposing view rather than treating the structural argument as permanently closed.*
