# Research Notes: Chapter 01 — The Honest Starting Point
**Source:** TIKTOC.md chapter entry
**Notes file:** 01-the-honest-starting-point_notes.md
**Corresponding chapter:** chapters/01-the-honest-starting-point.md (not yet written)
**Generated:** 2026-06-10

---
## Chapter summary (from TIKTOC.md)
**Decision question:** Is quantum computing a real investment opportunity or pure hype? **Short answer:** both, on different timelines. **Framework** = a three-layer test: (1) Is the physics real? (2) Does it translate to commercial advantage on a relevant timeline? (3) Is the stock pricing reality or narrative? **Thesis:** take a small "bookmark" position now, build domain knowledge always, wait for a four-part signal, and size up only when it fires. **Watch:** expansion of NVIDIA's minority investments, sovereign procurement converting into recurring revenue, architecture convergence. **Ignore:** raw qubit counts, "supremacy" claims without independent verification, vendor roadmaps promising commercial advantage by 2029.

---
## A. Conceptual foundations

### The three-layer test (the book's organizing device)
The chapter's core intellectual move is to separate three questions that hype routinely collapses into one. Layer 1 (physics): does the underlying device do something genuinely quantum and reproducible? This is mostly settled — superposition, entanglement and error correction are real, demonstrated phenomena (see Chapter 2). Layer 2 (commercial translation): does the real physics produce a *useful, economically relevant* result on a timeline an investor can underwrite? This is where most claims fail, and it is the subject of Chapter 3's filter. Layer 3 (pricing): even when 1 and 2 are favorable, is the equity priced for reality or for narrative? In 2026 the answer to Layer 3 is overwhelmingly "narrative."

Keeping the layers distinct is what lets a skeptic hold two true thoughts at once: the science is real *and* the stocks are overvalued. Hype merchants and reflexive cynics both fail by treating the three as a single yes/no.

**Common misconception:** "If the physics is real, the investment is good." Real physics is necessary but nowhere near sufficient — most of an investor's risk lives in Layers 2 and 3, not Layer 1.
**Worked example:** Google's "Willow" chip and IonQ's 99.99% gate-fidelity milestone are strong Layer-1 evidence. Neither tells you anything about whether IonQ at a ~100x+ price-to-sales multiple is a good buy (Layer 3).
**Source(s):** McKinsey Quantum Technology Monitor 2026 (https://www.mckinsey.com/capabilities/mckinsey-technology/our-insights/mckinsey-quantum-technology-monitor-2026-a-commercial-tipping-point); Scott Aaronson, "Quantum Computing: Between Hope and Hype" (https://scottaaronson.blog/?p=8329)

### "Both, on different timelines" — why the honest answer is two answers
The science is on a multi-decade arc; the stocks trade on a quarterly one. BCG's framing is useful: NISQ (noisy intermediate-scale) era to ~2030, "broad quantum advantage" 2030–2040, full fault tolerance after 2040. McKinsey's 2026 monitor calls the moment a "commercial tipping point" but its own value figures are modest and back-loaded ($72B of quantum-computing value by 2035 in McKinsey's framing; BCG's $450B–$850B of *economic value* is a 2040 number). An investor who buys "real" on a 2026 horizon is buying a 2035–2040 thesis at 2026 prices.

**Common misconception:** that "tipping point" language means revenue is imminent. The tipping point is in *enterprise pilots and roadmaps*, not in fault-tolerant, advantage-grade machines.
**Worked example:** Drug-discovery/chemistry simulation is the application most likely to mature first (late 2020s–early 2030s per BCG/McKinsey), which is still 4–10+ years out.
**Source(s):** BCG, "Quantum Computing On Track to Create Up to $850 Billion... By 2040" (https://www.bcg.com/press/18july2024-quantum-computing-create-up-to-850-billion-of-economic-value-2040); McKinsey Quantum Technology Monitor 2026 (link above)

### The "sell shovels" analogy and its limits
The Mark-Twain-attributed maxim — "during a gold rush, sell shovels" — is the dominant investing frame for AI, where NVIDIA is the canonical shovel-seller (compute infrastructure profits regardless of which app wins). The chapter should both use and stress-test this analogy for quantum. The "shovel" logic argues for owning infrastructure/enablers rather than picking the winning qubit modality. But the analogy has a defect in quantum: in the AI gold rush there was real gold being dug *today* (working models, paying customers), so shovels sold. In quantum the gold is still mostly theoretical and a decade out, so a "shovel" business may be selling to miners who haven't struck anything yet.

**Common misconception:** that NVIDIA's AI playbook transfers cleanly to quantum. NVIDIA itself is a *hedged* shovel-seller here — via CUDA-Q (hybrid quantum-classical software) and small NVentures equity stakes, not a bet-the-company commitment.
**Worked example:** NVIDIA's posture — software layer (CUDA-Q) plus minority venture stakes across modalities — is the literal "sell shovels and own a slice of several mines" strategy, and is a model for the book's own "bookmark position" thesis.
**Source(s):** "Why NVIDIA Is Buying Into Quantum Computing," TIME (https://time.com/7319603/nvidia-ai-quantum-computing/); The Quantum Insider on NVentures (https://thequantuminsider.com/2025/09/13/how-is-nvidia-betting-on-quantum-a-look-at-nventures-quantum-investment-playbook-from-skepticism-to-strategic-stakes/)

### Why valuation, not technology, is the near-term risk
As of mid-May 2026, IonQ, Rigetti and D-Wave traded at price-to-sales (P/S) ratios reported around 109x, 836x and 791x respectively (other mid-May snapshots put Rigetti and Quantum Computing Inc. at ~592x and ~606x). For context, even the leading next-big-thing names of the dot-com era topped out around 30–45x P/S — a level that historically proved unsustainable. The stocks have also been violently volatile: a 72% run across seven sessions in April 2026, then a multi-name crash (IonQ −7%, D-Wave −8%, Rigetti/QCI −9%) on profit-taking in May. Insiders at all three have been net sellers over five years.

**Common misconception:** "Revenue is growing 700%+, so the multiple is justified." IonQ's Q1 2026 revenue of $64.7M (up 755% YoY) is real but tiny relative to a multi-billion market cap; off a small base, triple-digit growth still leaves a P/S that prices decades of flawless execution.
**Worked example:** IonQ FY2025 revenue was $130.0M (beat guidance by 20%); FY2026 guidance ~$235–270M; cash position ~$3.3B. The cash hoard is itself a tell — these are companies funded by capital markets, not customers.
**Source(s):** Motley Fool (https://www.fool.com/investing/2026/05/28/quantum-computing-ionq-rgti-qbts-wall-st-warning/); 24/7 Wall St. (https://247wallst.com/investing/2026/05/18/ionq-falls-7-d-wave-dives-8-rigetti-and-quantum-computing-inc-plunge-9-quantum-stocks-crash-on-profit-taking/); IonQ 8-K filings (https://www.sec.gov/cgi-bin/browse-edgar?action=getcompany&CIK=0001824920)

---
## B. Domain examples and cases

### Case 1: NVIDIA's hedged entry (the model for "bookmark + watch")
In 2025, NVentures invested in QuEra (neutral atom), Quantinuum (trapped ion) and PsiQuantum (photonic) — one bet per major modality. In a September 2025 cluster, NVentures participated in Quantinuum's $600M round (~$10B valuation) and PsiQuantum's $1B Series E (~$7B valuation, led by BlackRock/Baillie Gifford/Temasek). This is the *architecture-agnostic, minority-stake* posture the chapter recommends watching for expansion.
**Source(s):** Global Venturing (https://globalventuring.com/corporate/investment/nvidia-backs-three-quantum-startups-amid-investment-boom/); DCD on PsiQuantum (https://www.datacenterdynamics.com/en/news/psiquantum-raises-1bn-in-funding-including-from-nvidias-venture-capital-arm/)

### Case 2: Sovereign procurement as a revenue signal
A large share of IonQ's 2025–2026 momentum came from government/sovereign deals and partnerships (e.g., a KISTI MOU on hybrid quantum-HPC with NVIDIA accelerated computing). The book's thesis treats sovereign *procurement converting into recurring revenue* as one leg of its four-part buy signal — the distinction being between one-off grant/grand-announcement money and durable, renewing contracts.

### Failure case: the 2029 commercial-advantage roadmap
Vendor roadmaps promising *commercial* (not merely technical) quantum advantage by 2029 run ahead of every independent forecast (BCG's broad-advantage window opens 2030; McKinsey's value is a 2035 story). The chapter flags these as marketing to be discounted. The honest read: technical advantage demos may continue; *broad commercial* advantage by 2029 is an outlier claim.

---
## C. Connections and dependencies
**Prerequisites:** None — this is the opening chapter. It only needs the reader's willingness to hold "real science / overvalued stock" simultaneously.
**Unlocks:** The three-layer test structures the entire book; Layer 1 → Chapter 2 (the physics vocabulary), Layer 2 → Chapter 3 (the big-compute/small-data filter), Layer 3 → the valuation/signal chapters later in the book.
**Adjacent chapter connections:** Chapter 2 supplies the six-term vocabulary that lets a reader audit a Layer-1 claim. The "four-part signal" and NVIDIA/sovereign watch-items are developed in the later signal and NVIDIA chapters.

---
## D. Current state of the field
**Settled:** The physics is real and advancing (error correction below threshold demonstrated; four-nines gate fidelity reached). Pure-play quantum equities are, by any historical yardstick, in bubble-grade valuation territory. Timelines to *broad commercial* advantage are 2030s+.
**Contested or emerging:** Whether 2026 is a genuine "commercial tipping point" (McKinsey's framing) or just a funding/sentiment peak; which qubit modality wins (the case for not picking one); whether any pure-play reaches self-sustaining revenue before its cash runway and equity-issuance window close.
**Key references:**
1. McKinsey, *Quantum Technology Monitor 2026* — the most-cited industry value/forecast baseline; use for "tipping point" framing and value numbers.
2. BCG, *Quantum Computing... $850B by 2040* — the canonical phased timeline (NISQ→broad advantage→fault tolerance).
3. Scott Aaronson, *Quantum Computing: Between Hope and Hype* (blog, 2024) — the best skeptic-insider counterweight to vendor optimism.
4. Motley Fool / 24/7 Wall St. 2026 coverage — contemporaneous valuation and insider-selling data points (treat as journalism, verify P/S against filings).
**Recent developments (last 3 years):** Google "Willow" error-correction milestone (2024); IonQ four-nines (99.99%) two-qubit gate fidelity (2025); NVIDIA's pivot from public skepticism to NVentures stakes + CUDA-Q (2025); extreme 2026 stock volatility (April surge, May crash).

---
## E. Teaching considerations
**Where readers get stuck:** Believing they must choose between "it's a scam" and "it's the future." The whole chapter exists to dissolve that false binary.
**Analogies that work:** The gold-rush/shovels frame (used *and critiqued*). A second useful one: distinguishing the *invention* of the airplane (1903) from the *profitable airline industry* (decades later) — real tech, terrible early equity.
**Exercises that build the skill:** Hand the reader a recent quantum press release and have them sort each claim into Layer 1, 2, or 3. Have them compute a P/S ratio from a 10-K and compare to the dot-com 30–45x ceiling.

---
## F. Library files relevant to this chapter
- `_lib_physics-quantum-physics-for-beginners-into-the-light-...md` — background only; supports Layer-1 confidence (superposition, entanglement, uncertainty are textbook-real). More directly relevant to Chapter 2.
- `_lib_physics-the-physics-of-wall-street-a-brief-history-of-predicting-the-unpredictable.md` — potentially useful for the Layer-3 / valuation-skepticism framing (history of physics-flavored market models that overpromised).

---
## G. Gaps and flags
- FLAG: All P/S figures are from 2026 financial-press snapshots and move daily; the chapter author should re-pull from EDGAR filings at draft time. The 109x / 836x / 791x and 592x / 606x figures came from different mid-May 2026 articles and are not mutually consistent — present as "ranges reported in the financial press," not precise truths.
- FLAG: I did not find evidence of a *direct NVIDIA equity stake in IonQ* (as opposed to a partnership). The "NVIDIA minority investment expansion" watch-item is real for QuEra/Quantinuum/PsiQuantum/Alice & Bob via NVentures, but do not assert an IonQ equity stake without verification.
- GAP: The book's "four-part signal" is referenced in the thesis but not fully enumerated in this chapter's source material — its four components are developed in a later chapter and should be cross-referenced, not invented here.
