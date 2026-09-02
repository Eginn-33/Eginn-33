## Eginn — VIATREE

Independent **security researcher** — electronic travel document authentication (**eMRTD / ePassport, ICAO 9303 & PKI**) and **self-hosted AI security infrastructure**. Founder, VIATREE.

---

### 🛂 ICAO ePassport Inspector

An iPhone app that runs the same cryptographic passport check used at airport immigration counters — implemented directly against the ICAO 9303 standard rather than wrapped around a commercial SDK.

`ICAO Doc 9303 Parts 10/11` · `BAC / PACE over CoreNFC` · `Passive Authentication (RSA · ECDSA · SHA-256)` · `ICAO PKD Master List trust anchors` · `iOS 16+ / Swift`

Fully on-device — MRZ OCR, the chip session and signature validation never leave the phone. No accounts, no server calls, no images uploaded.

→ [epassport-web.vercel.app](https://epassport-web.vercel.app) · [site source](https://github.com/Eginn-33/epassport-web)

---

### 🔐 eMRTD verification toolkit

Python tooling for the ICAO 9303 PKI stack — BAC, PACE, Active Authentication, Chip Authentication, Terminal Authentication, Passive Authentication.

Extracted and parsed **588 CSCA certificates across 114 countries** from the German BSI Master List. Analysed how `AA_Failed` / `CA_Failed` surface as independent error conditions across commercial SDKs (Regula Document Reader) and open-source validators (OST Kinegram eMRTD Validator).

Also used to disprove a third-party claim of having defeated AA and CA verification: the observed Passive Authentication failure was evidence *against* the claim, not for it.

---

### ⚔️ IAEL — dual-model adversarial evolution harness

Two AI models attack an isolated lab; the surviving defenses evolve; every result has to be provable rather than self-reported.

- `Attack-A` and `Attack-B` must be **different model revisions**, with independent sessions, run directories, lab clones, budgets and event streams
- Scripts, fixtures, static JSON and same-model aliases are **barred from registering as contestants**
- Every real match emits a `run_id`, provider request evidence, tool events, an environment state diff and an event root hash
- Winning one match earns *candidate* champion only — a formal champion clears **5 hidden scenarios x 3 seeds**
- Raw traces, match evidence, training provenance, frozen assets and generational lineage are never auto-pruned

Windows control plane to WSL2 GPU worker, Electron desktop client, macOS/iOS runner planned.

---

### 🌳 VIATREE OS

AI-autonomous company operating system on a dedicated VPS. Seven departments and 27+ agents, each department locked to a **different model vendor** — R&D, Production, QA, Sales, Finance, Support, Ops routed across Claude, GPT, Perplexity, DeepSeek, Qwen, MiniMax and GLM — so no single provider outage stops the system.

→ [viatreebot.com](https://viatreebot.com)

---

### Working principles

- **No fabricated metrics.** If a number isn't measured, it doesn't ship.
- **Open standards over vendor SDKs.** If it passes here, it passes at a real border.
- **On-device by default.** Cloud only as an explicit, declared fallback.

---

📧 303@viatreebot.com · 🌐 [viatreebot.com](https://viatreebot.com) · 💼 [linkedin.com/in/viatree](https://linkedin.com/in/viatree)
