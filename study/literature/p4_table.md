**Table 1: Comparison of WorldModelBench to other existing video benchmarks: VBench, VideoArena, and VideoPhy.**

![Table 1 source image](p4_table1.png)

| Category | Metric | VBench | VideoArena | VideoPhy | Ours |
|---|---|---|---|---|---|
| Metrics | Instruction Following | ✓ | × | ✓ | ✓ |
|  | Common Sense | ✓ | × | × | ✓ |
|  | Physics Adherence | × | × | ✓ | ✓ |
| Support Types | T2V | ✓ | ✓ | ✓ | ✓ |
|  | I2V | ✓ | ✓ | × | ✓ |
| Basic Statistics | Prompt Suite Size | 946 | 1500 | 688 | 350 |
|  | Human Label | - | 30k | 73k | 67k |
|  | Label Release? | - | No | No | Yes |

---

**Table 2: Vote statistics of WorldModelBench.**

![Table 2 source image](p4_table2.png)

| Basic Statistics | Value | Agreement Statistics | Value |
|---|---|---|---|
| # complete votes | 8336 | Pairwise agreement | 70.0% |
| # voters | 65 | Score agreement (±2) | 87.1% |
| # votes per video | 1.70 | Experts agreement (±σ) | 96.2% |
| # labels | 67K | Crowd agreement (±σ) | 95.4% |

---

**Table 3: Model performance on WorldModelBench on human annotations. Bold and underline indicates the best performance over all models, and open models respectively. "Deform.", "Penetr.", "Grav." is short for "Deformation", "Penetration", "Gravitation".**

![Table 3 source image](p4_table3.png)

| Group | Model | Instruction | Common Sense (Frame) | Common Sense (Temporal) | Physics Adherence (Newton) | Physics Adherence (Mass) | Physics Adherence (Fluid) | Physics Adherence (Penetr.) | Physics Adherence (Grav.) | Total |
|---|---|---|---|---|---|---|---|---|---|---|
| Closed Models | KLING [27] | **2.36** | **0.94** | **0.92** | 0.93 | **0.88** | 0.96 | 0.89 | 0.93 | **8.82** |
|  | Minimax [37] | 2.29 | 0.91 | 0.88 | 0.93 | 0.81 | 0.96 | 0.86 | 0.94 | 8.59 |
|  | Mochi-official [3] | 2.01 | 0.89 | 0.83 | **0.94** | 0.82 | **0.99** | **0.92** | **0.98** | 8.37 |
|  | Runway [44] | 2.15 | 0.87 | 0.78 | 0.91 | 0.69 | 0.94 | 0.82 | 0.91 | 8.08 |
|  | Luma [35] | 2.01 | 0.81 | 0.76 | 0.89 | 0.62 | 0.95 | 0.77 | 0.90 | 7.72 |
| Open Models | Mochi [3] | 2.22 | 0.63 | 0.63 | **<u>0.94</u>** | 0.58 | <u>0.97</u> | 0.71 | 0.94 | <u>7.62</u> |
|  | OpenSoraPlan-T2V [28] | 1.79 | <u>0.70</u> | <u>0.77</u> | 0.9 | <u>0.66</u> | <u>0.97</u> | <u>0.89</u> | 0.93 | 7.61 |
|  | CogVideoX-T2V [56] | 2.11 | 0.60 | 0.51 | 0.91 | 0.52 | 0.96 | 0.74 | 0.95 | 7.31 |
|  | CogVideoX-I2V [56] | 1.89 | 0.56 | 0.43 | 0.87 | 0.43 | 0.96 | 0.66 | <u>0.96</u> | 6.75 |
|  | OpenSora-Plan-I2V [28] | 1.77 | 0.47 | 0.54 | 0.84 | 0.42 | <u>0.97</u> | 0.70 | 0.92 | 6.62 |
|  | Pandora [53] | 1.56 | 0.42 | 0.53 | 0.91 | 0.50 | 0.96 | 0.74 | 0.94 | 6.57 |
|  | T2VTurbo [32] | 1.33 | 0.49 | 0.43 | 0.88 | 0.42 | 0.96 | 0.75 | <u>0.96</u> | 6.22 |
|  | OpenSora-T2V [62] | 1.71 | 0.40 | 0.33 | 0.89 | 0.32 | 0.95 | 0.60 | 0.92 | 6.11 |
|  | OpenSora-I2V [62] | 1.60 | 0.37 | 0.25 | 0.90 | 0.25 | 0.92 | 0.60 | 0.94 | 5.83 |

---

**Table 4: Score comparison between scores provided by humans and the judge model. The averaged predicting error (1/n Σ |Judge − Human| / Human) is 4.1%. The highest prediction error is 6.81%, showing the reliability of our judge model.**

![Table 4 source image](p4_table4.png)

| Group | Model | Scores↑ Human (H) | Scores↑ Judge (J) | Prediction Error (100%) |
|---|---|---|---|---|
| Closed Models | kling | 8.82 | 9.08 | 2.95% |
|  | minimax | 8.59 | 8.92 | 3.84% |
|  | mochi-official | 8.37 | 8.66 | 3.46% |
|  | runway | 8.08 | 8.63 | 6.81% |
|  | luma | 7.72 | 8.24 | 6.74% |
| Open Models | mochi | 7.62 | 7.91 | 3.81% |
|  | OpenSoraPlan-T2V | 7.61 | 8.04 | 5.65% |
|  | CogVideoX-T2V | 7.31 | 7.65 | 4.65% |
|  | CogVideoX-I2V | 6.75 | 7.08 | 4.89% |
|  | OpenSora-Plan-I2V | 6.63 | 6.86 | 3.47% |
|  | pandora | 6.57 | 6.90 | 5.02% |
|  | T2VTurbo | 6.22 | 6.56 | 5.47% |
|  | OpenSora-T2V | 6.11 | 6.17 | 0.98% |
|  | OpenSora-I2V | 5.83 | 5.82 | -0.17% |

---

**Table 5: Model prediction error results of different judge choices on WorldModelBench. VILA-2B is a vision-language model with 2B parameters, trained on image and video understanding tasks [33]. We report the average error rate between the model's predictions and the ground truth.**

![Table 5 source image](p4_table5.png)

| Model Prediction Error +Method | Instruction (%) following ↓ | Common (%) Sense ↓ | Physics (%) Adherence ↓ |
|---|---|---|---|
| GPT-4o | 29.3 | 35.0 | 36.0 |
| +CoT | 29.7 | 28.5 | 45.6 |
| Gemini-1.5-Pro | 30.7 | 34.5 | 29.3 |
| +CoT | 29.3 | 19.5 | 28.3 |
| Qwen2-VL-2B | 30.3 | 39.0 | 39.7 |
| VILA-2B +Zero-Shot | **21.0** | 28.0 | **24.0** |
| VILA-2B +CoT Fine-tuned | 32.3 | **16.4** | 29.7 |
