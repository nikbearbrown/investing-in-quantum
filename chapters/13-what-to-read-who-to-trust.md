# Chapter 13 — What to Read, Who to Trust

## Decision question

A quantum headline hits your feed. A company has achieved "quantum advantage," or "quantum utility," or a "beyond-classical" result, and the stock is moving. You have five minutes before the move is over, and you cannot personally evaluate the physics — nobody who isn't a working quantum information theorist can. So the practical question is not "is this claim true?" It is the more tractable one: *whose interpretation of this claim should I trust before I act?* This chapter gives you a credibility hierarchy and a two-step decision rule you can run from your phone.

## The short answer

Trust independent academics with no equity in the outcome — principally Scott Aaronson and John Preskill — and trust the Flatiron Institute's classical-simulation group to tell you whether a "beyond-classical" claim survives. Read everyone with a financial stake in the answer skeptically, and treat a handful of specific phrases as outright red flags. Before acting on any quantum news, check whether a Tier-1 independent commented and whether Flatiron has a classical response.

## Why this matters

The single most useful idea in *Calling Bullshit*, Carl Bergstrom and Jevin West's field guide to the data-driven version of nonsense, is that you almost never need to open the black box (Bergstrom & West, 2020). You do not need to understand the neural network to know that an algorithm trained on dating-site photos learned to detect smiles, not sexuality. You evaluate what goes in and what comes out, and you ask the oldest question in skepticism: *who benefits?* Quantum claims are an extreme case of a black box — the physics is genuinely beyond most readers — which makes the "who benefits" question not a shortcut but the whole game.

The cost of getting this wrong is concrete. Every major "quantum supremacy" or "beyond-classical" claim of the past several years has eventually been matched classically, often within months. An investor who traded each announcement on the day it landed would have bought a series of tops. The reason is not that the companies are lying in the ordinary sense. It is that a vendor's chief scientist may be brilliant and *still* have a structural incentive to frame a result favorably, because their equity depends on the story. Bergstrom and West borrow Harry Frankfurt's distinction: a lie is meant to lead you away from the truth, but bullshit is produced with indifference to whether it is true, because the goal is to persuade. Vendor significance-claims are rarely lies. They are frequently, in this precise technical sense, the other thing.

There is a tempting and wrong objection here: *the company built the machine, so surely they understand it best.* This is true about the engineering and false about the significance claim. Whether a result was hard to *build* and whether it represents a genuine advantage over the *best available classical method* are two different questions, and the incentive is compromised only on the second. A useful mental model, borrowed from the courtroom: you do not ask the defendant's lawyer whether the defendant is guilty. The vendor is counsel for one side. Flatiron is opposing counsel, whose professional job is to break the claim by reproducing it on a classical computer. Aaronson and Preskill are the expert witnesses with no stake in the verdict. The tier hierarchy is, in effect, a recusal rule.

## The framework

Sort every source by *incentive first, evidentiary standard second*. The axis that matters is not credentials — it is whether the source has a financial stake in the answer being yes.

**Tier 1 — high credibility: independent academics and labs with no equity.**

- **Scott Aaronson** (Schlumberger Centennial Chair of Computer Science, the University of Texas at Austin — *not* MIT; he moved to UT Austin in 2016, and any source still calling him an MIT professor is stale) runs the blog *Shtetl-Optimized*, the field's central public forum and the single most investor-accessible "is this real?" voice anywhere. He is scrupulous about his own uncertainty — his recent posts openly weigh the possibility that the skeptic Gil Kalai turns out to be right — which is a feature, not a weakness. Calibrated doubt is exactly what you want.
- **John Preskill** (Caltech; [verify] exact current title — widely cited as the Richard P. Feynman Professor of Theoretical Physics and director of IQIM) coined the term **"NISQ"** — Noisy Intermediate-Scale Quantum — in a 2018 paper, and earlier popularized the phrase **"quantum supremacy."** The word "NISQ" is itself a discipline: it is the field's own admission that today's machines are *not* fault-tolerant. If a claim ignores the NISQ-versus-fault-tolerant distinction, downgrade it on Preskill's own terms.
- **The Flatiron Institute's Center for Computational Quantum Physics** (Simons Foundation) is the classical reality check. Its role in this book is the *defender*: in May 2026 the group, with Boston University, published in *Science* a classical algorithm that efficiently simulates large-scale quantum-annealing dynamics — work widely read as erasing a D-Wave advantage claim. [contested — see pantry flag] D-Wave contests such classical results, and Chapter 6 treats this specific case as a *strong, peer-reviewed classical response* rather than a total refutation. Present it that way: Flatiron's result is powerful and independent; it is also disputed by the vendor. Both are true.
- **The National Quantum Computing Centre (NQCC)** at Harwell in the UK — a roughly £93M government facility opened in 2024 — is a non-commercial, hardware-agnostic benchmarking body. A useful independent source for "does the hardware do what is claimed," with no share price to defend.

**Tier 2 — medium credibility.** Peer-reviewed papers in *Physical Review Letters*, *Nature Physics*, and *Science*; government national-quantum-strategy documents (which reveal timeline expectations honestly, because governments plan conservatively); and independent resource-estimation papers that calculate how many qubits a real application would actually need.

**Tier 3 — low credibility, read with caution.** Vendor roadmaps (every company forecasts commercial advantage suspiciously close to its own funding runway); ecosystem partners selling cloud access; financial-analyst notes on quantum stocks (most analysts cannot evaluate the physics); and "quantum utility" press releases. None of these are worthless — they are inputs. But they need Tier-1 adjudication before they move you.

**Tier 4 — red flags, apply heavy discount.** These are not vibes. They are specific, checkable physics tells.

- **"Quantum AI" as the primary value proposition.** Almost always the quantum-plus-LLM thesis, which the dequantization literature has dismantled (Chapter 4).
- **A raw qubit count with no logical error rate.** A 1,000-physical-qubit chip with no error-rate disclosure is *less* informative than a 96-logical-qubit result that publishes below-threshold data.
- **"Beyond classical" with no named classical method.** Unfalsifiable by construction — this is Bergstrom and West's "demand the comparison group" applied directly. If they will not name what they beat, there is nothing to check.
- **A 2D planar superconducting grid claiming volume-law entanglement.** This is physically suspect on its face: a shallow circuit on a flat, nearest-neighbor lattice is bounded by the *area law* of entanglement (the physics from Chapter 3), so it cannot generate volume-law entanglement. The claim contradicts the architecture.
- **Any claim that does not distinguish physical qubits from logical qubits.** The most common single inflation in the entire field.

## What it looks like in practice

Take the canonical worked example: the 2026 D-Wave episode. A vendor announces a result framed as far beyond any classical computer — in this telling, something a supercomputer would take on the order of a million years to reproduce. The stock moves. Now run the framework. The announcement is a Tier-3 vendor claim. Does it name the specific best-available classical method it beat? Run the two-step decision rule. Step one: did a Tier-1 independent comment? Step two: did Flatiron post a classical response? In this case Flatiron did exactly that, publishing a classical algorithm in *Science* that simulated the dynamics efficiently — while D-Wave contested the relevance of the classical comparison. The investor's takeaway is not "the result was fake." It is "this is precisely the situation the decision rule is built for: a splashy Tier-3 claim, a strong but contested Tier-1 classical response, and therefore no basis for trading on the announcement day." You stand down and let the dispute resolve.

Contrast that with a hypothetical that *would* pass: a result published in *Nature Physics* (Tier 2), on a problem of genuine economic relevance, naming the exact classical method it beat, distinguishing logical from physical qubits, commented on approvingly by Aaronson on *Shtetl-Optimized*, and left unmatched by Flatiron for eighteen months. That is the profile of a claim worth acting on. The difference between the two is not the size of the headline number. It is whether the independent, no-stake adjudicators have weighed in and the claim survived.

It is worth practicing the red-flag checks on the *language* of a release, because the tells are in the wording. "A 1,000-qubit processor" with no further qualification triggers the physical-versus-logical flag: a thousand *physical* qubits at, say, a 1-in-1,000 error rate cannot run a deep useful circuit, while ninety-six *logical* qubits with documented below-threshold behaviour can be far more meaningful — so the unqualified count is designed to impress rather than inform. "Beyond the reach of any classical computer" triggers the comparison-group flag: *which* classical computer, running *which* algorithm? Bergstrom and West's instruction is to demand the comparison group every time, and a claim that omits it is unfalsifiable by construction. "Quantum-accelerated AI" triggers the quantum-AI flag and sends you to Chapter 4. And a superconducting chip on a flat grid claiming the kind of richly entangled state that its own geometry forbids triggers the area-law flag — a physics contradiction you can spot without a physics degree, because the architecture and the claim are simply inconsistent. None of these checks requires you to evaluate the result. They require you to read the sentence carefully and ask what it is quietly leaving out.

A note on the temptation to skip all this and just read the company's investor deck. The deck is not useless — it is a Tier-3 input, and it tells you what the company *plans* and *believes*. But it is written by the most interested party in the room, and its job is to persuade you to hold or buy. Read it the way you would read a defence attorney's opening statement: for the facts it cannot avoid stating, not for its characterization of them. The characterization is what you outsource to Tier 1.

## What to watch for

- **A new *Shtetl-Optimized* post on the result.** Aaronson's cadence is reliable; his silence on a "breakthrough" is itself information.
- **A Flatiron classical-simulation paper**, or a credible independent group attempting the match — and how long the result survives the attempt.
- **Whether the announcement distinguishes logical from physical qubits** and **names the classical baseline.** These two checks alone filter most of the noise.
- **NQCC or other national-lab benchmarking** of the hardware in question.

## What to ignore

- **The vendor's own significance claim, taken alone.** Trust their engineering; discount their "what it means."
- **Analyst price targets premised on physics the analyst cannot evaluate.**
- **"Quantum utility" and "quantum AI" framing** until a Tier-1 source has independently endorsed the underlying result.
- **Your own enthusiasm.** Bergstrom and West close their book with Neil Postman's line that the chief source of bullshit you have to contend with is yourself. A claim that confirms your existing thesis deserves *more* scrutiny, not less.

## The decision rule

Before acting on any quantum news, run two lookups. (1) Did a Tier-1 independent — Aaronson or Preskill — comment? (2) Has the Flatiron Institute posted, or is anyone attempting, a classical response? If the claim survives both, it is worth your attention. If either knocks it down, or if neither has yet addressed it, it is too early to act. The rule is fast, public, and free — which is exactly why it works.

## Further reading

- **Carl T. Bergstrom and Jevin D. West, *Calling Bullshit: The Art of Skepticism in a Data-Driven World*** (Random House, 2020) — the accessible toolkit behind this whole chapter: who benefits, name the comparison group, and you rarely need to open the black box.
- **Scott Aaronson, *Shtetl-Optimized* (scottaaronson.blog)** — the independent academic source itself; the highest-signal free running commentary on whether any given quantum claim is real, written by someone with no equity and a scrupulous habit of stating his own uncertainty.
- **John Preskill, "Quantum Computing in the NISQ Era and Beyond," *Quantum* 2 (2018): 79** — the primary source that named the era and drew the line between noisy current machines and the fault-tolerant future, the distinction every Tier-4 claim tends to blur.

---

*This chapter is part of* Investing in Quantum: A Skeptic-First Framework. *It is a framework for evaluating claims, not financial advice. Company names are illustrative examples, not recommendations.*
