## Elias (Eginn) Chen — VIATREE

Independent **security researcher** — electronic travel document authentication (**eMRTD / ePassport, ICAO 9303 & PKI**) and **self-hosted AI security infrastructure**. Chairman, VIATREE.

---

### 📱 PLIEVA by VIATREE — remote iPhone console

Device-security research turned into a working console: how far a stock, non-jailbroken iPhone can be legitimately reached from a Windows PC across arbitrary networks — no jailbreak, no exploit, no cable, developer-signed on owned hardware.

Existing iOS mirroring tools land in one of two buckets: view-only, or touch via Bluetooth pairing — which puts the computer in the same room as the phone. PLIEVA does neither. Screen and input travel over a single end-to-end encrypted link, so the PC and the phone never have to share a network.

`iOS 26.5.2` · `live screen + touch injection` · `text input` · `hardware buttons` · `multi-terminal handover (~1s switchover)`

**Measured:** 108 minutes continuous with the phone off Wi-Fi on carrier data only — 205 probes, 2 failures, both inside the Wi-Fi→cellular handover. Not yet verified: tower handover with the phone physically off-site.

Intended for my own devices only. Source not public.

---

### 🛂 ICAO ePassport Inspector — a VIATREE product

An iPhone app that runs the same cryptographic passport check used at airport immigration counters — implemented directly against the ICAO 9303 standard rather than wrapped around a commercial SDK.

`ICAO Doc 9303 Parts 10/11` · `BAC / PACE over CoreNFC` · `Passive Authentication (RSA · ECDSA · SHA-256)` · `ICAO PKD Master List trust anchors` · `iOS 16+ / Swift`

Fully on-device — MRZ OCR, the chip session and signature validation never leave the phone. No accounts, no server calls, no images uploaded.

→ [App Store](https://apps.apple.com/us/app/icao-epassport-inspector/id6762305723) · [epassport-web.vercel.app](https://epassport-web.vercel.app) · [site source](https://github.com/Eginn-33/epassport-web)

---

### 🔐 eMRTD verification toolkit

Python tooling for the ICAO 9303 PKI stack — BAC, PACE, Active Authentication, Chip Authentication, Terminal Authentication, Passive Authentication.

Extracted and parsed **581 CSCA certificates across 112 countries** from the German BSI Master List. Analysed how `AA_Failed` / `CA_Failed` surface as independent error conditions across commercial SDKs (Regula Document Reader) and open-source validators (OST Kinegram eMRTD Validator).

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

### 🤖 Her (她) — an agent that lives on your iPhone

An agent that stays on your phone's screen, reads what is on it, and carries out what you ask in one sentence.

- Reads the screen **on-device** (about 0.6 s), also from the background
- Multi-step tasks: tap by label, search, pick the n-th result, go back, scroll, **up to six steps in a row**
- Route memory: the same three-step request took **49.8 s** the first time and **18.4 s** the second
- Safety gate: never taps pay or delete; taps Send only if you said to; does nothing while the phone is locked
- Heavier reasoning runs on your own computer; the phone falls back to Apple's on-device model when it is unreachable

Native iOS. iOS does not let an app operate other apps, so acting on the phone needs the paired computer.

*In active development, not released.*

---

### 🧪 VIATREE BOT — desktop AI assistant app and security-domain models

A personal AI assistant app for your desktop, and the security-domain language models I am training for it, fine-tuned from open-weight Qwen3 bases on a single A100 80GB.

- Method: refusal-direction ablation, then LoRA supervised fine-tuning on security corpora
- Release gate on a self-built 72-question probe set: hard-refusal rate at most **15%**, false-pass rate at most **5%**, perplexity ratio at most **1.05**; a candidate that misses one does not ship
- 4B clears all three; 32B text holds perplexity ratio at **1.0013** but sits at **10.7%** false-pass; a 32B vision-language model is merged with the same gap; the first 14B run failed and will be redone

*In active development, not released. Numbers are my own measurements. Stay tuned.*

---

### 🌳 VIATREE

The platform I'm building to turn security research into something usable — packaging tooling, findings and demo material into verifiable, shareable outputs, with a distribution and delivery pipeline of its own. Same discipline as everything else here: nothing ships as a claim unless it's measured.

*In active development.*

→ [viatreebot.com](https://viatreebot.com)

---

### Working principles

- **No fabricated metrics.** If a number isn't measured, it doesn't ship.
- **Open standards over vendor SDKs.** If it passes here, it passes at a real border.
- **On-device by default.** Cloud only as an explicit, declared fallback.

---

📧 303@viatreebot.com · 🌐 [viatreebot.com](https://viatreebot.com) · 💼 [linkedin.com/in/viatree](https://linkedin.com/in/viatree)
