# Chapter 2 — What Quantum Actually Is (And Isn't)

*The vocabulary that separates a real advance from a press release.*

Here is a number that appeared in a press release a few years ago: 1,000 qubits. That was the whole claim — a company had built a machine with 1,000 of the things that are supposed to make quantum computers special. The number was real. The machine existed. And the number was almost completely meaningless, for reasons the press release did not mention and most readers had no way to notice.

That is the problem this chapter is built to solve. Not quantum physics as a complete subject — that is a career, not a chapter — but the specific, narrow set of physical ideas and technical terms you need to read a quantum computing claim and know whether it says anything. Three concepts. Six terms. That is actually the whole list. Everything else in the field is either downstream of these or irrelevant to anyone evaluating a technology claim rather than building the hardware.

Start with why the vocabulary gap is expensive.

---

## The number that tells you nothing

For several years, qubit count was the headline metric in quantum computing. Companies announced ever-larger chips. Journalists reported the numbers. Investors noticed them. And then the field — the engineers, the physicists, the people actually building these things — publicly repudiated the metric. The phrase that appeared in practitioner writing around 2024 was "from more qubits to better qubits." The reason for the pivot is simple once you understand the physics, and I will explain it shortly. But notice what happened first: an entire sector spent years optimizing for a number that the people closest to the problem already knew was wrong.

An investor who does not know what a qubit actually does cannot tell the difference between 1,000 useful qubits and 1,000 noisy, short-lived, essentially decorative ones. The vocabulary that follows is the difference.

---

## Superposition: the resource, not the magic

A classical bit is always either 0 or 1. Before you measure a qubit, it is in what physicists call a *superposition* — a combination of both, weighted by numbers called amplitudes. The amplitude is not a probability exactly; the strange part is that amplitudes can be negative, and the way they combine is the key to everything.

The popular shorthand is that a qubit "tries both 0 and 1 at once," and this is the single most damaging misconception in the field. It implies unlimited free parallelism: ten qubits try all 1,024 combinations simultaneously, a hundred qubits try 2¹⁰⁰ answers in parallel. If that were true, you would just read out all the branches and have your answer. But you cannot. When you measure a qubit, the superposition collapses to a single ordinary value, 0 or 1, chosen according to the amplitudes. You get one answer. The computation is over.

So what was the superposition actually doing?

The honest answer is: interference. Because amplitudes can be negative, two branches of a computation can cancel each other out — just as two waves with opposite phases cancel in water. A quantum algorithm is a carefully arranged sequence of operations that makes the wrong answers cancel and the right answer reinforce, so that when you finally measure, the outcome you get is overwhelmingly likely to be correct. The parallelism is not free; it is a setup for interference. The algorithm's entire job is to load the dice before you measure.

The cleanest physical demonstration of this is the double-slit experiment. A single particle is sent through two slits. It arrives as a wave — its amplitude passes through both openings — and on the screen behind, the waves from the two slits interfere. Bright bands form where they reinforce; dark bands where they cancel. No one guides the particle; the geometry of the amplitudes does all the work. Quantum computing is that same self-interference, engineered on purpose.

<!-- → [DIAGRAM: Two-slit interference with amplitude wave going through both slits, reinforcing at bright bands and canceling at dark bands. Caption: The particle's amplitude passes through both slits and interferes with itself — bright where amplitudes add, dark where they cancel. Quantum algorithms use the same principle: arrange operations so wrong answers cancel and the correct answer survives to measurement.] -->

This matters for evaluating claims because an algorithm that cannot set up this interference has no quantum advantage. Superposition alone — without the right interference structure — is not enough. The question to ask of any proposed quantum application is: does the algorithm exploit interference in a way a classical computer cannot replicate? If the answer is not clearly yes, the quantum speedup is probably not real.

---

## Entanglement: correlations that classical physics cannot reproduce

When two qubits become entangled, their states are correlated in a way that no independent description of the two can capture. Measure one qubit and you instantly fix what you will find when you measure the other — regardless of the physical distance between them. Einstein called this "spooky action at a distance" and was, famously, bothered by it his entire life.

For the investor, skip the philosophy and keep the capacity. Entanglement allows *n* qubits to encode correlations that would require 2ⁿ classical numbers to write down explicitly. That exponential compression is what makes certain computations tractable on quantum hardware that are impossible to run classically — not because the quantum machine is faster at the same work, but because the representation it uses is fundamentally different in structure.

Two myths worth retiring immediately. First: entanglement does not transmit information faster than light. You cannot control which outcome you observe, so no usable signal travels between the entangled particles. Every "quantum teleportation" headline glosses over this. Second: entanglement is not a guarantee of quantum speedup — it is a necessary ingredient for it. A quantum computation without entanglement can always be simulated efficiently on a classical computer. Entanglement is required; it is not sufficient.

<!-- → [DIAGRAM: Two entangled qubits shown with measurement outcomes correlated — measuring one (getting 0 or 1) immediately fixes the other's outcome. Annotation: 'No information travels — you cannot choose which outcome you observe.' Caption: Entanglement is not communication; it is correlation. Measuring one member of an entangled pair fixes what you'll find on the other, but neither party can use this to send a message.] -->

---

## Decoherence: the enemy

Superposition and entanglement are exquisitely fragile. A stray photon, a vibration, a fluctuation in the electromagnetic environment — any uncontrolled interaction between the qubit and its surroundings — leaks quantum information out of the system and destroys the superposition. Physicists call this *decoherence*.

The length of time a qubit survives in a useful quantum state before decoherence wins is its *coherence time*. Today's best hardware achieves coherence times ranging from microseconds to low milliseconds, depending heavily on the physical implementation. That sounds like a small number, and it is — but it is enough time to run thousands of gate operations if the gates are fast and reliable. The constraint is that every operation in a computation must complete before decoherence degrades the state beyond recovery.

Decoherence is the whole engineering problem. It is why quantum processors live inside dilution refrigerators cooled to temperatures colder than deep space. It is why quantum chips need elaborate electromagnetic shielding. It is why building these machines is genuinely, deeply hard in ways that cannot be solved by manufacturing at scale or by writing better software. The physics sets the limits; the engineering is a sustained effort to push against them.

<!-- → [DIAGRAM: A qubit's quantum state depicted as a sphere (Bloch sphere representation, simplified) gradually losing coherence over time — clear sphere becoming blurry, then collapsing to a classical bit. Timeline labels: 'coherent state,' 'partial decoherence,' 'classical noise.' Caption: Decoherence is the loss of quantum information to the environment. Every computation must complete inside the coherence window.] -->

---

## The six terms

Three concepts are enough to understand *why* quantum computing is hard. Six terms are enough to evaluate *whether a specific claim is real*.

**1 and 2. Physical qubit versus logical qubit.**

A physical qubit is the actual hardware device — a superconducting junction, a trapped ion, a photon, a spin. It is noisy and it decoheres. A logical qubit is an error-corrected abstraction built from many physical qubits arranged so that the collective survives even as individual components fail. The analogy is a RAID storage array: many unreliable disks combined into one reliable volume through redundancy and error correction. The exchange rate between physical and logical qubits is brutal — getting one good logical qubit can cost hundreds to thousands of physical ones, depending on the hardware's noise level and the error correction code being used.

This is why "1,000 physical qubits" might represent *zero* logical qubits. If the physical error rate is too high, no amount of adding more physical qubits helps; you are below the threshold where error correction works in the right direction. The investor-relevant count is always logical qubits. Physical qubit count, quoted alone, is a marketing number.

**3 and 4. Physical error rate versus logical error rate.**

The physical error rate is how often a single hardware operation — a gate, a measurement — fails. Today's best hardware sits around one in a thousand (10⁻³) per operation; the engineering ceiling for most physical approaches is thought to be around one in ten thousand (10⁻⁴). The logical error rate is how often the error-corrected, encoded qubit fails. Useful algorithms need logical error rates of at least one in a million (10⁻⁶); the hardest problems want far lower.

The landmark result of 2024 was Google demonstrating that its error correction code worked *in the right direction*: adding more physical qubits to a logical qubit drove the logical error rate down, crossing what physicists call the "below-threshold" line. This was the first convincing experimental demonstration that the scheme scales. It does not mean the problem is solved — the logical error rates achieved are still far from what practical algorithms need — but it confirmed that the error correction approach is not fundamentally broken.

**5. Gate fidelity.**

A gate is one elementary operation on one or two qubits. Fidelity is how accurately it executes: a gate fidelity of 99.9% means one in a thousand operations introduces an error. The difference between 99.9% and 99.99% looks small — a tenth of a percent. In practice it is enormous, because fidelity compounds like interest in reverse over a long computation.

Consider a circuit of ten thousand gates. On a machine with 99.9% fidelity, the probability that every gate succeeds is 0.999 raised to the ten-thousandth power — which works out to something vanishingly small. On a machine with 99.99% fidelity, the same calculation yields a number that is still workable. IonQ's own estimate is that the gap between three-nines and four-nines fidelity amounts to roughly a ten-billion-fold difference in end-to-end performance over a deep circuit. Higher native fidelity also reduces the physical-to-logical overhead — fewer physical qubits are needed per logical qubit to hit a given logical error rate target.

<!-- → [CHART: Line chart showing cumulative success probability vs. circuit depth for two machines — 99.9% fidelity and 99.99% fidelity per gate. X-axis: number of gates (1 to 10,000). Y-axis: probability all gates succeed (log scale). The two lines diverge dramatically. Caption: Fidelity compounding. At 99.9% per gate, a 10,000-gate circuit has a near-zero probability of running clean. At 99.99%, the same circuit remains workable. The difference between three nines and four nines is not a rounding error — it is the difference between a usable machine and one that cannot run the algorithm.] -->

The caveat that always accompanies a fidelity announcement: a record on a single two-qubit gate pair is not a demonstration that the whole machine runs at that fidelity. When you see "four nines," the question to ask is: on what, and at what scale? A single-pair record is a starting line, not a finish.

**6. BQP versus BPP — why advantage is problem-specific.**

BPP is the set of problems a classical computer can solve efficiently. BQP is the set a quantum computer can solve efficiently. It is believed — but not proven — that BQP contains problems outside BPP; integer factoring is the canonical example. This distinction matters: the advantage is not general. A quantum computer is not simply a faster classical computer across all tasks. It is a machine with a different capability profile, one that dramatically outperforms classical hardware on a short, structured list of problem types and offers little or no advantage on everything else.

The unproven status of BQP ≠ BPP is not a technicality to wave away. It means that "quantum advantage" rests on a conjecture — a very well-supported conjecture, but a conjecture. The field operates under the practical assumption that the advantage is real because no one has found an efficient classical algorithm for factoring, and decades of effort have not produced one. But the theoretical foundation is not settled mathematics. State the advantage as well-evidenced conjecture, not established fact.

<!-- → [DIAGRAM: Venn diagram showing BPP inside BQP, with the region outside BPP but inside BQP labeled 'believed quantum advantage — includes factoring, simulation.' Annotation: 'BQP ≠ BPP is well-supported conjecture, not proven.' Caption: Quantum advantage is not general — it applies to a specific set of problem types, and the theoretical separation between classical and quantum tractability is believed but not proven.] -->

---

## Reading a claim

Take a generic announcement: *Company X unveils 1,000-qubit quantum computer, a world record.* Now restate it in the six terms. How many logical qubits? Unstated. Physical versus logical error rate? Unstated. Coherence time? Unstated. Gate fidelity at that scale? Unstated. Four of the six critical numbers are missing; the only number provided is the one the engineers abandoned. The announcement is marketing.

Contrast Google's 2024 below-threshold result. It named the right quantity — logical error rate. It showed the right direction — down with scale. It ran on a documented experiment with transparent methodology, published in *Nature* and reviewed by independent researchers. It specified the code used, the number of physical qubits per logical qubit, and the conditions under which the result held. A reader who knew the six terms could assess every critical dimension. A reader who knew only qubit count could not assess anything.

The difference between the two announcements is invisible without the vocabulary and obvious with it. That is what the vocabulary is for.

---

## What to watch for

Three signals that something real is happening:

**Logical error rates trending toward 10⁻⁶ and below** — on real machines, in reported experiments, not in simulation or roadmap projections. The below-threshold crossing in 2024 was a milestone; the next milestone is reaching logical error rates low enough to run a practically useful algorithm.

**Coherence times extending into the milliseconds across full processor arrays** — not just on a single hand-picked qubit in isolation. Coherence time in a real computation reflects the noisiest qubit in the chain, not the best.

**Gate fidelity above 99.99% demonstrated at scale** — across many qubits in a working processor, with the scope stated explicitly. "At scale" is the whole point of the claim; a two-qubit record with no system context is a data point, not a product announcement.

## What to ignore

Physical qubit counts quoted without logical error rates. "World record" announcements that do not specify what was measured and at what scale. Comparisons to classical computers that do not name the specific problem and the specific classical baseline. Any claim that does not distinguish physical from logical qubits. That last screen alone eliminates most of the hype in the sector.

---

The vocabulary in this chapter is a filter, not a formula. It will not tell you whether a company is worth investing in; nothing will do that reliably. What it will do is let you read a press release, find the numbers that matter, and notice when they are conspicuously absent. An investor who cannot tell a physical qubit from a logical one is reading the wrong number. An investor who does not understand how fidelity compounds will not grasp why a tenth of a percent per gate matters catastrophically at scale. An investor who does not know BQP from BPP will not understand why "quantum computers will solve everything faster" is not a claim the physics supports.

Chapter 3 takes this vocabulary and applies it to the landscape of specific problem types — what quantum hardware is actually suited to attack, and how to evaluate whether a proposed application sits inside that list or outside it.

---

## Further Reading

- **"Four Myths About Quantum Computing" (introtoquantum.org)** — A short, purpose-built debunking of the "tries everything at once" and related misconceptions, written for non-physicists and free to read. [introtoquantum.org/essentials/myths/](https://introtoquantum.org/essentials/myths/)
- **John Preskill, "Quantum Computing in the NISQ Era and Beyond" (arXiv:1801.00862, 2018)** — The independent academic source that named the "noisy intermediate-scale quantum" era; the conceptual framing for why today's machines are limited. [arxiv.org/pdf/1801.00862](https://arxiv.org/pdf/1801.00862)
- **Google Quantum AI et al., "Quantum error correction below the surface code threshold" (*Nature*, 2024)** — The primary source for the logical-versus-physical breakthrough. The *Quanta Magazine* write-up is the accessible companion. [nature.com/articles/s41586-024-08449-y](https://www.nature.com/articles/s41586-024-08449-y)

---

*This handbook is a framework document, not financial advice. Company names are illustrative examples, not recommendations, and may age quickly.*

---

## Exercises

**Warm-up**

1. *(Basic recall — tests understanding of physical vs. logical qubit distinction)*
A press release announces a "500-qubit quantum processor." What single follow-up question should an investor ask before treating this number as meaningful? Explain what the answer would reveal.

2. *(Basic recall — tests understanding of decoherence)*
In your own words, define coherence time and explain why it sets a ceiling on computation depth. What does it mean for a computation to "finish inside the coherence window"?

3. *(Basic recall — tests understanding of superposition)*
The claim "a qubit tries all answers simultaneously" is widely repeated and widely wrong. What does it get right, and what does it miss? What is the correct description of what superposition contributes to a quantum computation?

**Application**

4. *(Fidelity compounding — tests ability to apply the concept to a novel comparison)*
Machine A runs two-qubit gates at 99.5% fidelity. Machine B runs them at 99.9%. A proposed algorithm requires a circuit depth of 5,000 two-qubit gates. Without computing exact values, explain qualitatively what happens to the cumulative error probability on each machine, and what this implies for whether either machine can run the algorithm reliably.

5. *(Claim evaluation — tests ability to apply the six-term filter)*
You receive an analyst note that reads: "Company Y has achieved a coherence time of 1.2 milliseconds on its new chip, a 40% improvement over last quarter." Is this a meaningful datapoint, an incomplete one, or a misleading one? What additional information would you need to assess whether this represents genuine progress?

6. *(BQP/BPP framing — tests understanding of where quantum advantage applies)*
A startup claims their quantum system will "dramatically accelerate" logistics optimization for a major retailer. What question about the mathematical structure of logistics optimization would you ask before evaluating this claim? What answer would make the claim plausible, and what answer would make it implausible?

**Synthesis**

7. *(Connecting error correction and the physical/logical distinction)*
Explain in your own words the relationship between physical error rate, logical error rate, and the physical-to-logical qubit overhead. Why does a machine with a lower physical error rate require fewer physical qubits per logical qubit? What does "crossing the threshold" mean in this context, and why did Google's 2024 result matter?

8. *(Full filter applied to a realistic scenario)*
Draft a two-paragraph analysis of the following announcement using all six terms as a checklist: *"QuantumCo today announced its Apex-2 processor achieves 99.99% two-qubit gate fidelity, a new world record. The system contains 127 physical qubits and operates at 15 millikelvin."* What does the announcement establish, what does it leave unaddressed, and what would you need to know before treating it as evidence of practical quantum advantage?

**Challenge**

9. *(Open-ended — engages the contested nature of quantum advantage)*
The theoretical claim that BQP ≠ BPP — that there exist problems quantum computers can solve efficiently that classical computers cannot — is well-supported conjecture, not proven mathematics. Design a due-diligence question for a potential quantum investment that would be answered differently depending on whether this conjecture is eventually proven true versus false. What does this exercise reveal about how to hold quantum advantage claims with appropriate epistemic weight?
