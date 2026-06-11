# Chapter 1 — The Honest Starting Point

*The science is real. The stocks are not priced for the science.*

In the spring of 2026, something strange happened in the quantum computing sector. Over a handful of sessions in April, the stock prices of IonQ, D-Wave, Rigetti, and Quantum Computing Inc. ran hard — the kind of move that shows up on brokerage apps' trending lists and gets a cable-news segment and makes your friend who is up 200% on something he cannot quite explain seem very wise. Then in May, in a single day, all four names dropped high single digits. IonQ fell 7%. D-Wave dove 8%. Rigetti and Quantum Computing Inc. plunged 9%. The financial press called it routine profit-taking.

Nothing changed in any laboratory that week. No experiment failed. No result was retracted. The physics was identical on the day the stocks peaked and on the day they fell. What moved was a story — and the story had gotten ahead of itself, as stories about new technologies usually do.

Here is the question that story leaves you with: *Is quantum computing a real investment opportunity, or is it pure hype?*

I want to give you a useful answer, which means I cannot give you a simple one. The honest answer is: both, simultaneously, for different reasons and on different timelines. The underlying physics is real and demonstrably advancing. The near-term commercial narrative — the part that actually moves the stocks — is mostly wrong. You can hold "the science is real" and "the stocks are overvalued" in the same hand without contradiction. Learning to do so is the single most valuable thing this handbook teaches.

<!-- → [CHART: Timeline showing the April–May 2026 quantum equity round-trip — line chart with IonQ, D-Wave, Rigetti, QUBT plotted across April 1–May 31, 2026, annotated at peak and single-day drop. Caption: "Nothing changed in the labs. What moved was a story."] -->

---

The cost of getting this question wrong runs in two directions, and most people only guard against one of them.

The obvious failure is buying the hype: paying a bubble-grade price for a technology whose payoff is a decade away, then watching the position fall 70% on a sentiment reversal that had nothing to do with science. The April–May round trip is a small illustration of a larger possibility. It is not hard to imagine a more serious version.

The less obvious failure is dismissing the sector as a scam and stopping there. This is the reflexive cynic's move, and it is just as expensive. The technology is genuinely real. A credible — if distant — commercial application exists. An investor who decided in 2026 that "quantum is just the next crypto" and switched off her attention would have abandoned the one faculty that actually matters in a slow-developing story: continuous, informed watching.

What makes the cynicism seductive is that it feels like sophistication. But the cynicism that says "the stocks are overpriced, therefore the technology is fake" is making the same logical error as the hype that says "the technology is real, therefore the stocks are cheap." Both collapse three separate questions into one. The discipline that protects against both failures is to refuse that collapse — to answer the three questions separately, in order, and to keep their answers from bleeding into each other.

<!-- → [DIAGRAM: Three stacked horizontal layers labeled Layer 1: Physics, Layer 2: Commercial Timeline, Layer 3: Equity Pricing — with arrows showing the direction of common errors (Layer 1 evidence leaking into Layer 3 conclusions). Caption: "The three-layer test: strong evidence at one layer tells you nothing about the layer below."] -->

---

**Layer 1** asks: Is the underlying physics real? Does the device do something genuinely quantum, reproducibly, in a way that independent experts accept?

This layer is mostly settled. The answer is yes.

Let me say what I mean by that, because "quantum" gets used to mean at least three different things in the financial press, and only one of them is the layer we are checking here.

A quantum computer exploits two phenomena that have no classical analogue. The first is *superposition*: a quantum bit — a qubit — can exist in a combination of 0 and 1 simultaneously, not as an average, but as a genuine quantum state that collapses only when measured. The second is *entanglement*: two qubits can be correlated in a way that has no classical explanation, such that a measurement on one instantly determines the state of the other regardless of the distance between them. A quantum computation works by carefully orchestrating these states across many qubits so that interference — the same wave phenomenon that makes noise-canceling headphones work — amplifies the paths that lead to the right answer and suppresses the paths that lead to wrong ones. When it works, certain classes of problem become tractable that would require more steps than there are atoms in the universe to solve classically.

The engineering problem is that qubits are fragile. Any interaction with the environment — a stray photon, a vibration, a temperature fluctuation — collapses the quantum state before the computation can finish. This is called *decoherence*, and it is the central obstacle the field has been fighting for thirty years. The question that separates serious from unsupported Layer-1 claims is: how well is the field actually fighting it?

In 2024, Google's "Willow" processor produced the most significant Layer-1 result to date. The team demonstrated *below-threshold error correction*: as they added more physical qubits to protect a single *logical* qubit, the logical error rate went *down* rather than up. This does not sound dramatic until you understand what it means. Every error-correction scheme in principle promises to suppress errors by adding redundancy — if one qubit misfires, the others vote it down. But in practice, adding more qubits also adds more opportunities for errors, and for most of the field's history, the second effect had dominated the first. The Willow result was the first convincing evidence that the error-correction math wins at scale. It is a threshold result, and crossing it matters ([Google Quantum AI, 2024](https://www.nature.com/articles/s41586-024-08449-y)).

In 2025, IonQ reported 99.99% fidelity on a two-qubit gate — meaning a single elementary operation on two qubits was performed correctly 9,999 times out of 10,000 ([Quantum Computing Report, 2025](https://quantumcomputingreport.com/ionq-achieves-99-99-two-qubit-gate-fidelity-using-electronic-qubit-control-technology/)). *Fidelity* is how accurately a gate operation is performed; *two-qubit gate* is one elementary step in a quantum circuit. Four-nines fidelity on a single gate is a genuine engineering achievement. The important caveat — and it matters for how you carry this forward — is that it is a record on an individual isolated gate, not a demonstration that such fidelity holds across a whole machine running a full algorithm. Do not read it as "four-nines at scale" [verify scope of any future at-scale claim].

Layer 1, then, is not a question. The phenomena are real. The engineering is advancing in the direction the theory requires. Anyone who tells you quantum computing is physically impossible is wrong.

---

**Layer 2** asks: Does the physics translate into commercial advantage on a timeline you can actually underwrite?

This is the layer where nearly every investment claim in the financial press dies quietly.

Real physics is necessary but nowhere near sufficient for a good investment. A device can be unimpeachably quantum and still have no economically useful task it can perform faster than a classical computer for another fifteen years. The history of technology is full of real inventions with terrible early equities. The airplane was invented in 1903. A profitable airline industry arrived decades later. The invention and the investment were two very different things separated by a very long time.

The honest forecasts cluster far out. Boston Consulting Group's analysis frames a "noisy intermediate-scale" era — the era we are currently in — running to roughly 2030, broad quantum advantage emerging across 2030–2040, and full fault tolerance later still. Their projected economic value of up to $450–850 billion lands in *2040*, not 2026 ([BCG, 2024](https://www.bcg.com/press/18july2024-quantum-computing-create-up-to-850-billion-of-economic-value-2040)). McKinsey's 2026 *Quantum Technology Monitor* calls the present moment a "commercial tipping point," but the tipping is in enterprise pilots and roadmaps, not in advantage-grade machines — and its value figures are modest and back-loaded ([McKinsey, 2026](https://www.mckinsey.com/capabilities/mckinsey-technology/our-insights/mckinsey-quantum-technology-monitor-2026-a-commercial-tipping-point)).

<!-- → [TABLE: Three-column table — Era | Approximate window | What becomes possible — rows: Noisy Intermediate-Scale (NISQ) | present–~2030 | small-scale demonstrations, hybrid classical-quantum pilots; Broad Quantum Advantage | ~2030–2040 | first commercially useful speedups in specific domains; Fault-Tolerant Universal | 2040+ | full error-corrected computation at scale. Source: BCG, McKinsey. Caption: "Every serious independent forecast places commercial advantage a decade or more away."] -->

An investor who buys on a 2026 thesis is buying a 2035-or-later story at 2026 prices. That is not impossible to do profitably, but it requires a very particular kind of patience and a very particular kind of position size — both of which the chapter's final section addresses.

The other thing Layer 2 reveals is a structural fact about how these companies are currently financed. The pure-play quantum names carry large cash balances — IonQ's was reported in the billions in 2026 — raised through equity issuance rather than earned through sales [verify current figures]. That cash hoard is itself informative. It means survival currently depends on the equity-issuance window staying open, which in turn depends on the narrative staying intact. A company that runs on sentiment rather than revenue can stay aloft for years and then reprice violently when sentiment turns. The April–May round trip is a small preview of what a larger sentiment shift could look like.

---

**Layer 3** asks: Is the stock pricing in reality or narrative?

In 2026 the answer is overwhelmingly narrative.

As of mid-May 2026, the financial press reported price-to-sales multiples for the pure-play names in ranges that strain historical comparison. IonQ was reported around 109 times sales. Rigetti and D-Wave were reported anywhere from the high-hundreds into the 800s. Quantum Computing Inc. in similar territory ([Motley Fool, 2026](https://www.fool.com/investing/2026/05/28/quantum-computing-ionq-rgti-qbts-wall-st-warning/)). These figures came from different snapshots on different days and are not mutually consistent; treat them as ranges reported in the financial press, not precise truths, and verify against filings before acting [verify against EDGAR at time of reading].

But even the most generous reading lands well above any historical precedent for a technology stock. The marquee names of the dot-com era topped out around 30–45 times sales — a level that itself proved unsustainable. Triple-digit price-to-sales multiples price in decades of perfect execution at scale in a field where the timeline to scale is genuinely uncertain. They price in the scenario where quantum advantage arrives early, where this specific company is the winner, and where nothing goes wrong. That is an awful lot of conditional clauses.

IonQ's FY2025 revenue was roughly $130 million [verify current figures]. Its market capitalization was in the billions. The growth rate is real — revenue growing several hundred percent year-over-year is genuinely impressive — but the growth rate is off a tiny base, and a growth rate does not justify a multiple unless you believe the base will compound to something very large very soon. The BCG and McKinsey timelines tell you how "soon" independent analysts actually expect "very large" to arrive.

<!-- → [CHART: Bar chart comparing peak price-to-sales multiples — dot-com era marquee names (Pets.com, Webvan, etc.) at 30–45x alongside IonQ at ~109x, Rigetti/D-Wave at 400–800x. Caption: "Even the dot-com era's most speculative multiples were a fraction of what the pure-play quantum names carried in 2026."] -->

---

The power of the three-layer test is that it forces you to say *which* layer you are excited about.

"Google's Willow chip is a breakthrough" is a true Layer-1 statement. It tells you nothing about whether IonQ at 100-plus times sales is a good buy. A real technology can have overpriced stocks. An overpriced stock can eventually earn its valuation. These are separate propositions, and conflating them is how people lose money on real technologies.

Consider NVIDIA's posture toward quantum computing — useful precisely because it is the posture of an organization that understands the technology as well as anyone and has no incentive to flatter it.

The reflexive read of NVIDIA's involvement is: "They are going all-in on quantum, so it must be the next AI." The three-layer test produces a more accurate picture. On Layer 1, NVIDIA clearly believes the physics is real — it built CUDA-Q, a software platform for running hybrid quantum-classical programs across different qubit hardware. On Layer 2, its *actions* reveal genuine uncertainty about commercial timing. Rather than betting the company, its venture arm NVentures took minority stakes spread across three leading hardware approaches: QuEra (neutral atom), Quantinuum (trapped ion), and PsiQuantum (photonic), participating in 2025 funding rounds including Quantinuum's roughly $600 million raise and PsiQuantum's $1 billion Series E ([Global Venturing, 2025](https://globalventuring.com/corporate/investment/nvidia-backs-three-quantum-startups-amid-investment-boom/); [TIME, 2025](https://time.com/7319603/nvidia-ai-quantum-computing/)). One small bet per approach is not conviction that quantum is here. It is the purchase of optionality across a field with no clear winner.

NVIDIA's chief executive said as much, publicly estimating "15 to 30 years" for commercially meaningful quantum as recently as 2024 before softening the language somewhat in 2025. The underlying hedge remained: small positions across multiple architectures, not a large bet on any one of them.

This is a pattern worth naming. In the AI gold rush, NVIDIA sold shovels — compute — to miners who were striking real gold *today*: working models, paying customers, immediate demand. The shovel business and the mine were aligned in time. In quantum, the gold is still mostly theoretical and a decade out. A shovel business in quantum is, for now, selling to prospectors who have not yet found anything. The analogy that NVIDIA's own hedge fits better is not the gold rush but the early aviation industry: real, world-changing technology invented in 1903, and a profitable airline industry that arrived decades later. Real invention. Terrible early equity. NVIDIA is positioned to profit either way; a retail investor paying 100-plus times sales for a pure-play is not.

<!-- → [DIAGRAM: Split diagram — left side: "AI gold rush" with NVIDIA shovels connecting to immediate revenue (miners striking gold today); right side: "Quantum" with NVIDIA optionality connecting to projected revenue circa 2035 (prospectors, gold not yet found). Caption: "NVIDIA is hedging, not betting. The distinction matters."] -->

---

The signals that would actually strengthen the bull case — not press-release noise but structural shifts — are specific and observable.

Watch for NVIDIA's minority stakes becoming something larger. A move from small venture positions to a material acquisition would mean the most sophisticated hardware buyer in the world shifted from hedging to owning. Note that such an acquisition currently faces national-security review hurdles; if it cleared them, that clearance would itself be informative. Watch for sovereign procurement converting into recurring revenue — specifically, multi-year government contracts with named deliverables showing up as renewing revenue lines in earnings reports, not memoranda of understanding or one-off research grants. And watch for architecture convergence: a clear signal that one hardware approach — superconducting qubits, trapped ions, neutral atoms, photonics — is decisively pulling ahead on the metrics that govern error correction would reduce the "we don't know who wins" risk that currently argues for diversification over concentration.

What to ignore is just as important. Raw qubit-count announcements are nearly meaningless without the logical error rate and fidelity at that scale; more noisy qubits can make a machine worse, not better. "Quantum supremacy" or "beyond classical" claims without independent verification deserve skepticism: every major such claim to date has been matched classically within 12 to 24 months. Vendor roadmaps promising *commercial* advantage by 2029 run ahead of every independent forecast. Technical demonstrations may continue on schedule; broad commercial advantage by 2029 is an outlier claim, and it is marketing. And triple-digit revenue growth rates cited without the base are a tell: IonQ's revenue growing several hundred percent year-over-year is real, but it is growing off a tiny base, and the growth rate cannot justify the multiple unless you believe the base compounds to something enormous very soon.

---

The decision rule this chapter argues for is modest and deliberate. Start a small "bookmark" position in the strongest hardware names — small enough that a 50% decline does not hurt, large enough that you pay attention. Use it to build domain knowledge while you wait. Do not size up on the strength of Layer-1 physics alone; size up only when the commercial and verification signals developed later in this handbook actually fire.

That advice will feel unsatisfying to anyone who came here looking for a bold call. But the bold call in quantum investing in 2026 is not "buy everything" or "it's all hype." The bold call is to maintain conviction at Layer 1 while remaining disciplined at Layer 3 — to hold simultaneously that the science is real and that the stocks are not priced for the science. That is the harder position intellectually, and in my experience it is the one that holds up longest.

The three-layer test is the tool. The rest of this handbook is the evidence you need to use it well.

---

## Further Reading

- **Scott Aaronson, "Quantum Computing: Between Hope and Hype" (Shtetl-Optimized blog, 2024)** — [scottaaronson.blog/?p=8329](https://scottaaronson.blog/?p=8329). The best free, investor-accessible counterweight to vendor optimism, written by a leading complexity theorist who is neither a hype merchant nor a cynic.
- **Boston Consulting Group, "Quantum Computing Is On Track to Create Up to $850 Billion of Economic Value by 2040" (2024)** — [bcg.com](https://www.bcg.com/press/18july2024-quantum-computing-create-up-to-850-billion-of-economic-value-2040). The canonical phased timeline from an independent analyst; useful for grounding Layer-2 expectations.
- **Google Quantum AI et al., "Quantum error correction below the surface code threshold" (Nature, 2024)** — [nature.com/articles/s41586-024-08449-y](https://www.nature.com/articles/s41586-024-08449-y). The primary source for the strongest Layer-1 result to date; read the abstract even if the body is technical.

---

## Exercises

**Warm-up**

1. *(Basic recall)* Name the three layers of the three-layer test and state the distinct question each layer asks. *What this tests: whether you can keep the layers separate before applying them.*

2. *(Basic recall)* What is decoherence, and why does it matter for quantum computing hardware? *What this tests: whether you have the Layer-1 vocabulary needed to evaluate technical claims.*

3. *(Basic recall)* What did the Google Willow result demonstrate that prior error-correction experiments had not? *What this tests: your ability to distinguish a threshold result from an incremental one.*

**Application**

4. *(Translation)* A brokerage note claims: "IonQ's revenue grew 300% year-over-year — this validates the bull thesis." Apply Layer 2 and Layer 3 analysis to evaluate the claim. What is missing from the note? *What this tests: whether you can identify which layers a claim actually addresses.*

5. *(Translation)* A vendor announces: "Our machine achieved quantum supremacy on a sampling task." List the follow-up questions you would need answered before updating your Layer-1 view. *What this tests: ability to apply verification criteria to a real-world press claim.*

6. *(Translation)* Describe NVIDIA's quantum investment posture using the three-layer framework. What does its structure of small, diversified minority stakes reveal about its Layer-2 conviction? *What this tests: applying the framework to an observable real-world case.*

**Synthesis**

7. *(Cross-layer reasoning)* An investor says: "The BCG report projects $850 billion in value by 2040, so a $10 billion market cap for IonQ today is cheap." Identify the logical error in this argument and explain which layer it conflates with which. *What this tests: your ability to catch cross-layer contamination in an argument you might find plausible.*

8. *(Cross-layer reasoning)* The chapter argues that companies funded by equity issuance rather than revenue create a structural vulnerability. Explain the mechanism — how does narrative dependence translate into price volatility — and connect it to the April–May 2026 round trip. *What this tests: whether you can trace a structural claim through to an observable price event.*

**Challenge**

9. *(Open-ended)* The chapter uses the aviation analogy: real technology in 1903, profitable industry decades later. Identify one way this analogy strengthens the bear case for near-term quantum equities and one way it might be misleading — what is importantly different about the quantum situation that the analogy does not capture? *What this tests: the ability to stress-test an analogy rather than accept it.*

---

*This handbook is a framework document, not financial advice. Company names are illustrative examples, not recommendations, and figures may age quickly.*
