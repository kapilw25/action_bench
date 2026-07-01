# 🤖 ACTION-ATLAS — Plan & Novelty (🇮🇳 India · DenseWorld · YouTube driving)

## 🎯 Table 1 — The novelty wedge (lead with this)

| 🆕 Element | 💡 Content |
|---|---|
| ⭐ One-sentence claim | "First benchmark testing whether the **world-model advantage survives real-world, socially-dense Indian street driving** (curated from **YouTube dashcam/driving clips**), and whether **forecasting other agents** is the mechanism — across all four prediction families (VLA/LWM/WAM/WFM) with a VLA-baselined advantage score (WAS)." |
| 🧱 Un-scoopable asset | Dense Indian-street driving video (YouTube): rickshaws, mixed traffic, street vendors, pedestrians, animals, night/rain — **no rival benchmark has this data** |
| 🕳️ Gap it fills | Every competitor is **simulation-only + single-agent**; none test **real-world + social/multi-agent + sim→real transfer** |
| 🎯 Positioning | Complementary to World-in-World (the *sim* half) → ACTION-ATLAS is the **real-world social** half |

---

## 🆕 Table 2 — Novelty audit (🔴 scooped · 🟡 differentiate · 🟢 defensible)

| 🆕 Claim | 📚 Prior work (venue) | 🔧 FIX / verdict |
|---|---|---|
| 🔴 Closed-loop "behavior not fidelity" WM benchmark | **World-in-World (ICLR'26 Oral)** · WorldArena (arXiv'26) | ❌ Don't claim. Cite WiW as the sim half; you = real-world social half |
| 🔴 **"Prediction ≠ behavior"** finding | World-in-World finding #1 · WorldModelBench (CVPR'25) | Concede it's established → your version = **on real Indian dense video** |
| 🔴 **WAS** = world-model advantage metric | WorldArena **EWMScore** · WiW base→+WM deltas | Differentiate: **capability-resolved × VLA-baselined × real-world social** |
| 🔴 "Missing / capability-centric benchmark" | VLABench (ICCV'25) · WorldArena | ❌ Delete "missing"; add Related Work; position complementary |
| 🟢🇮🇳 **Real-world socially-dense Indian driving (YouTube)** | nuScenes/Waymo (AV, not WM-advantage eval) · all rivals sim | ⭐ **The moat** — un-scoopable data |
| 🟢🚸 **Social / multi-agent (ION) as a capability axis** | WiW/WorldArena/VLABench all single-agent; NavThinker = 1 method, not a benchmark | ⭐ The differentiating capability |
| 🟢🔁 **Sim→real transfer of the WM advantage** | World-in-World is sim-only | ⭐ Open scientific question |
| 🟡 4-family taxonomy (VLA→LWM→WAM→WFM) | Embodied-WM surveys (ACM CSUR'25) | ⬇️ Demote to framing; cite surveys |

---

## 🇮🇳 Table 3 — DenseWorld-India data (YouTube driving clips)

| 🎬 Aspect | 📋 Detail |
|---|---|
| Source | YouTube India dashcam / driving vlogs (Creative-Commons + fair-use research) |
| Scenes | Crowded markets · mixed traffic · rickshaws/buses · street vendors · pedestrians · domestic animals |
| Splits | normal · dense-market · night · rain · animal-crossing |
| Unit | short clips → frames; ego-action derived from optical flow / steering proxy |
| Eval mode | offline **replay / counterfactual action-agreement** + generative-sim closed-loop subset |
| Labels | ego-action, other-agent tracks, crossing/stop intent, collision-risk flags |
| Privacy | blur faces + license plates; release **URLs + timestamps + labels**, not raw video |
| Release | pointer-only dataset + auto-download + blur pipeline |

---

## 🧩 Table 4 — Four model families (unified protocol) + WAS

| # | 👪 Family | 🔮 Predicts | 🧊 Frozen models | 🔌 Role / adapter |
|---|---|---|---|---|
| I | 🦾 **VLA policy** | observation + language → action | OpenVLA-7B · Octo · π0 · GR00T N1.7 | **baseline $m_{\text{VLA}}$**, native head (zero added) |
| II | 🧠 **LWM (JEPA latent)** | predictive latent state | V-JEPA 2 (+2-AC) · I-JEPA | needs downstream policy head + HSLA probe |
| III | 🎬 **WAM (world-action)** | future states + executable actions (jointly) | UVA · iVideoGPT | rollout → action (frozen) |
| IV | 🌍 **WFM (world foundation)** | large-scale world simulation | Cosmos-Predict2.5 · Cosmos-Reason | simulator / planner / policy backbone + tiny head |
| — | 📏 **WAS** | capability-level gain vs direct action prediction | $\dfrac{S(c,m)-S(c,m_{\text{VLA}})}{S(c,m_{\text{VLA}})+\epsilon}$ | statistically-significant advantage (bootstrap CIs) |

---

## 🗺️ Table 5 — Capability domains → data + headline metric

| 🎯 Domain | ♻️ Data (reuse or 🇮🇳 India) | 📐 Metric |
|---|---|---|
| 👁️ Absent Objects | LIBERO-Mem · MIKASA-Robo | HSLA |
| 🔮 Counterfactual Futures | RoboFail (FailSafe) · Dream2Fix | CSA · RSR |
| ⏳ Temporal Coordination | CALVIN · LIBERO-Long | LHCR |
| 🚸 **ION (social)** ⭐ | 🇮🇳 India YouTube dense + JRDB · Social-HM3D | SPR · social-collision |
| 🌪️ **DenseWorld-India** ⭐ | 🇮🇳 YouTube driving clips | $D_{\text{Dense}}$ · WAS |
| ✅ Sanity | SimplerEnv replay | TSR · WAS vs OpenVLA |

---

## 🔧 Table 6 — Execution (100% solo · inference-only)

| # | 🪜 Step | 📤 Output |
|---|---|---|
| 1 | 🎯 Lock the wedge; write §1 vs World-in-World/WorldArena from day 1 | framed §1 |
| 2 | 🇮🇳 Curate YouTube India clips → blur faces/plates → derive ego-actions & agent tracks | DenseWorld-India set |
| 3 | ♻️ Reuse LIBERO-Mem / RoboFail / CALVIN / Social-HM3D as offline sets | 4 non-India domains |
| 4 | ⚖️ One harness: same frozen backbone + same tiny head (or zero); **ablate head** | fair protocol + ablation |
| 5 | 📏 WAS: pin $m_{\text{VLA}}$=OpenVLA · bound it · 3 weight settings · bootstrap CIs | robust metric |
| 6 | 🧮 Frozen 4-family × domain matrix; **scatter generative-score vs real behavior → divergence** | results + 1 measured finding |
| 7 | 🔁 Leaderboard + auto-eval: ingest any HF checkpoint → frozen inference → rank | adoption engine |
| 8 | 📦 Release pointer-dataset + blur pipeline + eval scripts + leaderboard | citations = **P0** |

---

## ⚠️ Table 7 — Risks → fixes

| ⚠️ Risk | 🛡️ Fix |
|---|---|
| Core thesis scooped by World-in-World (Oral) | Pivot to **real-world social India**; cite WiW as the sim half |
| Can't truly close the loop on recorded video | (i) validate replay proxy vs a sim closed-loop subset · (ii) YouTube → generative social sim · (iii) small real-robot trial |
| YouTube licensing / privacy | Pointer-only release · blur faces + plates · CC + fair-use research clips |
| Ego-action labels noisy | Optical-flow / steering proxy + report label-noise bound |
| "Head does the work, not the model" | Zero-head vs linear-head **ablation** isolates representation |
| WAS unstable at near-zero baseline | Bound/clip · pin OpenVLA · weight sensitivity |
| Embodiment mismatch confound | Same frozen backbone + same head for all families |

---

## 🔗 Table 8 — Key prior-art links

| 🏷️ Topic | 📄 Paper (venue) | 🔗 Link |
|---|---|---|
| 🚨 Core thesis scoop | World-in-World (**ICLR'26 Oral**) | https://arxiv.org/abs/2510.18135 |
| Thesis + metric scoop | WorldArena / EWMScore (arXiv'26) | https://arxiv.org/abs/2602.08971 |
| Capability VLA bench | VLABench (ICCV'25) | https://arxiv.org/abs/2412.18194 |
| WM benchmark | WorldModelBench (CVPR'25) | https://worldmodelbench.github.io/ |
| WM improves VLA | WMPO (arXiv'25) | https://arxiv.org/html/2511.09515v1 |
| Social WAM (method) | NavThinker (arXiv'26) | https://arxiv.org/html/2603.15359 |
| Object permanence | LIBERO-Mem (arXiv'25) | https://arxiv.org/html/2511.11478 |
| Counterfactual recovery | Dream2Fix · FailSafe | https://arxiv.org/abs/2603.13528 · https://arxiv.org/html/2510.01642v2 |
| Egocentric real sim | EgoSim (arXiv'26) | https://arxiv.org/abs/2604.01001 |
| Survey framing | "Understanding World or Predicting Future?" (ACM CSUR'25) | https://github.com/tsinghua-fib-lab/World-Model |
