<div align="center">
  <img src="./assets/hackathon_topic.png" width="450" alt="PEC Hacks 4.0">
</div>

<hr style="border: 2px solid #333; margin: 30px 0;">

<div align="center">
  <h2><strong>Team Name</strong></h2>
</div>


<div align="center">
  <img src="./assets/team_logo.png" width="280" alt="PromptVibers Logo">
  <hr style="border: 2px solid #333; margin: 30px 0;">

  <h1><strong>ASTRA</strong></h1>
  <h3>(Autonomous Sequence & Temporal Risk Architecture)</h3>
</div>

<br>

> **Building the Missing Layer Against India's ₹22,495 Crore Digital Arrest Epidemic**

![Digital Arrest Targets Everyone](./assets/digital_arrest_banner_diverse.png)

### How a three-member team engineered a real-time, on-device AI system to detect scam calls as they happen — and physically stop the money before it moves

<hr style="border: 2px solid #333; margin: 40px 0;">

## Prologue: A 92-Year-Old Man, Two Days, Two Crore Rupees

In 2025, a 92-year-old man in Delhi was kept on a video call for 48 hours by scammers posing as CBI officers. He was told he was under "digital arrest" — a fabricated legal concept that doesn't exist anywhere in Indian law — and that leaving the camera's view, or telling his family, would result in immediate imprisonment. By the time the siege ended, he had transferred ₹2 crore.

A retired doctor couple lost ₹15 crore the same year. A woman in Mangaluru lost ₹1.8 crore. These aren't edge cases — they're a documented pattern occurring at national scale: **₹22,495 crore lost to cyber fraud in India in 2025, 2.81 million reported cases, 30,000+ specifically "digital arrest" incidents, and 51% of victims who never report the crime at all.**

Here's the detail that should unsettle every product team working on fraud prevention: in nearly every documented case, the victim later said they *knew* the underlying rule — "no real police officer arrests you over a video call." They knew it. They just couldn't access that knowledge while under sustained psychological siege. This isn't an awareness problem. It's a **behavioral pattern-interruption problem**, and nothing on the market was built to solve it.

This is the story of **ASTRA** — a system built to occupy the one part of the fraud lifecycle that every existing defense ignores: the middle.

**Related News & Case Studies:**
- [92-year-old man defrauded of Rs 2.2 crore in 'digital arrest', Delhi Police arrests two](https://www.newindianexpress.com/cities/delhi/2024/May/20/92-year-old-man-defrauded-of-rs-22-crore-in-digital-arrest-delhi-police-arrests-two)
- [Elderly couple kept under ‘digital arrest’ for over two weeks in Delhi; duped of ₹14 crore](https://www.thehindu.com/news/national/elderly-couple-kept-under-digital-arrest-for-over-two-weeks-in-delhi-duped-of-14-crore/article70497188.ece)
- [Mangaluru woman loses over ₹3 crore to online fraudsters who threatened arrest of her husband](https://www.thehindu.com/news/cities/Mangalore/homemaker-loses-over-3-crore-to-online-fraudsters-who-threatened-arrest-of-her-husband/article69777617.ece)
- [Elderly couple duped of Rs 2.5 crore in Chandigarh, kept under digital arrest for 15 days](https://www.ptcnews.tv/nation/elderly-couple-duped-of-rs-2-crore-in-chandigarh-kept-under-digital-arrest-for-15-days-4425251)
- [This news segment breaks down the exact timeline of the Delhi doctor couple's digital arrest, illustrating the sustained psychological manipulation your system is built to intercept](https://www.youtube.com/watch?v=AsKbc-P5BcY)

<hr style="border: 2px solid #333; margin: 40px 0;">

## Part 1: The Empty Middle Column

![Gemini Generated Image](./assets/gemini_custom_image.png)

Every anti-fraud product in existence falls into one of two buckets — before the call, or after the money is gone.

| Defense Layer | What It Does | When It Fires | The Gap |
|---|---|---|---|
| Telecom spoofing blocks | Blocks fake international caller IDs | Pre-call | Scammers use domestic SIM farms + WhatsApp/Skype, bypassing telecom entirely |
| Audio-authenticity detectors (Pindrop, Google's fake-call detection) | Determines if a *voice* is synthetic | During call, narrow scope | Fails completely against a live human scammer reading a script — the majority case in India |
| Deepfake takedown rules | Platforms remove flagged content | Post-call, +3 hours | Money is already gone in 15 minutes |
| Bank AI fraud flags | Flags unusual transfer patterns | Post-transfer | The victim *authorized* the transfer under duress — banks legally cannot reverse it |
| 1930 helpline / NCRP | Cybercrime reporting hotline | Post-loss | Mule-account freezing takes days; 51% never even file |
| Public awareness campaigns | "Don't pay, verify first" | Pre-call, passive | Fails under sustained psychological siege — see the 92-year-old case |
| **ASTRA** | **Multimodal coercion-pattern detection + payment circuit-breaker + autonomous evidence swarm** | **DURING the call** | **This row didn't exist before** |

The one-line pitch we built the entire system around:

> *"ASTRA is the only defense layer that operates during the six hours between a scam call starting and the money leaving — it doesn't just listen to what's said, it watches who's saying it, tracks the coercion script in real time, and physically breaks the payment path before the victim's own judgment gets there."*

<hr style="border: 2px solid #333; margin: 40px 0;">

## Part 2: The Core Insight — Scams Aren't Improvised, They're Scripted

![Second Gemini Generated Image](./assets/gemini_custom_image_2.png)

The single most important engineering decision in ASTRA comes from a hypothesis that turned out to be true: **digital-arrest scams follow a documented, repeating five-stage narrative arc**, independent of language, independent of whether the caller is a live human or an AI clone, and — critically — **sequence-dependent**.

### The Canonical Five-Phase Coercion Arc

| Phase | Name | Behavioral Function | Example (Hindi) | Example (Tamil) |
|---|---|---|---|---|
| 1 | **AUTHORITY_CLAIM** | Caller asserts law-enforcement/government identity with fabricated badge numbers | "Main CBI officer Rajesh Kumar bol raha hoon, badge 4578" | "Naan Income Tax officer Suresh pesuren, badge ID 9821" |
| 2 | **CRISIS_FRAMING** | Anchors victim to a specific crime via a personal identifier (Aadhaar, PAN) | "Aapka Aadhaar ek drug parcel mein mila hai" | "Ungal PAN card money laundering case-la use aaguthu" |
| 3 | **ISOLATION** | Severs the victim's support network — the single highest-leverage move | "Kisi ko mat batao. Family ko call kiya toh raid karenge" | "Yarukkum sollaatheenga, family-kku theriyaadha irukkanum" |
| 4 | **URGENCY_ESCALATION** | Hard deadline + custodial-visibility order to prevent independent verification | "Camera ke saamne rehna. Sirf 10 minute hain" | "Camera munnadi irungal, 10 nimisham mattume irukku" |
| 5 | **PAYMENT_DEMAND** | The financial ask — "security deposit," verification fee, via UPI or OTP | "2 lakh security deposit transfer karo" | "1 lakh Google Pay-la transfer panningal" |

Why does sequence matter so much? Because a call that opens with Phase 5 language — a legitimate bank calling about a fraudulent OTP — scores fundamentally differently from a call that reaches Phase 5 only *after* Phases 1→3→4 have fired in order. A system that scores markers as an unordered bag cannot make this distinction. A system that tracks them as an ordered arc can. This single architectural choice is the strongest answer to the most common objection a system like this receives: *"isn't this just keyword matching?"*

<hr style="border: 2px solid #333; margin: 40px 0;">

## Part 12: The 3-Minute Demo, Beat by Beat

![Circuit Breaker Interception UI](./assets/circuit_breaker_ui.png)

| Time | Beat | What Happens |
|---|---|---|
| 0:00–0:30 | The hook | ₹22,495 crore. 2.81 million cases. 51% never reported. Zero products stop it while it's happening. |
| 0:30–0:45 | Scenario setup | Scammer's mock CBI backdrop on a laptop video call; victim's phone screen-mirrored via scrcpy for the judges to watch |
| 0:45–1:45 | The call runs live | Scripted arc delivered in order — Authority → Crisis → Isolation → Urgency — while the risk meter climbs in real time on the mirrored screen |
| 1:45–2:15 | Hard alert fires | R(t) crosses 0.65 — full-screen overlay, risk meter at ~78%, three trigger phrases with plain-English explanations |
| 2:15–2:35 | **The money shot** | Victim opens Google Pay mid-call — the Accessibility/UsageStats circuit-breaker intercepts it, 60-second cooling-off countdown appears |
| 2:35–2:50 | Physical proof | A judge's pre-registered phone audibly buzzes with the WhatsApp alert — the single strongest non-technical proof point in the entire demo |
| 2:50–3:00 | Close | Dashboard shows the number auto-flagged nationally and the NCRP evidence packet pre-filled, ready in one tap |

The rehearsal discipline behind this: both phones on shared WiFi, backend deployed (never localhost during a live demo), judge's phone pre-registered as a trusted contact, the scam script rehearsed verbatim in exact order, GPay pre-launched, and — critically — a full screen-recorded fallback video always on hand. Never demo a broken pipeline live.

<hr style="border: 2px solid #333; margin: 40px 0;">

## Epilogue: What This Project Actually Is

Strip away the acronyms and the risk-fusion formula, and ASTRA is an attempt to answer one specific, narrow question: **can a piece of software recognize, in real time, that a person is being psychologically coerced — and can it act on that recognition faster than the coercion can complete itself?**

The honest answer, built into every design decision here, is: *mostly, and imperfectly, and only if you're honest about every place it can still fail.* The AudioPlaybackCapture path can be closed by one manifest update. MIUI can still kill the background service if a user never grants battery whitelist. A sufficiently patient scammer can still stay under the deepfake gate. A frightened victim can still be talked into deleting the app.

None of those are marketing problems to paper over. They're engineering problems to keep solving, one redundant path and one gated threshold at a time — which is the actual difference between a hackathon pitch and a system someone might eventually trust with their life savings.

<hr style="border: 2px solid #333; margin: 40px 0;">
*ASTRA: the bodyguard that lives inside your call. It doesn't stop the scammer from calling. It stops you from paying.*



