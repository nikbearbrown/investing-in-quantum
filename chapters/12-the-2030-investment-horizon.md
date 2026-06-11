# Chapter 12 — The 2030 Investment Horizon

*Why the honest answer is not a date, and how to act without one.*

The number 2030 is everywhere in quantum computing. It appears in vendor roadmaps, consultancy reports, executive presentations, and the occasional congressional testimony. When a number appears that consistently, across sources with such different incentives, the natural inference is that it reflects some underlying consensus — that people who know the field have converged on a timeline. I want to show you why that inference is wrong, and then give you something more useful than a date.

The forecasters who cluster around 2030 are not liars. They are doing something subtly different from what they appear to be doing. They are naming a year by which certain *laboratory* milestones might plausibly be achieved — and then allowing that framing to blur into something that sounds like "quantum computing becomes commercially relevant in 2030." These are very different claims. A laboratory milestone is a physics achievement. Commercial relevance is a market achievement. The gap between them is not a matter of months. For genuinely transformative technologies, it has historically been measured in decades.

Nate Silver, in *The Signal and the Noise*, identified the core failure mode of expert prediction in complex domains: "hedgehogs" who commit to one big idea and defend it against accumulating evidence, versus "foxes" who hold many partial models, update constantly, and distrust their own certainty. Quantum timeline forecasts are almost universally hedgehog forecasts — made by people with equity, grants, or reputations attached to a particular answer. What you need is a fox framework, and a fox framework does not center on a date. It centers on a question: *what would I have to observe before I move?*

---

Let me explain why confident dates fail here specifically, because the reason is structural rather than a function of anyone's honesty.

Quantum computing is what you might call a *threshold technology*. Its usefulness does not grow smoothly with hardware improvement the way, say, processor speed scaled with transistor density. It jumps — discontinuously — when a specific condition is met: genuine fault-tolerant operation at a scale sufficient to run an algorithm that matters. Below that threshold, the improvement is real and measurable in the laboratory, but the economic value delivered to the world outside the laboratory is close to zero. Above it, the value could be enormous. The threshold is not a gradient; it is a step.

This makes it extremely difficult to extrapolate from current progress to commercial arrival. A researcher observing genuine, accelerating, below-threshold progress has every reason to feel optimistic and every incentive to translate that optimism into a date. But the date they name is a date by which they expect to *approach* the threshold, not a date by which anything economically important changes. And the distance from "approaching the threshold" to "delivering commercial value" depends on engineering, economics, ecosystem, and adoption dynamics that have nothing to do with the physics, and that no laboratory roadmap captures.

Consider the forecaster spread, which is itself the most useful data point available. IBM's public roadmap describes a system called Starling around 2029 — on the order of 200 logical qubits with 100 million gate operations — followed by a far larger system in the 2033-and-beyond range. McKinsey and BCG analyses cluster first *commercial* advantage around 2035. In one widely cited survey, only about 72 percent of executives expected commercial fault-tolerant computing by 2035 — meaning roughly a quarter of serious practitioners did not. Other analyses push broad, full-scale fault tolerance past 2040. Credible sources spread across more than a decade. That spread is not noise to be averaged into a tidy "2032." It is the signal. When people who understand the field disagree by a decade, the honest investor stops betting on a date and starts gating on a milestone.

<!-- → [CHART: Horizontal scatter plot showing timeline estimates from different sources along an x-axis spanning 2026–2045. Sources plotted: IBM roadmap (Starling ~2029, larger system ~2033+), McKinsey/BCG commercial advantage cluster (~2035), pessimistic academic estimates (~2040+), Kalai/Dyakonov (possibly never). Each source marked with a different symbol and labeled. Caption: "The forecaster spread as signal. When credible sources disagree by a decade, the spread is information — it tells you the honest answer is 'when specific milestones fire,' not a year. Average the cluster at your peril."] -->

---

There is a deeper reason to be humble about dates, and it lives in the laboratory results that are easiest to misread. Multiple platforms have now demonstrated *below-threshold error correction* — logical qubits that get better, not worse, as you add physical qubits, which is the mathematical condition that fault tolerance requires. This is genuine progress. It is not a breakthrough of the kind that changes the commercial picture, and confusing the two is the most common timing error I see in coverage of the field.

Below-threshold error correction proves the *direction* is right. It does not tell you how far away the threshold is. Imagine a runner who has broken four and a half minutes for the mile. That is real progress toward a four-minute mile. It tells you nothing about whether they will achieve it in six months or six years, and it tells you almost nothing about whether they will ever win an Olympic medal, because Olympic medals depend on factors — competition, injury, economics, coaching — that running time does not capture. Below-threshold operation is the four-and-a-half-minute mile. The threshold itself, the commercially relevant algorithm, the economically important result — these are separated from the current position by a distance that the current rate of progress cannot reliably extrapolate.

One more structural complication: the classical baseline is moving. Artificial intelligence is accelerating drug discovery and materials science right now — not in 2030, now. Every year that quantum hardware spends crossing the fault-tolerance threshold is a year in which classical methods improve. The bar quantum must eventually clear to deliver commercial advantage keeps rising. A quantum chemistry calculation that would have been decisive in 2022 may not be decisive in 2032, because the best classical method in 2032 will not be the best classical method of 2022. This moving baseline does not make the quantum thesis wrong, but it means the distance to meaningful advantage is not simply a function of how fast quantum hardware improves — it is a function of that rate minus the rate at which classical alternatives improve.

---

With those cautions in place, a phased framework is more useful than a single date — not because the phase boundaries are known with any precision, but because each phase is defined by what you would have to *observe* before changing your position, rather than by what you hope will happen by a particular year.

The current phase — which is where we are as of mid-2026 — is characterized by sovereign procurement as the revenue floor, genuinely accelerating hardware science, no commercially meaningful quantum advantage anywhere, and a classical AI baseline rising fast. The revenue that exists, including IonQ's roughly $130 million in 2025, is hardware sales, cloud access, and government contracts — a floor built on geopolitical optionality, not commercial fundamentals. This is the right observation to anchor on, because it tells you what the position is actually priced on: not a fundamentals story, but a story about what governments will pay to avoid being strategically unprepared.

The correct position size for this phase is modest — enough to participate if the signal fires, small enough not to damage you if the below-threshold hardware continues improving for years without crossing into commercial relevance. The worst outcome available to a quantum investor is not missing a move. It is paying the holding cost — cash burn, dilution, the carrying cost of a large position — for a decade, only to be right eventually at a price where the time-adjusted return is unexciting.

The phase boundary into the next stage is not a year. It is a pair of signals: a chemical-accuracy result on a real transition-metal complex — a molecule that classical methods genuinely struggle with, not a textbook example like hydrogen or lithium hydride — where the classical comparison is honestly specified and quantum wins, followed by that result surviving independent classical scrutiny for twelve to twenty-four months without being matched. When those two conditions are met, something has changed. Until they are, the phase boundary has not been crossed, whatever the calendar says.

<!-- → [DIAGRAM: Four-phase horizontal flow diagram with signal gates between phases rather than year boundaries. Phase 1 (current): "Hardware science + sovereign floor — bookmark position." Gate 1→2: "Chemical accuracy on hard molecule, survives classical counterattack 12–24 months." Phase 2: "First credible fault-tolerant demonstrations — modest increase." Gate 2→3: "All four breakthrough signals fired (Chapter 8)." Phase 3: "First economically important advantage — meaningful position." Gate 3→4: "Commercial adoption at scale." Phase 4: "Quantum as infrastructure." Each gate labeled with what must be observed, not what year it might arrive. Caption: "The phase framework. Phases are defined by observable signals, not calendar dates. You move when you see the signal, not when the roadmap says you should."] -->

---

The pessimistic scenario belongs in this chapter, and I will not bury it. There is a serious minority scientific position that fault-tolerant quantum computing at useful scale may never be achieved, and it deserves a fair presentation rather than a polite footnote.

Gil Kalai, a mathematician at the Hebrew University of Jerusalem, argues that noise in entangled quantum systems is *correlated* in a way that scales with the computation itself — so that error rates cannot in practice be pushed below the threshold fault-tolerance theory requires. This is not an engineering argument about better hardware. It is a complexity-theoretic argument about a structural wall. The claim is that the very process of running a long quantum circuit generates correlated errors that defeat the error-correcting codes, in a way that getting more physical qubits or lower individual error rates does not fix. Kalai has written about this extensively, including in arXiv:1908.02499, "The Argument against Quantum Computers," and his work is ongoing.

It is important to know that Kalai is not a fringe figure. Scott Aaronson — who thinks Kalai is wrong — has debated him seriously for roughly fifteen years, and the debate is conducted at the highest level of the field on both sides. A second skeptic worth knowing is Michel Dyakonov, a physicist who argues that a many-qubit quantum state is described by an enormous number of continuous parameters, making a quantum computer an irreducibly analog device — and no analog device in the history of engineering has ever been made fault-tolerant in the relevant sense.

The recent below-threshold results, including demonstrations across dozens of logical qubits, are the kind of experimental evidence that pressures Kalai's position. His response is that the wall appears only at larger scales and longer circuits than any current demonstration has reached. As of mid-2026, the dispute is unresolved in either direction [contested — the question of whether correlated noise defeats fault tolerance at scale is genuinely open; below-threshold demonstrations constitute evidence against Kalai but do not close the question].

The bookmark position is sized for the world where the pessimists turn out to be right. It costs you little if they are.

<!-- → [TABLE: Two-column table. Left: Skeptical position. Right: Current experimental evidence. Rows: (1) Kalai — correlated noise defeats fault tolerance at scale / Below-threshold demonstrations on dozens of logical qubits — pressures conjecture, doesn't close it. (2) Dyakonov — analog device argument, continuous parameters / Fault-tolerant codes demonstrated at small scale — does not address the scaling argument. (3) Both — threshold may be unreachable at commercially useful circuit depth / No demonstration of a commercially relevant algorithm at fault-tolerant scale — dispute unresolved. Caption: "Where the skeptical case stands as of mid-2026. The evidence pressures these positions without refuting them."] -->

---

How to read a roadmap is a practical skill worth spending a moment on. IBM publishes the most detailed public roadmap in the sector. The instinct is to treat the dates on it as predictions. They are plans — something quite different. A plan is a hypothesis a company offers about itself, conditional on funding, physics, and execution all going right. The correct use of a roadmap date is to convert it into a test: by around 2029, IBM plans to demonstrate roughly 200 logical qubits. Has an independent party confirmed that milestone was reached? Was the demonstration useful — was it a step toward chemical-accuracy results on hard molecules, or a laboratory demonstration with no near-term economic application? The roadmap is not a forecast; it is a series of testable hypotheses. Your job is to wait for the independent evidence, not to price in the plan.

The dollar figures in consultancy reports deserve even less weight than roadmap dates. A "quantum computing market of $850 billion by 2040" is a Tier-3 projection multiplied by a Tier-3 adoption assumption. Each layer of the calculation compounds the uncertainty of the layer below it. The number that comes out is precise in a way that papers over the genuine uncertainty at each step. Use these figures only as a reminder that the *potential* is large if the technology arrives — not as evidence about when it will arrive, at what cost, or for which companies.

---

## What Would Change My Mind

A chemical-accuracy result on a genuine transition-metal complex — something like iron-sulfur clusters or strongly correlated transition-metal oxides — where the classical comparison was run against the best available methods (not brute-force simulation), the result survived twelve months of independent classical scrutiny without being matched, and a second unaffiliated group reproduced the quantum result on different hardware. That stack of evidence would move me from Phase 1 to Phase 2 with genuine conviction.

On the pessimistic side: a demonstration that noise in a fifty-plus-logical-qubit system is empirically correlated in the way Kalai predicts, rather than independently distributed as fault-tolerance theory assumes, would substantially revise my view of the long-term ceiling.

## Still Puzzling

The part I cannot resolve is the moving classical baseline. I know that the bar quantum must clear keeps rising as classical AI and specialized simulation methods improve. I do not know at what rate the bar is rising relative to the rate at which quantum hardware is improving, and I am not sure anyone does. The gap might be shrinking — quantum hardware improving faster than the classical baseline rises. It might be growing — classical methods accelerating faster than quantum hardware. The answer matters enormously for when Phase 2 arrives, and the honest position is that I do not have a confident estimate of either rate. Track both sides of the race, not just the quantum side.

---

## Further Reading

- **Nate Silver, *The Signal and the Noise: Why So Many Predictions Fail — but Some Don't* (Penguin, 2012).** The methodological backbone of this chapter — the fox-versus-hedgehog framework, the case for calibration over confidence, and why immature fields are exactly where point forecasts fail most reliably.
- **John Preskill, "Quantum Computing in the NISQ Era and Beyond," *Quantum* 2, 79 (2018).** The independent academic statement of why current machines are not fault-tolerant and what it would take to change that — from the physicist who named the era we are in, written without a hardware company's equity stake.
- **Gil Kalai, "The Argument against Quantum Computers," arXiv:1908.02499 (2019).** The primary source for the pessimistic scenario — read it to understand exactly what experimental result would have to appear to seriously challenge his position, and use that as a filter when the next below-threshold headline lands.

---

*This chapter is part of* Investing in Quantum: A Skeptic-First Framework. *It is a framework for evaluating claims, not financial advice. Company names are illustrative examples, not recommendations.*
