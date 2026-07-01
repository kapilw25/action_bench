# 🤖 ACTION-ATLAS

> Beyond Action Prediction: **what must world models achieve to surpass Vision-Language-Action systems** — and does that advantage survive **real-world, socially-dense Indian street driving**?

## 🎯 Table 1 — What this is

| 🧩 Field | 📋 Value |
|---|---|
| Core question | Which robotic capabilities genuinely need predictive world models, and when does prediction improve *action* (not just visual fidelity)? |
| ⭐ Novelty wedge | Does the world-model advantage **survive real-world, socially-dense Indian street driving** (🇮🇳 curated from YouTube driving clips), and is **forecasting other agents** the mechanism? |
| Families compared | I **VLA** · II **LWM** (JEPA latent) · III **WAM** (world-action) · IV **WFM** (world foundation) |
| Metric | **WAS** — capability-level, VLA-baselined, bootstrap-significant advantage over direct action prediction |
| Mode | Solo · frozen · inference-only (offline replay + sim closed-loop subset) |
| Status | 🔴 pre-experiment — repositioning novelty vs World-in-World (ICLR'26 Oral) / WorldArena |
| Target venue | NeurIPS D&B · CoRL · RSS |

---

## 🗂️ Table 2 — Repository layout

| 📁 Path | 📦 Contents |
|---|---|
| `README.md` | This top-level guide |
| `study/README.md` | Research-package guide (detailed) |
| `study/proposal/proposal_ACTION_ATLAS.md` · `.pdf` | Full proposal (taxonomy, benchmark, metrics, findings) |
| `study/proposal/plan1.md` | Execution + novelty plan (🇮🇳 India / DenseWorld / YouTube focus) — tables only |
| `study/literature/p_all_table.md` | All competitor tables combined — 6 papers · 21 tables · 25 images |
| `study/literature/p{1..6}_table.md` | Per-paper extracted tables + embedded source images |
| `study/literature/p{1..6}_*.pdf` · `*.png` | 6 source papers + 25 table screenshots |

---

## 🧩 Table 3 — Four prediction families + WAS

| # | 👪 Family | 🔮 Predicts | 🔌 Role |
|---|---|---|---|
| I | 🦾 VLA policy | observation + language → action | baseline $m_{\text{VLA}}$ |
| II | 🧠 LWM (JEPA latent) | predictive latent state | needs downstream policy head |
| III | 🎬 WAM (world-action) | future states + executable actions | plan via rollout |
| IV | 🌍 WFM (world foundation) | large-scale world simulation | simulator / planner / backbone |
| — | 📏 **WAS** | gain vs direct action prediction | $\dfrac{S(c,m)-S(c,m_{\text{VLA}})}{S(c,m_{\text{VLA}})+\epsilon}$ |

---

## 🆕 Table 4 — Novelty status

| 🚦 | Claim | Verdict |
|---|---|---|
| 🔴 | Closed-loop "behavior not fidelity" benchmark · "prediction ≠ behavior" · WAS · "missing benchmark" | Scooped — World-in-World (ICLR'26 Oral) · WorldArena · VLABench · WorldModelBench |
| 🟢 | 🇮🇳 Real-world socially-dense Indian driving (YouTube) | **Un-scooped — the moat** |
| 🟢 | 🚸 Social / multi-agent (ION) capability axis | **Un-scooped** (rivals are single-agent) |
| 🟢 | 🔁 Sim→real transfer of the world-model advantage | **Open question** |

---

## 📚 Table 5 — Competitor papers (`study/literature/`)

| # | Paper | Venue |
|---|---|---|
| p1 | World-in-World: World Models in a Closed-Loop World | ICLR'26 Oral |
| p2 | WorldArena: Perception + Functional Utility of Embodied WMs | arXiv'26 |
| p3 | VLABench: Language-Conditioned Manipulation w/ Long-Horizon Reasoning | ICCV'25 |
| p4 | WorldModelBench: Judging Video Gen Models as World Models | CVPR'25 |
| p5 | WorldScore: Unified Evaluation for World Generation | arXiv |
| p6 | WorldSimBench: Video Gen Models as World Simulators | arXiv |

---

## ▶️ Table 6 — Next actions

| # | Action | Priority |
|---|---|---|
| 1 | Curate + privacy-blur YouTube India driving clips (DenseWorld-India) | 🔴 P0 |
| 2 | Rewrite §1 + abstract as "ACTION-ATLAS-Social" vs World-in-World | 🔴 P0 |
| 3 | Build frozen 4-family inference harness + uniform-head ablation | 🟡 P1 |
| 4 | Run matrix → WAS + generative-vs-behavior divergence scatter | 🟡 P1 |
| 5 | Leaderboard + pointer-dataset release | 🟢 P2 |
