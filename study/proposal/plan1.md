# 🤖 ACTION-ATLAS — Plan & Novelty (solo · inference-only)

## 🆕 Table 1 — Novelty audit (🔴 scooped · 🟡 differentiate · 🟢 defensible)

| 🆕 Novelty proposal | 📚 Papers covering similar work (venue) | 🔧 FIX to modify / maintain novelty |
|---|---|---|
| 🟢⭐ **THE wedge (1 sentence):** "First fair, capability-indexed, closed-loop comparison of all 4 families (VLA/LWM/WAM/WFM) on real-world dense scenes (**WalkIndia**), with a VLA-relative advantage score." | WorldArena (WM types only, no VLA) · World-in-World (visual WMs only) · RoboArena (policies only, CoRL'25) · COLOSSEUM (sim perturb, not real video) | Lead §1 with this exact sentence, written **against WorldArena/VLABench from day one**. |
| 🟢🇮🇳 **WalkIndia data moat** — Indian dense-street dashcam **replay eval** | nuScenes / Waymo (AV, not embodied replay) · COLOSSEUM (sim) · JRDB (campus, not dense street) | **Un-scoopable** — nobody else has this video. Privacy-safe release = adoption engine. |
| 🔴 **"Missing benchmark" framing** | WorldModelBench (CVPR'25) · EWMBench (arXiv'25) · WorldSimBench · EVA (ICML'25) | ❌ Delete the claim. Add Related Work; position as **complementary**, not first. |
| 🔴 **Capability-centric benchmark** | VLABench (ICCV'25) · WorldArena (arXiv'26) · "Understanding World or Predicting Future?" (ACM CSUR'25) | Reframe: "first to map **capabilities → 4-family prediction spectrum** under one VLA-baselined metric." Cite all three. |
| 🔴 **World Advantage Score (WAS)** | 🚨 WorldArena **EWMScore** (holistic index) · WorldEval · WMPO | Differentiate: WAS = **capability-resolved × VLA-baselined** (EWMScore is model-holistic). Bound it + weight $w_j$ sensitivity. |
| 🔴 **"Prediction ≠ behavior"** burden of proof | WorldArena · World-in-World · EWMBench · WMPO | Concede principle is established → claim = **applying it across all 4 families at once**. |
| 🟢 **4-family taxonomy** (VLA→LWM→WAM→WFM) | Surveys: ACM CSUR'25 · "World Model for Robot Learning" | ⬇️ Demote to "framing," not a contribution. Cite surveys. |
| 🟡 **Absent Objects** domain | LIBERO-Mem · MIKASA-Robo · MemoryBench (arXiv'25) | ♻️ Reuse LIBERO-Mem. Novelty = cross-family WAS. |
| 🟡 **Counterfactual Futures** domain | Dream2Fix (arXiv'26) · FailSafe→RoboFail (arXiv'25) | ♻️ Reuse RoboFail. Differentiate via counterfactual **selection (CSA)**. |
| 🟡 **Temporal Coordination** domain | CALVIN · LIBERO-Long · VLABench (ICCV'25) | ♻️ Reuse CALVIN / LIBERO-Long. Novelty = **LHCR × WAS**. |
| 🟡 **ION** domain (forecast other agents) | JRDB · Social-HM3D/MP3D · 🚨 NavThinker (WAM-for-social, arXiv'26) | ♻️ Reuse Social-HM3D / JRDB. Cite & differentiate NavThinker (you compare families; they propose 1 method). |

---

## 🚦 Table 2 — Tier-1 readiness

| 🧪 Dimension | 🚦 Status | 🗒️ Action |
|---|---|---|
| Novelty | 🟢 wedge + 🇮🇳 moat | Lead with WalkIndia + 4-family fair comparison |
| Experiments | 🟢 cheap, solo | **Frozen-inference replay matrix** (no training, no sim, no robot) |
| Related work | 🔴 0 benchmark refs | Cite WorldArena / VLABench / WorldModelBench / UniSim / iVideoGPT |
| WAS soundness | 🟡 weak | Bound WAS · pin $m_{\text{VLA}}$=OpenVLA · 3 weight settings · bootstrap CIs · head ablation |
| Target venue | 🎯 fit | NeurIPS D&B · CoRL · RSS |

---

## 🧩 Table 3 — Models (all frozen, inference-only)

| 👪 Family | 🧊 Frozen open models (closed → proxy) | 🔌 Uniform adapter |
|---|---|---|
| 🦾 VLA | OpenVLA-7B · Octo · π0 · GR00T N1.7 (RT-2/Gemini → proxy) | native head — zero added |
| 🧠 LWM | V-JEPA 2 (+ 2-AC) · I-JEPA | same tiny linear head **+ HSLA probe** |
| 🎬 WAM | UVA · iVideoGPT | native rollout → action, frozen |
| 🌍 WFM | Cosmos-Predict2.5 · Cosmos-Reason (critic) | frozen predictor/critic + tiny head |

---

## 🗺️ Table 4 — Domains → offline replay set + headline metric

| 🎯 Domain | ♻️ Offline replay set (score frozen models, don't author) | 📐 Metric |
|---|---|---|
| 👁️ Absent Objects | LIBERO-Mem · MIKASA-Robo | HSLA |
| 🔮 Counterfactual Futures | RoboFail (FailSafe) · Dream2Fix | CSA · RSR |
| ⏳ Temporal Coordination | CALVIN · LIBERO-Long | LHCR |
| 🚸 ION (social) | JRDB · Social-HM3D/MP3D | SPR |
| 🇮🇳 DenseWorld = **WalkIndia** | your dashcam replay (frame_t → predict → score vs frame_{t+1}) | $D_{\text{Dense}}$ · WAS |
| ✅ Sanity | SimplerEnv replay | TSR · **WAS vs OpenVLA** |

---

## 🔧 Table 5 — Execution (100% solo · inference-only · 8 steps)

| # | 🪜 Step | ⚙️ How | 📤 Output |
|---|---|---|---|
| 1 | 🎯 **Lock the wedge** | Write §1 around the one-sentence claim (Table 1) vs WorldArena/VLABench from day 1 | framed §1 |
| 2 | 🇮🇳 **Build WalkIndia moat** | Dashcam clips → replay eval: model sees frame_t → predicts next action/state → score vs real frame_{t+1}. No robot, no sim, pure inference | un-scoopable eval set |
| 3 | ♻️ **Reuse, never hand-build** | Pull LIBERO-Mem (Absent), COLOSSEUM (DenseWorld perturb), JRDB (social) as **offline trajectory sets**; score frozen models | 4 domains, no authored tasks |
| 4 | ⚖️ **One harness, one fair rule** | Every family = same frozen backbone + same tiny linear head (or zero head); **ablate the head** → proves WAS measures representation, not glue | fair protocol + ablation |
| 5 | 📏 **Pin + stress-test WAS** | Fix $m_{\text{VLA}}$=OpenVLA; **bound WAS** (near-zero baseline can't blow up); report 3 weight settings + bootstrap CIs | robust metric |
| 6 | 🧮 **Run the cheap matrix** | ~6 frozen models × 4 domains; fill Table 6 + per-model tables + radar. **Headline: scatter open-loop prediction score vs closed-loop success → show they diverge** | results + 1 measured finding |
| 7 | 🔁 **Ship the flywheel (15-day)** | Public leaderboard + auto-eval script: ingest any new HF checkpoint → frozen inference → update ranks → auto-post | adoption engine |
| 8 | 📦 **Release everything** | Code + WalkIndia replay (pointer, blurred faces/plates) + eval scripts + leaderboard | citations = **P0** |

---

## ⚠️ Table 6 — Risks → fixes

| ⚠️ Risk | 🛡️ Fix |
|---|---|
| Reviewer: "offline replay ≠ true closed-loop" | Frame as action-replay w/ feedback; validate a subset on SimplerEnv closed-loop |
| WalkIndia privacy (faces / plates) | Blur faces + plates; release pointer + license, not raw video |
| WalkIndia action labels noisy | Derive ego-action from IMU / optical flow; report label-noise bound |
| "Head does the work, not the model" | Zero-head vs linear-head **ablation** isolates representation |
| WAS unstable at near-zero baseline | Bound/clip WAS · pin $m_{\text{VLA}}$=OpenVLA · weight sensitivity |
| Embodiment mismatch confound | Same frozen backbone + same head for all families |

---

## 🔗 Table 7 — Key prior-art links

| 🏷️ Topic | 📄 Paper (venue) | 🔗 Link |
|---|---|---|
| Thesis + metric scoop | WorldArena / EWMScore (arXiv'26) | https://arxiv.org/abs/2602.08971 |
| Unified closed-loop | World-in-World (arXiv'25) | https://arxiv.org/pdf/2510.18135 |
| Capability VLA bench | VLABench (ICCV'25) | https://arxiv.org/abs/2412.18194 |
| WM benchmark | WorldModelBench (CVPR'25) | https://worldmodelbench.github.io/ |
| WM-as-sim · action-cond WM | UniSim (ICLR'24) · iVideoGPT (NeurIPS'24) | https://iclr.cc/virtual/2024/oral/19722 · https://neurips.cc/virtual/2024/poster/96668 |
| Stress test | THE COLOSSEUM (RSS'24) | https://roboticsconference.org/2024/program/papers/133/ |
| WM improves VLA | WMPO (arXiv'25) | https://arxiv.org/html/2511.09515v1 |
| Object permanence | LIBERO-Mem (arXiv'25) | https://arxiv.org/html/2511.11478 |
| Counterfactual recovery | Dream2Fix · FailSafe | https://arxiv.org/abs/2603.13528 · https://arxiv.org/html/2510.01642v2 |
| Social WAM | NavThinker (arXiv'26) | https://arxiv.org/pdf/2603.15359 |
| Survey framing | "Understanding World or Predicting Future?" (ACM CSUR'25) | https://github.com/tsinghua-fib-lab/World-Model |
