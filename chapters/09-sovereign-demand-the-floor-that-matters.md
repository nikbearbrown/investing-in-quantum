# Chapter 9 — Sovereign Demand: The Floor That Matters

## Decision question

Here is a puzzle that should bother any value-minded investor. Most quantum hardware companies have negligible commercial revenue. They burn cash, they sell almost nothing a customer would buy on its own economic merits, and the technology they make will not be commercially useful for the better part of a decade — possibly longer. Under a pure-commercial lens, many of them should trade near zero. They do not. Why haven't they collapsed? This chapter answers the question behind that one: **how do I distinguish companies with real government revenue from companies with press releases about government interest?**

## The short answer

Look for contracts with specific deliverables and multi-year terms — not memoranda of understanding, not "strategic partnership" announcements, not one-off research grants. Recurring procurement revenue is a real demand floor; everything else is noise. The UK's ProQure program is the most transparent sovereign procurement structure currently operating, and you should use it as the template against which you judge every other government claim.

## Why this matters

The reason these companies have not gone to zero is that governments are buying quantum computing for reasons that have nothing to do with whether it is commercially useful yet. A government does not need a quantum computer to be profitable to want a sovereign one — it needs the capability to exist *domestically*, before adversaries have it. That converts a slice of demand from "depends on the product working in the market" to "depends on the geopolitics continuing," and geopolitics is far more durable on a five-to-ten-year horizon than any commercial roadmap.

But — and this is the whole investment point — only *some* government money is structured this way. The overwhelming majority of "government interest" announcements are non-binding theater: a photo op, an MOU, a press release that borrows credibility without committing a pound. If you cannot tell the difference between a multi-year procurement contract and a memorandum of understanding, you will mistake noise for a floor, overweight a company that has nothing, and be surprised when its "government backing" evaporates because it was never a revenue line in the first place. Getting this distinction right is the difference between identifying a company with a durable demand floor and buying a company with a flattering email from a ministry.

## The framework

Two asymmetries explain why governments fund quantum despite the long timeline, and both reward the *structure* of the funding over its volume.

**Asymmetry one — cryptographic risk.** Shor's algorithm, run on a large fault-tolerant quantum computer, would efficiently factor the large numbers that secure RSA and elliptic-curve encryption — the cryptography protecting essentially all current digital infrastructure. The threat is asymmetric in *time*: an adversary can record encrypted traffic *today* and decrypt it years later when the hardware exists. This "harvest now, decrypt later" dynamic makes the risk actionable now, even though the capable machine is a decade-plus away. The concrete trigger already happened: **NIST finalized its first three post-quantum cryptography standards in August 2024** — FIPS 203, 204, and 205 — giving US federal agencies a migration mandate.

A crucial scope note, because it is where investors most often go wrong: post-quantum cryptography is **defensive software spending** — migrating systems to new algorithms — not a revenue line for quantum *hardware* makers. It explains why the sector has strategic *salience* in the eyes of governments. It is not a hardware investment thesis, and this handbook treats it as out of scope as one. Keep it firmly in the "why governments care" column, never the "how hardware companies make money" column.

**Asymmetry two — strategic capability risk.** Governments fund quantum the way they hedge against any technology they cannot afford to be late on. The UK's framing is explicit: avoid "repeating semiconductor and AI mistakes" — ceding a strategic industry to other nations. And here is the tell that this is *optionality*, not *conviction that payoff is imminent*: the planning horizons are conservative and the programs are structured as multi-phase validation, not crash commercialization. A government that believed quantum would arrive in 2027 would not first run a multi-year prototype-validation program. The *structure* of the spending reveals the true timeline expectation, and that expectation is long. Heavy government funding is therefore not evidence the technology is nearly ready — if anything, the validation-first structure is evidence the government thinks it is years off.

**The contract-quality hierarchy.** From this, the core investor filter falls out. Rank any "government involvement" by how binding and recurring it is:

1. **Multi-year procurement contract, milestone-tied payments, named deliverables** — a real demand floor.
2. **Recurring procurement labeled as such in earnings** — confirms the floor is company-specific.
3. **One-off research grant** — non-recurring; signals interest in the *field*, not readiness of the *company*. When the grant ends, the revenue ends.
4. **MOU, letter of intent, "strategic partnership"** — non-binding; near-zero investment value.

Tiers 1 and 2 are floors. Tiers 3 and 4 are noise. Most of what you will read in a press release is tier 4.

Why does the tier matter so much more than the dollar figure? Because a demand floor is not about the *size* of the money but its *durability and recurrence*. A £20 million grant is a larger number than a £5 million annual procurement contract, but the grant is a one-time event — next year the revenue is gone — while the procurement contract recurs, is milestone-protected, and behaves like a defense program: politically sticky, expensive to cancel, and renewed across budget cycles. For a company burning cash on a decade-long horizon, what stops the stock from going to zero is not a big one-time number; it is a *predictable, recurring* line that survives the years before commercial revenue arrives. That is why the binding, multi-year, milestone-tied structure is the thing to find, and why the dollar amount on an MOU — which is zero, because an MOU commits no money — is the honest measure of what an MOU is worth.

A useful mental model: treat the procurement-versus-grant distinction the way you would treat the difference between a multi-year defense contract and a one-time research scholarship. The defense contract is sticky, protected, and renewed; the scholarship is generous, welcome, and over the moment it is spent. And treat the government's overall posture as buying *insurance* — paying a premium for optionality against being strategically blindsided, whether or not it expects to "use" the technology soon. Insurance premiums are paid regardless of whether the insured event happens; that is exactly what makes sovereign quantum demand durable in a way commercial demand is not.

## What it looks like in practice

**ProQure — the benchmark.** ProQure ("Procurement of Quantum") is the UK's staged sovereign-procurement program, run through Innovate UK's Contracts for Innovation, with the **National Quantum Computing Centre (NQCC) at Harwell as the technical evaluator** that verifies milestones. The verified details: the Phase 1 **competition opened 27 March 2026 and closed 29 May 2026**, offering up to **£14 million** across up to **ten contracts** to develop, build, and validate integrated quantum hardware and software.

A flag worth carrying: TIKTOC's chapter notes describe Phase 1 as running "October 2026 – September 2028." The verified dates above are for the *competition* (the bidding window). The "October 2026 – September 2028" span most plausibly refers to the *performance window* — when the funded work is actually delivered — but I have not confirmed a single authoritative performance-start date, so I will not assert one [verify]. Do not treat the competition dates and the delivery dates as the same thing.

ProQure is explicitly designed to inform a **future large-scale public procurement beyond 2030, with a budget of up to roughly £1 billion**. (TIKTOC also cites a "£75M Phase 2"; I could not verify that specific figure against a primary ProQure document, so treat the £75M number as **unverified** [verify].) The program sits under the broader **£2.5 billion National Quantum Strategy** (published March 2023), whose Mission 1 targets a UK quantum computer capable of **one trillion logical operations by 2035**, with an interim milestone of **one million operations by 2028**. These are conservative government planning horizons — exactly the long-timeline tell described above.

**NSIA interventions as conviction signals.** The UK's National Security and Investment Act (NSIA) is now used to treat quantum as critical national infrastructure. The verified case: IonQ's acquisition of **Oxford Ionics** (completed **17 September 2025**, roughly **$1.075 billion**, mostly stock) was cleared *with sovereignty conditions* — current and future generations of the trapped-ion hardware must be manufactured in the UK, and the science, engineering, personnel, and manufacturing capacity must remain domestic. A government that imposes those conditions on a quantum acquisition is treating the technology as strategic supply-chain infrastructure, not a speculative commercial bet. That is conviction expressed through regulation. (TIKTOC cites a second NSIA case involving a dilution-refrigerator maker in December 2025, naming "Oxford Nanoscience / QD Oxford." I could not verify that entity; the likely intended company is **Oxford Instruments NanoScience**, a leading dilution-refrigerator manufacturer — but confirm the exact name, date, and conditions before relying on it [verify].)

**The failure case — mistaking a grant or MOU for a floor.** The recurring investor error is treating any government association as validation. A company whose only "government revenue" is grant income has no floor: when the grant ends, the revenue ends. An MOU commits no money at all. The discipline is to read earnings for *recurring procurement* line items with deliverables, and to discount everything labeled "partnership," "MOU," or "selected for a study."

There is a second face to this same regulatory regime worth noting, because it connects to how you read NVIDIA's position elsewhere in this handbook. The very national-security apparatus that creates the demand floor — NSIA in the UK, CFIUS in the US — also *blocks* large compute incumbents from acquiring quantum hardware companies, because that hardware is classified as critical dual-use infrastructure. The floor and the acquisition barrier are two faces of one regime: governments protect these companies from foreign or strategic capture, which both underwrites their revenue and constrains who can buy them. An investor who sees only the protective subsidy and misses the acquisition constraint will misread the strategic landscape.

One honest current-state caveat: as of June 2026, no quantum company yet reports the kind of sustained, multi-year sovereign *procurement* revenue that would satisfy Signal 3 of the four-part breakthrough signal (Chapter 8). ProQure Phase 1 (£14M across ten contracts) is small relative to company cash burn; the floor thesis depends on Phase 2 and on US analogues materializing. US procurement (Department of Energy, Department of Defense, national labs) is larger in aggregate than the UK's but far less transparent, which makes it harder to verify as recurring company revenue. State this as the current status, not a permanent fact.

## What to watch for

- **ProQure contract awards** naming specific companies — these reveal who is actually embedded in UK sovereign demand.
- **US Department of Energy quantum program awards** — larger in aggregate than the UK's, less transparent, but worth tracking.
- **Multi-year recurring revenue lines in earnings reports, explicitly labeled as government procurement** rather than research grants.
- **Further NSIA-style sovereignty conditions** on quantum acquisitions — each one is fresh evidence of government conviction.

## What to ignore

- **MOUs with government agencies.** Non-binding.
- **Letters of intent.** Non-binding.
- **"Strategic partnerships"** without a contract value and deliverable milestones.
- **Research grants.** One-time, non-recurring, and not evidence the government believes the technology is commercially ready — only that it wants the field to exist.

## The decision rule

A quantum company with ProQure-style procurement revenue — or equivalent verifiable US or EU procurement, with named deliverables and multi-year terms — has a real demand floor, and you can weight that floor modestly in position sizing. A company whose government story is grants, MOUs, or "partnerships" has no floor; treat its government association as noise and size it as if that revenue were not there.

## Further reading

- **Carl Bergstrom & Jevin West, *Calling Bullshit* (Random House)** — accessible toolkit for distinguishing a substantive claim (a binding multi-year contract) from a credibility-borrowing one (an MOU or "partnership"), which is exactly the skill the contract-quality hierarchy requires.
- **UK National Quantum Strategy and Quantum Missions, GOV.UK (March 2023)** — independent government policy document whose conservative 2035 timeline and validation-first structure reveal the true official expectation for the technology.
- **NIST, FIPS 203/204/205 announcement (August 2024)** — the primary source dating the post-quantum cryptography standards, the concrete trigger that made cryptographic risk an active government concern rather than a future one.
