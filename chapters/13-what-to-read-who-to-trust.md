# Chapter 13 — What to Read, Who to Trust

*A credibility hierarchy and a two-step decision rule you can run from your phone.*

A quantum headline hits your feed. A company has achieved "quantum advantage," or "quantum utility," or a "beyond-classical" result, and the stock is moving. You have maybe five minutes before the move is over, and you cannot personally evaluate the physics. Nobody who isn't a working quantum information theorist can. The journals are paywalled, the papers are dense, and even if you had them open in front of you, the mathematics would take days to check.

So the question you actually need to answer is not "is this claim true?" It is the more tractable one: *whose interpretation of this claim should I trust before I act?*

The answer exists, and it is more systematic than it might seem. The key insight is one Carl Bergstrom and Jevin West offer in *Calling Bullshit*, their field guide to the data-driven variety of nonsense: you almost never need to open the black box. You do not need to understand the neural network to know that an algorithm trained on dating-site photos probably learned to detect smiles, not sexuality. You evaluate what goes in and what comes out, and you ask the oldest question in skepticism: *who benefits?*

Quantum claims are an extreme case of a black box — the physics is genuinely beyond most readers — which makes the "who benefits" question not a shortcut but the whole game. A vendor's chief scientist may be brilliant and still have a structural incentive to frame a result favorably, because their equity depends on the story. Bergstrom and West borrow Harry Frankfurt's distinction between lies and bullshit: a lie is meant to lead you away from the truth, but bullshit is produced with indifference to whether it is true, because the goal is simply to persuade. Vendor significance-claims are rarely lies in the ordinary sense. They are frequently, in this precise technical sense, the other thing.

There is a tempting objection: the company built the machine, so surely they understand it best. This is true about the engineering. It is false about the significance claim. Whether a result was hard to build and whether it represents a genuine advantage over the best available classical method are two different questions, and the incentive is compromised only on the second. Think of it as a recusal rule. You do not ask the defendant's lawyer whether the defendant is guilty. The vendor is counsel for one side. The Flatiron Institute is opposing counsel, whose professional job is to break the claim by reproducing it classically. Aaronson and Preskill are expert witnesses with no stake in the verdict. The tier hierarchy below is that recusal rule made explicit.

<!-- → [DIAGRAM: Four-tier pyramid — Tier 1 at top (smallest, highest credibility): independent academics, no equity; Tier 2: peer-reviewed journals, government bodies; Tier 3: vendor materials, analyst notes; Tier 4 at base (widest, lowest): red-flag phrases. Axis label on right: "Financial stake in the answer being yes" — arrows pointing downward as stake increases. Caption: "Sort by incentive first, evidentiary standard second."] -->

---

**Tier 1: High credibility — independent academics with no equity in the outcome.**

Scott Aaronson holds the Schlumberger Centennial Chair in Computer Science at the University of Texas at Austin — not MIT; he moved to UT Austin in 2016, and any source still calling him an MIT professor is stale. He runs a blog called *Shtetl-Optimized*, which has become the field's central public forum and the single most investor-accessible "is this real?" voice anywhere. His recent posts openly weigh the possibility that the skeptic Gil Kalai turns out to be right — the possibility, that is, that scalable quantum computation may face fundamental physical obstacles not yet fully understood. That willingness to state his own uncertainty is a feature, not a weakness. Calibrated doubt is exactly what you want from someone whose job is to tell you what he actually thinks. Read *Shtetl-Optimized* whenever a quantum claim moves a stock. Its silence on a "breakthrough" is itself information.

John Preskill is at Caltech, widely cited as the Richard P. Feynman Professor of Theoretical Physics [verify current title]. He coined two terms that belong in every investor's vocabulary. The first is **"quantum supremacy"** — the threshold at which a quantum processor performs a task no classical machine can match in practical time. The second, from a 2018 paper, is **"NISQ"**: Noisy Intermediate-Scale Quantum, the descriptor for every machine that currently exists. NISQ means these devices are not fault-tolerant. They perform computations that decohere quickly and cannot be extended indefinitely. The word NISQ is the field's own admission of its current limits, and when a vendor glosses over the NISQ-versus-fault-tolerant distinction, they are blurring a line that Preskill — the person who drew it — considers fundamental. Downgrade any claim on Preskill's own terms when it treats the distinction as cosmetic.

The Flatiron Institute's Center for Computational Quantum Physics sits inside the Simons Foundation and has no equity in any quantum computing company. Its job, in relevant contexts, is to attempt the classical simulation — to ask whether the problem a quantum machine just solved can also be solved classically. In May 2026, working with Boston University, the group published in *Science* a classical algorithm that efficiently simulates large-scale quantum-annealing dynamics, work widely read as erasing a D-Wave "beyond-classical" claim. [contested — D-Wave disputes the relevance of the classical comparison; treat as a strong peer-reviewed classical response rather than a total refutation. Both the Flatiron result and D-Wave's objection are real.] Flatiron does not always respond quickly, and its silence is not an endorsement — but when it does respond, the response is independent and technically rigorous. It is opposing counsel doing its job.

The National Quantum Computing Centre at Harwell in the UK — a roughly £93 million government facility opened in 2024 — is a non-commercial, hardware-agnostic benchmarking body. It has no share price to defend. An NQCC assessment of whether a piece of hardware does what it claims is the kind of independent technical check the investment community should be demanding from somewhere and largely isn't.

---

**Tier 2: Medium credibility — filtered by publication standard.**

Peer-reviewed papers in *Physical Review Letters*, *Nature Physics*, and *Science* carry genuine evidentiary weight. The peer-review process is not perfect — the Google Sycamore "supremacy" result of 2019 passed peer review and was subsequently matched classically — but it at least requires methodological transparency that press releases do not. Government national-quantum-strategy documents reveal timeline expectations honestly, because governments plan conservatively and have no incentive to overpromise. Independent resource-estimation papers — the kind that calculate how many logical qubits and how many gate operations a given real-world application would actually require — are among the most useful documents in the field and among the least cited in the financial press.

---

**Tier 3: Low credibility — read, but require adjudication.**

Vendor roadmaps. Ecosystem partners selling cloud access. Financial analyst notes on quantum stocks, most of which are written by people who cannot evaluate the physics and are therefore doing pure sentiment analysis on a sector they frame as technical. "Quantum utility" press releases. None of these are worthless — they are inputs. But they need Tier-1 adjudication before they move you. The key instruction from Bergstrom and West: read Tier-3 material the way you would read a defense attorney's opening statement. Look for the facts they cannot avoid stating; discount their characterization of those facts. The characterization is what you outsource to Tier 1.

---

**Tier 4: Red flags — checkable physics tells, not vibes.**

These are specific phrases that indicate a claim is probably inflated. Each one is checkable from the language of the release, with no physics background required.

*"Quantum AI" as the primary value proposition.* This is almost always the quantum-plus-LLM thesis, which the dequantization literature has dismantled (Chapter 4). Three independent structural objections. Any one is fatal. A company leading with this in 2026 either has not read the literature or is counting on you not to have.

*A raw qubit count with no logical error rate.* "1,000 qubits" with no error-rate disclosure is less informative than 96 logical qubits with documented below-threshold behavior. More noisy physical qubits can make a machine worse, not better — they add more opportunities for errors to accumulate. The unqualified count is designed to impress rather than inform.

*"Beyond classical" with no named classical method.* Unfalsifiable by construction. "We beat a classical computer" requires you to ask: which classical computer, running which algorithm, on which problem? Bergstrom and West's sharpest instruction — *demand the comparison group* — applies here directly. If a claim will not name what it beat, there is nothing to verify and nothing to contest.

*A 2D planar superconducting grid claiming volume-law entanglement.* This is a physics contradiction you can spot without a physics degree, because the architecture and the claim are simply inconsistent. A shallow circuit on a flat, nearest-neighbor lattice is bounded by the area law of entanglement (Chapter 3): the quantum correlations it can generate are bounded by the surface area of the region, not its volume. A circuit that cannot physically create volume-law entanglement cannot have done what a volume-law entanglement claim requires. The architecture contradicts the announcement.

*Any claim that does not distinguish physical qubits from logical qubits.* The most common single inflation in the field. A logical qubit is built from many physical qubits, with error correction running underneath it; a physical qubit is a raw, noisy component. A thousand physical qubits at a 1-in-100 error rate cannot run a deep useful algorithm. Ninety-six logical qubits with documented below-threshold behavior can be far more powerful. Conflating the two is not a simplification for a general audience — it is the rhetorical move that makes a machine look orders of magnitude more capable than it is.

<!-- → [TABLE: Red-flag phrase checklist — two columns: "Phrase or pattern" | "What to ask" — rows: "Quantum AI" | Did you read Chapter 4?; "N qubits" (no error rate) | Physical or logical? What is the logical error rate?; "Beyond classical" (no named baseline) | Which classical method, which machine, which problem?; "Volume-law entanglement" (planar superconducting) | Does the geometry permit this?; No physical/logical distinction | What is actually being counted? Caption: "Four checks, thirty seconds, no physics required."] -->

---

The worked example is the 2026 D-Wave episode, and it is worth walking through slowly because it illustrates the full decision rule under real conditions.

D-Wave announces a result framed as far beyond the reach of any classical computer — in the vendor's framing, something a supercomputer would take on the order of a million years to reproduce. The stock moves. Now run the framework.

The announcement is a Tier-3 vendor claim. Does it name the specific best-available classical method it beat? The decision rule has two steps: Did a Tier-1 independent comment? Did Flatiron post a classical response? In this case, Flatiron published a classical algorithm in *Science* that simulated the dynamics efficiently. D-Wave contested the relevance of the classical comparison. Both of those things are true simultaneously.

The investor's takeaway is not "the result was fake." D-Wave's engineering achievement may be exactly what they say it is. The takeaway is: *this is precisely the situation the decision rule is built for.* A Tier-3 vendor claim. A strong but contested Tier-1 classical response. No Tier-1 consensus yet. Therefore: no basis for trading on the announcement day. You stand down and let the dispute resolve.

Contrast that with the hypothetical that would pass. A result published in *Nature Physics* (Tier 2), on a problem of genuine economic relevance, naming the exact classical method it beat, distinguishing logical from physical qubits, commented on approvingly by Aaronson on *Shtetl-Optimized*, and left unmatched by Flatiron for eighteen months. That is the profile of a claim worth acting on. The difference between the two cases is not the size of the headline number. It is whether the independent, no-stake adjudicators have weighed in and the claim survived.

<!-- → [DIAGRAM: Two-path flowchart from "Quantum claim hits your feed" — left path: "Tier-3 vendor claim → Tier-1 commented? → Flatiron responded?" → "Contested: stand down"; right path: "Tier-2 publication → Tier-1 endorsed → no classical match after 18 months" → "Profile worth acting on." Caption: "The two-step decision rule applied to two real cases."] -->

---

Bergstrom and West close *Calling Bullshit* with a line from Neil Postman that deserves the last paragraph of this chapter: the chief source of bullshit you have to contend with is yourself. A claim that confirms your existing thesis — that the company you own just proved it is years ahead, that the technology is arriving on the schedule you need — deserves *more* scrutiny than one that challenges it, not less. Confirmation bias does not feel like bias from the inside. It feels like recognition.

The practical protection against it is the recusal rule: route every claim through sources with no equity in the answer, before you act. The hierarchy is fast to apply and almost entirely free. Aaronson's blog is public. Flatiron's publications are indexed. The two lookups together take ten minutes.

That is the decision rule. One axis of the five-metric architecture table (Chapter 7), two independent lookups, and the four red-flag checks. The physics may be a black box. The epistemology does not have to be.

---

## Further Reading

- **Carl T. Bergstrom and Jevin D. West, *Calling Bullshit: The Art of Skepticism in a Data-Driven World*** (Random House, 2020) — the accessible toolkit behind this chapter: who benefits, demand the comparison group, and you rarely need to open the black box.
- **Scott Aaronson, *Shtetl-Optimized*** — [scottaaronson.blog](https://scottaaronson.blog). The independent academic source itself — the highest-signal free running commentary on whether a quantum claim is real, written by someone with no equity and a scrupulous habit of stating his own uncertainty.
- **John Preskill, "Quantum Computing in the NISQ Era and Beyond," *Quantum* 2 (2018): 79** — the primary source that named the era and drew the line between noisy current machines and the fault-tolerant future. The distinction every Tier-4 claim tends to blur.

---

## Exercises

**Warm-up**

1. *(Basic recall)* Name the four tiers of the credibility hierarchy. For each tier, state the primary reason it sits where it does — not the names of sources, but the structural principle that places a source in that tier. *What this tests: whether you understand the logic of the hierarchy, not just its contents.*

2. *(Basic recall)* List the four Tier-4 red-flag patterns. For each one, state the specific question you should ask when you encounter it. *What this tests: whether you can apply the checklist from language alone, without evaluating the underlying physics.*

3. *(Basic recall)* Bergstrom and West distinguish lies from bullshit. State the distinction in your own words, and explain why vendor significance-claims tend to be the latter rather than the former. *What this tests: whether you have the epistemological framework the chapter builds on.*

**Application**

4. *(Translation)* A press release reads: "Our 2,048-qubit processor completed in four minutes a computation that would take the world's fastest supercomputer 10,000 years." Apply all four Tier-4 red-flag checks to this sentence. Which flags fire, and what is the specific information missing in each case? *What this tests: running the checklist on a realistic marketing claim.*

5. *(Translation)* You see a quantum news item: *Shtetl-Optimized* has not posted in two weeks; no Flatiron publication addresses the result; the claim appeared in a vendor press release. Walk through the two-step decision rule and state your conclusion. Then state what additional information would change that conclusion. *What this tests: applying the decision rule in conditions of silence, not just contradiction.*

6. *(Translation)* A financial analyst publishes a note raising her price target on a quantum stock based on a "landmark result." Using the tier framework, explain why the analyst's note is a Tier-3 input regardless of her credentials, and what you would need from Tier-1 sources before taking the note seriously. *What this tests: the principle that tier placement follows incentive structure, not credential level.*

**Synthesis**

7. *(Cross-chapter)* The D-Wave episode involves a strong Tier-1 classical response that the vendor contests. Apply the three-layer test from Chapter 1 to this situation: at Layer 1, what does Flatiron's result establish? At Layer 2, what remains genuinely unresolved? At Layer 3, what does the ongoing dispute imply about the appropriate pricing response on the day of the announcement? *What this tests: integrating the credibility hierarchy into the investment framework.*

8. *(Cross-chapter)* The chapter argues that Aaronson's willingness to openly consider the skeptic Gil Kalai's position — that scalable quantum computation may face fundamental physical obstacles — is a feature of Tier-1 credibility, not a weakness. Explain why calibrated uncertainty increases rather than decreases the value of a source, using the contrast with vendor certainty claims as your example. *What this tests: understanding why epistemological honesty is a credibility signal.*

**Challenge**

9. *(Open-ended)* Bergstrom and West argue the chief source of bullshit you face is yourself. Apply this to a quantum investor who has already built a position in a hardware pure-play: describe the specific cognitive distortions that make it harder for them to apply the credibility hierarchy correctly to news about their own holdings, and propose a concrete procedural rule — not an attitude, a procedure — that would reduce the bias. *What this tests: applying the epistemological framework to the hardest case, which is your own motivated reasoning.*
