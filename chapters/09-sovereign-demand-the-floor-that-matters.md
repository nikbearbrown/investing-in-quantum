# Chapter 9 — Sovereign Demand: The Floor That Matters

*Why these companies have not gone to zero, and how to tell the ones that won't from the ones that will.*

Here is a puzzle that should bother anyone who thinks carefully about valuation. Most quantum hardware companies have negligible commercial revenue. They burn cash at rates that would be alarming in any other sector, sell almost nothing a customer would buy on its own economic merits, and will not produce commercially useful output for the better part of a decade — possibly longer. Under a pure-commercial lens, many of them should trade near zero. They do not. The obvious question is why, but I want to ask a more useful one: how do you tell the companies with a real floor from the companies whose government story is a press release?

The answer is simpler than it sounds, and it turns entirely on one distinction. A multi-year procurement contract with milestone-tied payments and named deliverables is a real demand floor. A memorandum of understanding, a strategic partnership announcement, a letter of intent, a one-off research grant — these are not. Most of what appears in a quantum company's investor materials under the heading "government engagement" is the second kind. Learning to separate them quickly is worth more than anything else in this chapter.

---

Start with why governments are buying at all. The commercial case for quantum hardware is not there yet, and no honest government planner believes otherwise. The planning horizons in the programs that have actually been funded — the UK's ProQure, the US Department of Energy quantum programs, the EU Quantum Flagship — are measured in years toward validation, not months toward deployment. A government that genuinely believed quantum would arrive commercially in 2027 would not run a multi-year prototype-validation program with conservative milestones. The *structure* of the spending reveals the true timeline expectation, and that expectation is long. Heavy government funding is therefore not evidence the technology is nearly ready. It is evidence of something different: that governments have decided they cannot afford to be late.

Two asymmetries explain the spending in ways that have nothing to do with commercial readiness.

The first is cryptographic risk. Shor's algorithm, run on a large fault-tolerant quantum computer, would efficiently factor the large numbers that secure RSA and elliptic-curve encryption — the mathematical foundation of essentially all current digital infrastructure. The threat is asymmetric in time. An adversary can record encrypted traffic today and decrypt it years later, when the capable hardware finally exists. The breach happens before any quantum computer is operational. This "harvest now, decrypt later" dynamic made the risk actionable in the present, even though the threatening machine is still a decade away, and it produced a concrete regulatory trigger: in August 2024, NIST finalized its first three post-quantum cryptography standards — FIPS 203, 204, and 205 — giving US federal agencies an explicit migration mandate.

I want to be precise about what this means for the investment thesis, because it is exactly where analysts go wrong. Post-quantum cryptography is *defensive software spending* — migrating existing systems to new encryption algorithms. It is not a revenue line for quantum hardware makers. It explains why governments have urgency. It does not translate into hardware procurement. Keep it firmly in the "why governments care" column. Do not let it bleed into the "how hardware companies make money" column.

<!-- → [DIAGRAM: Two-column split. Left column headed "Why governments care." Right column headed "What generates hardware revenue." Left: cryptographic risk + harvest-now-decrypt-later timeline + NIST FIPS 203/204/205 mandate. Right: multi-year procurement contracts with milestone payments. A thick dividing line between them with a label: "Analysts confuse these. Don't." Caption: "The post-quantum cryptography story explains government urgency. It is not a hardware revenue source."] -->

The second asymmetry is strategic capability risk — the concern about repeating what happened with semiconductors and artificial intelligence, where strategic industries were ceded to other nations before their significance was fully understood. The UK government's framing is explicit about this motivation; the European Quantum Flagship uses the same language. What this produces is spending structured as *optionality*, not conviction that payoff is imminent. Governments are buying insurance: paying a premium to avoid being blindsided, whether or not they expect to collect on the policy soon. Insurance premiums are paid regardless of whether the insured event occurs. That is exactly what makes sovereign quantum demand durable in a way that commercial demand is not, and it is what keeps these companies off zero even when their commercial pipeline is empty.

---

Now the practical filter. Rank any "government involvement" by how binding and recurring it actually is.

At the top of the hierarchy: a multi-year procurement contract with milestone-tied payments and named deliverables. This is a real demand floor. The money is committed. The deliverables are specific. The program is expensive to cancel — politically sticky in the way defense contracts have always been, with constituencies inside the buying agency who depend on the program's continuation.

Below that: recurring procurement revenue that appears as a labeled line in a company's earnings. This confirms the floor is company-specific rather than sector-specific. When you see it in a quarterly report, you are seeing real cash that recurred.

Below that: a one-time research grant. This is non-recurring. It signals that the government is interested in the *field*, not that it has validated this particular *company*. When the grant ends, the revenue ends. A company whose only government story is grant income has no floor; it has a countdown.

At the bottom: an MOU, a letter of intent, a strategic partnership. These are non-binding. The dollar value is zero because no money is committed. They function as mutual credibility loans — each party borrows the other's name for a press release — and they expire without consequence. An investor who cannot immediately distinguish an MOU from a procurement contract will misread the floor entirely.

<!-- → [TABLE: Four-row hierarchy table. Columns: Tier, Form, Binding?, Revenue predictability, Investment value. Rows: (1) Multi-year procurement contract, milestone payments — Yes — Recurring, predictable — Real demand floor. (2) Recurring procurement in earnings — Yes — Confirmed recurring — Confirms floor is company-specific. (3) One-time research grant — Yes (single payment) — Non-recurring — Signals field interest only. (4) MOU / letter of intent / strategic partnership — No — None — Noise. Caption: "The contract-quality hierarchy. Most 'government engagement' announcements are tier 4. The investment signal lives in tiers 1 and 2."] -->

Why does the tier matter so much more than the dollar figure? Because a demand floor is not about the size of the money — it is about its durability and recurrence. A £20 million grant is a larger number than a £5 million annual procurement contract, but the grant is a one-time event. Next year, the revenue is gone. The procurement contract recurs, is milestone-protected, and behaves like a defense program: politically sticky, expensive to cancel, renewed across budget cycles. For a company burning cash on a decade-long horizon, what keeps the stock off zero is not a big one-time number. It is a predictable, recurring line that survives the years before commercial revenue arrives.

Think of it the way you would think about the difference between a multi-year defense contract and a one-time research scholarship. The contract is sticky and renewed; the scholarship is generous, welcome, and over the moment it is spent.

---

The UK's ProQure program is the most transparent sovereign procurement structure currently operating, and I want to use it as a template — both for what real procurement looks like and for the care required not to overstate what has been confirmed.

ProQure — "Procurement of Quantum" — is a staged sovereign-procurement program run through Innovate UK's Contracts for Innovation, with the National Quantum Computing Centre at Harwell serving as technical evaluator that verifies milestones. Phase 1 opened for competition on 27 March 2026 and closed 29 May 2026, offering up to £14 million across up to ten contracts to develop, build, and validate integrated quantum hardware and software. The program sits under the broader £2.5 billion National Quantum Strategy, published March 2023, whose Mission 1 targets a UK quantum computer capable of one trillion logical operations by 2035, with an interim milestone of one million operations by 2028.

Those milestones are worth sitting with. A trillion logical operations by 2035 is a conservative government planning horizon for a technology that boosters regularly describe as imminent. The structure of the target — staged, validated, milestone-first — is exactly the tell described earlier: a government that thought the technology was nearly ready would not build a program structured this way.

Two things I will not state without verification. First, Phase 1's competition dates (when bids were solicited) are not the same as the performance window (when funded work is delivered). The performance window most plausibly begins after contract awards, not at the competition opening, but I have not confirmed a single authoritative start date for when funded work commences [verify]. Second, a Phase 2 figure of £75 million appears in some sources; I could not confirm it against a primary ProQure document. Treat that number as unverified until you find a primary source [verify].

What ProQure is explicitly designed to inform: a future large-scale public procurement beyond 2030, with a budget of up to roughly £1 billion. That longer-horizon program is where a real demand floor of meaningful size would materialize. Phase 1 at £14 million across ten contracts is small relative to any single company's annual cash burn; the floor thesis for individual companies depends on that larger program taking shape and on US analogues generating comparable recurring revenue.

<!-- → [DIAGRAM: Timeline showing the ProQure program structure. Left anchor: National Quantum Strategy published March 2023. Middle section: Phase 1 competition window March–May 2026, £14M across up to 10 contracts, NQCC at Harwell as technical evaluator. Right section: future large-scale procurement beyond 2030, up to ~£1B. Below the timeline: Mission 1 milestones — 1 million logical operations by 2028, 1 trillion by 2035. Caption: "The ProQure program structure. Phase 1 is a validation and selection mechanism for the larger procurement beyond 2030. The milestone dates reveal the government's true timeline expectation."] -->

---

Alongside procurement, governments have a second instrument that reveals conviction: the national security review. The UK's National Security and Investment Act is now used to treat quantum hardware as critical national infrastructure, which means acquisitions of UK quantum companies by foreign entities require government clearance — and clearance may come with conditions.

The clearest documented case: IonQ's acquisition of Oxford Ionics, completed 17 September 2025 at approximately $1.075 billion mostly in stock, was cleared with explicit sovereignty conditions. Current and future generations of the trapped-ion hardware must be manufactured in the UK. The science, engineering, personnel, and manufacturing capacity must remain domestic. A government that imposes those conditions is not treating quantum as a commercial bet it might win. It is treating the technology as strategic supply-chain infrastructure it cannot afford to lose — conviction expressed through regulation rather than rhetoric.

There is a second NSIA case from around December 2025 involving a dilution-refrigerator manufacturer; the entity name in some sources is uncertain and I have not been able to confirm the exact company, date, and conditions [verify]. Do not cite it until you have a primary source.

The NSIA regime creates an important asymmetry worth understanding. The same national-security apparatus that generates the demand floor — protecting and funding domestic quantum companies — also blocks the large compute incumbents from acquiring them. NVIDIA, which has obvious commercial incentives to control quantum hardware if it becomes strategically important, is blocked from acquiring UK quantum companies under this regime for the same reason that blockade exists. The floor and the acquisition barrier are two faces of one policy: governments protect these companies from foreign strategic capture, which underwrites their revenue and simultaneously constrains who can eventually buy them. An investor who sees only the protective subsidy without the acquisition constraint is reading only half the strategic picture.

---

One honest statement about where things stand as of mid-2026: no quantum company yet reports the kind of sustained, multi-year sovereign procurement revenue that would constitute a fully confirmed demand floor. ProQure Phase 1 at £14 million across ten contracts is small. US procurement through the Department of Energy and Department of Defense is larger in aggregate than the UK's but substantially less transparent, which makes it harder to verify as recurring company-specific revenue. The floor thesis is real, but it is a *forward* thesis — it depends on Phase 2 of ProQure, on US analogues, and on the larger programs materializing on the timelines governments have described. That is not a reason to dismiss it. It is a reason to track it carefully and to insist on the tier-1 or tier-2 signals before weighting it in a position.

---

What to watch for in the coming years: ProQure contract awards naming specific companies. These will reveal who is actually embedded in UK sovereign demand versus who is adjacent to it. Multi-year recurring revenue lines in earnings reports, explicitly labeled as government procurement rather than research grants — that label distinction is the fastest screen. Further NSIA-style sovereignty conditions on quantum acquisitions, each of which is fresh evidence that the government is treating the technology as infrastructure, not a startup bet.

What to ignore: MOUs with government agencies, letters of intent, strategic partnerships without contract values and deliverable milestones, and research grants presented as proof of government conviction. A grant proves a government wants the field to exist. It does not prove it has chosen this company, and it does not produce recurring revenue when the grant year ends.

The discipline is not complicated. It is just unpopular, because most of what gets announced is tier 4.

---

## What Would Change My Mind

If US quantum procurement became as transparent as the UK's — if DoE and DoD quantum awards were regularly published with company names, contract values, and milestone structures — the demand floor could be assessed properly on both sides of the Atlantic, and the case would be much stronger than it is today with opaque aggregate spending figures. The opacity is not permanent; it is a function of how US procurement has historically been reported in this sector.

If ProQure Phase 2 materializes at the rumored scale and the awards are concentrated in a small number of companies rather than spread thinly, the floor becomes meaningful relative to individual company burn rates. The £1 billion beyond-2030 figure is the number to watch.

## Still Puzzling

The insurance-premium framing explains durable demand, but it leaves open a question I do not have a clean answer to: at what point does a government decide its insurance premium has bought it nothing? Defense programs routinely survive that question because they have constituencies — contractors, workers, local economies — who resist cancellation. Quantum programs are young and lack those constituencies in most countries. Whether the ProQure-style programs develop the political stickiness of real defense procurement — or remain reclassifiable as "R&D spending" that gets cut in a budget crunch — is genuinely uncertain. The UK's National Quantum Strategy was bipartisan in spirit but only one parliament old. Track it across a change of government.

---

## Further Reading

- **UK National Quantum Strategy and Quantum Missions, GOV.UK (March 2023).** The primary source for the £2.5 billion commitment, the Mission 1 milestones, and the government's explicit strategic framing — the conservative 2035 timeline and validation-first structure are most revealing about true official expectations.
- **NIST, FIPS 203/204/205 announcement (August 2024).** The primary source dating the post-quantum cryptography standards, the concrete trigger that made cryptographic risk an active government concern with a compliance mandate rather than a future abstraction.
- **Carl Bergstrom and Jevin West, *Calling Bullshit* (Random House).** The accessible toolkit for distinguishing substantive claims from credibility-borrowing ones — which is exactly the skill the contract-quality hierarchy requires when reading government engagement announcements.

---

*This handbook is a framework document, not financial advice. Company names are illustrative examples, not recommendations, and may age quickly.*
