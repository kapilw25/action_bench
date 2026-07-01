**Table 1: Comparison of existing world model benchmarks and WorldArena across three key evaluation dimensions.**

![Table 1 source image](p2_table1.png)

| Benchmark | Video Quality Visual Quality | Video Quality Motion Quality | Video Quality Content Consist. | Video Quality Physics Adher. | Video Quality Control ability | Video Quality 3D Acc. | Embodied Tasks Data Engine | Embodied Tasks Policy Eval. | Embodied Tasks Action Planner | Human |
|---|---|---|---|---|---|---|---|---|---|---|
| WorldModelBench (Li et al., 2025a) | ✗ | ✗ | ✗ | ✓ | ✓ | ✗ | ✗ | ✗ | ✗ | ✓ |
| WorldSimBench (Qin et al., 2024) | ✓ | ✓ | ✓ | ✗ | ✓ | ✗ | ✗ | ✗ | ✓ | ✓ |
| WorldScore (Duan et al., 2025) | ✓ | ✓ | ✓ | ✗ | ✓ | ✓ | ✗ | ✗ | ✗ | ✓ |
| 4DWorldBench (Lu et al., 2025) | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✗ | ✗ | ✗ | ✓ |
| EWMBench (Yue et al., 2025) | ✗ | ✓ | ✓ | ✗ | ✓ | ✗ | ✗ | ✗ | ✗ | ✓ |
| WorldEval (Li et al., 2025b) | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ | ✓ | ✗ | ✗ |
| World-in-World (Zhang et al., 2025) | ✓ | ✓ | ✗ | ✗ | ✓ | ✗ | ✗ | ✗ | ✓ | ✗ |
| WoW-World-Eval (Fan et al., 2026) | ✓ | ✓ | ✓ | ✓ | ✓ | ✗ | ✗ | ✗ | ✓ | ✓ |
| **WorldArena (Ours)** | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |

---

**Table 2: Video quality evaluation results across visual quality, motion quality and content consistency dimensions.**

![Table 2 source image](p2_table2.png)

| Models | Visual Quality Image Quality | Visual Quality Aesthetic Quality | Visual Quality JEPA Similarity | Motion Quality Dynamic Degree | Motion Quality Flow Score | Motion Quality Motion Smoothness | Content Consistency Subject Consist. | Content Consistency Background Consist. | Content Consistency Photometric Consist. |
|---|---|---|---|---|---|---|---|---|---|
| GigaWorld-0 | 0.5041 | 0.3991 | 0.4413 | 0.6709 | 0.3118 | 0.7811 | 0.7303 | 0.8563 | 0.1756 |
| Genie Envisioner | 0.2305 | 0.3289 | 0.3340 | <u>0.6930</u> | 0.0855 | 0.6966 | 0.7760 | 0.9024 | 0.2006 |
| TesserAct | 0.3322 | <u>0.4590</u> | 0.4579 | 0.5150 | 0.2447 | 0.7579 | 0.8250 | **0.9238** | 0.2491 |
| RoboMaster | 0.3487 | 0.3842 | 0.2966 | 0.6124 | 0.1484 | 0.6940 | 0.8295 | <u>0.9123</u> | 0.3356 |
| Vidar | 0.4145 | 0.4068 | 0.5608 | 0.2767 | 0.1426 | <u>0.7973</u> | 0.7629 | 0.8300 | 0.2350 |
| Cosmos-Predict 2.5 (text) | <u>0.6668</u> | 0.4501 | 0.3126 | 0.5911 | <u>0.4302</u> | 0.7882 | 0.7488 | 0.8511 | 0.1383 |
| Cosmos-Predict 2.5 (action) | 0.4489 | 0.3576 | 0.9296 | 0.3994 | 0.0573 | 0.7100 | 0.8197 | 0.8894 | 0.3528 |
| WoW | 0.4587 | 0.3868 | 0.7440 | 0.4608 | 0.2706 | 0.7692 | 0.8161 | 0.9025 | 0.2170 |
| CtrlWorld | 0.3522 | 0.3893 | 0.9185 | 0.4257 | 0.3449 | 0.7377 | **0.8411** | 0.9057 | 0.1729 |
| Wan 2.2 | 0.3884 | 0.3963 | 0.7575 | 0.4349 | 0.1269 | 0.7019 | <u>0.8388</u> | 0.9042 | **0.4776** |
| CogvideoX | 0.3582 | 0.3777 | **0.9384** | 0.3166 | 0.2189 | 0.7391 | 0.8083 | 0.8773 | <u>0.3580</u> |
| IRASim | 0.3489 | 0.3623 | <u>0.9330</u> | 0.4139 | 0.2083 | 0.7052 | 0.8312 | 0.9068 | 0.3522 |
| Veo 3.1 | 0.6605 | **0.4632** | 0.5694 | 0.5450 | 0.1396 | 0.6989 | 0.7878 | 0.8710 | 0.3247 |
| Wan 2.6 | **0.6824** | 0.4433 | 0.7229 | **0.7421** | **0.4532** | **0.8539** | 0.7517 | 0.8687 | 0.1904 |

---

**Table 3: Video quality evaluation results across physics adherence, 3D accuracy and controllability dimensions.**

![Table 3 source image](p2_table3.png)

| Models | Physics Adherence Interaction Quality | Physics Adherence Trajectory Acc. | 3D Accuracy Depth Acc. | 3D Accuracy Perspectivity | Controllability Instruction Following | Controllability Semantic Alignment | Controllability Action Following |
|---|---|---|---|---|---|---|---|
| GigaWorld-0 | 0.5368 | 0.1552 | 0.6316 | 0.7596 | 0.6156 | 0.8591 | <u>0.1134</u> |
| Genie Envisioner | 0.2052 | 0.0679 | 0.8663 | 0.5284 | 0.2028 | 0.8544 | 0.0109 |
| TesserAct | 0.5800 | 0.1396 | 0.7159 | 0.7920 | 0.6152 | 0.8783 | 0.0311 |
| RoboMaster | 0.5364 | 0.1158 | 0.8335 | 0.7588 | 0.5772 | 0.8761 | 0.0352 |
| Vidar | 0.5348 | 0.1928 | 0.7872 | 0.7592 | 0.5912 | 0.8826 | 0.0819 |
| Cosmos-Predict 2.5 (text) | 0.3872 | 0.0816 | 0.7051 | 0.7964 | 0.2664 | 0.7733 | **0.1418** |
| Cosmos-Predict 2.5 (action) | 0.5500 | 0.2945 | 0.8862 | 0.7644 | 0.5840 | 0.8879 | 0.0133 |
| WoW | 0.5564 | 0.2058 | 0.7283 | 0.7672 | 0.5692 | 0.8842 | 0.0434 |
| CtrlWorld | 0.6212 | **0.4766** | <u>0.9300</u> | 0.7960 | 0.7272 | <u>0.8912</u> | 0.0210 |
| Wan 2.2 | 0.5184 | 0.1627 | 0.7768 | 0.7660 | 0.5376 | 0.8877 | 0.0512 |
| CogvideoX | 0.5940 | 0.3526 | 0.9097 | 0.7828 | 0.7268 | **0.8977** | 0.0076 |
| IRASim | 0.5656 | <u>0.3639</u> | **0.9312** | 0.7788 | 0.6604 | 0.8849 | 0.0526 |
| Veo 3.1 | **0.7872** | 0.1231 | 0.7421 | **0.8276** | **0.9328** | 0.8607 | 0.0852 |
| Wan 2.6 | <u>0.7280</u> | 0.1182 | 0.7144 | <u>0.8032</u> | <u>0.8536</u> | 0.8728 | 0.0992 |

---

**Table 4: Task success rate of downstream policy models trained with generated data from different world models.**

![Table 4 source image](p2_table4.png)

| Model | Task 1 | Task 2 |
|---|---|---|
| π<sub>0.5</sub> policy model (zero-shot) | 2% | 5% |
| π<sub>0.5</sub> policy model (trained with real data) | 77% | 66% |
| Genie Envisioner (Liao et al., 2025) | 7% | 21% |
| TesserAct (Zhen et al., 2025) | 1% | 35% |
| RoboMaster (rob, 2025) | 7% | 68% |
| Vidar (Feng et al., 2025) | 13% | 53% |
| WoW (Chi et al., 2025) | 45% | 71% |
| Wan 2.2 (Wan et al., 2025) | 15% | 41% |

---

**Table 5: Task success rate of different world models directly as action planners in the RoboTwin simulator.**

![Table 5 source image](p2_table5.png)

| Model | Task 1 | Task 2 |
|---|---|---|
| π<sub>0.5</sub> policy model | 77% | 66% |
| Genie Envisioner (Liao et al., 2025) | 10% | 20% |
| TesserAct (Zhen et al., 2025) | 1% | 35% |
| RoboMaster (rob, 2025) | 8% | 20% |
| Vidar (Feng et al., 2025) | 2% | 19% |
| WoW (Chi et al., 2025) | 20% | 21% |
| Wan 2.2 (Wan et al., 2025) | 12% | 20% |
