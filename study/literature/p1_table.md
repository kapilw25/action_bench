**Table 1: Active Recognition (AR) and Image-Goal Navigation (ImageNav) performance across various models and base policies. Higher success rate (SR%), success weighted by path length (SPL%), and lower mean trajectory length (Mean Traj.) are better. "†" denotes our post-trained video generators.**

![Table 1 source image](p1_table1.png)

| Model Type | Method | Control Type | Input Type | #Param. | AR SR↑ | AR Mean Traj.↓ | ImageNav SR↑ | ImageNav Mean Traj.↓ | ImageNav SPL↑ |
|---|---|---|---|---|---|---|---|---|---|
| Base Policy | Heuristic (w/o WM) | – | RGB | – | 39.02 | 8.81 | 2.08 | 59.6 | 0.63 |
| + Video Gen. Post-Train | SVD† | Action | RGB; Pano | 1.5B | <u>60.62</u> | <u>5.17</u> | <u>20.83</u> | **58.5** | **11.86** |
|  | WAN2.1† | Action | RGB; Pano | 14B | **62.98** | **4.71** | **22.92** | <u>58.7</u> | <u>11.63</u> |
| Base Policy | VLM (w/o WM) | – | RGB | 72B | 50.27 | 6.24 | 35.42 | 47.5 | 25.88 |
| + Image Gen. | PathDreamer | Viewpoint | RGB-D; Pano | 0.69B | 56.99 | 5.28 | 36.80 | 47.3 | 26.85 |
| + Image Gen. | SE3DS | Viewpoint | RGB-D; Pano | 1.1B | 57.53 | 5.29 | 36.11 | 47.0 | 26.91 |
| + Video Gen. | NWM | Trajectory | RGB | 1B | 57.35 | 5.68 | 40.28 | 47.1 | 27.83 |
| + Video Gen. Zero-Shot | SVD | Image | RGB | 1.5B | 57.71 | 5.29 | <u>40.28</u> | <u>46.4</u> | <u>28.59</u> |
|  | LTX-Video | Text | RGB | 2B | 56.08 | 5.37 | 36.81 | 47.5 | 25.85 |
|  | Hunyuan | Text | RGB | 13B | 57.71 | 5.21 | 36.11 | 46.8 | 26.89 |
|  | Wan2.1 | Text | RGB | 14B | 58.26 | 5.24 | 38.19 | 48.2 | 25.92 |
|  | Wan2.2 | Text | RGB | 5B | 55.35 | 5.73 | 38.88 | 46.5 | <u>28.87</u> |
|  | Cosmos-P2 | Text | RGB | 2B | 55.35 | 5.71 | 36.81 | 47.6 | 25.89 |
|  | Wan2.2 | Text | RGB | A14B | <u>59.53</u> | <u>4.91</u> | **43.05** | **45.8** | **31.46** |
|  | Runway Gen4 (proprietary) | Text | RGB | – | **64.79** | **4.06** | - | - | - |
| + Video Gen. Post-Train | SVD† | Action | RGB; Pano | 1.5B | 60.98 | 5.02 | 43.05 | 46.0 | 30.96 |
|  | LTX-Video† | Action | RGB; Pano | 2B | 57.53 | 5.49 | 38.89 | 47.4 | 27.47 |
|  | WAN2.1† | Action | RGB; Pano | 14B | **62.61** | <u>4.73</u> | <u>45.14</u> | 45.8 | <u>32.10</u> |
|  | Cosmos-P2† | Action | RGB; Pano | 2B | 60.25 | 5.08 | 41.67 | <u>45.5</u> | 30.29 |
|  | Wan2.2† | Action | RGB; Pano | 5B | 56.26 | 5.15 | 38.89 | 46.7 | 28.24 |
|  | Wan2.2† | Action | RGB; Pano | A14B | <u>62.43</u> | **4.67** | **46.53** | **44.6** | **34.61** |

---

**Table 2: Active Embodied Question Answering (A-EQA) performance.**

![Table 2 source image](p1_table2.png)

| Model Type | Method | Ans. Score↑ | Mean Traj.↓ | SPL↑ |
|---|---|---|---|---|
| Base Policy | VLM (w/o WM) | 45.7 | 20.4 | 29.6 |
| + Image Gen. | PathDreamer | 46.0 | 20.4 | 29.3 |
| + Image Gen. | SE3DS | 45.8 | 20.3 | 29.4 |
| + Video Gen. | NWM | 47.1 | 20.5 | 30.1 |
| + Video Gen. | Wan2.1 | 45.7 | **20.1** | 28.8 |
|  | Wan2.2 (5B) | 46.3 | <u>20.3</u> | <u>31.4</u> |
|  | LTX-Video | 46.6 | 20.8 | 29.5 |
|  | Cosmos-P2 | 46.6 | 21.0 | 31.3 |
|  | Hunyuan | 46.8 | 20.4 | 29.9 |
|  | SVD | <u>46.9</u> | 20.4 | 29.7 |
|  | Wan2.2 (A14B) | **47.2** | 20.7 | **31.9** |
| + Video Gen. Post-Train | SVD† | 46.4 | 21.1 | 30.1 |
|  | Cosmos-P2† | 46.5 | <u>20.6</u> | 30.1 |
|  | Wan2.2† (5B) | 47.5 | 20.8 | 30.7 |
|  | Wan2.1† | 48.2 | 20.7 | 31.6 |
|  | LTX-Video† | **48.6** | 20.7 | <u>31.8</u> |
|  | Wan2.2† (A14B) | <u>48.4</u> | **20.2** | **31.9** |

---

**Table 3: Robotic manipulation performance across various models and base policies.**

![Table 3 source image](p1_table3.png)

| Model Type | Method | SR↑ | Mean Traj.↓ |
|---|---|---|---|
| Base Policy | VLM (w/o WM) | 44.5 | 2.52 |
| + Video Gen. | SVD | 44.0 | 2.47 |
|  | LTX-Video | 44.5 | 2.46 |
|  | Hunyuan | 44.5 | 2.44 |
|  | Wan2.1 | 44.0 | 2.51 |
|  | Cosmos-P2 | 44.0 | 2.50 |
| + Video Gen. Post-Train | SVD† | 46.5 | 2.38 |
|  | Cosmos-P2† | 45.0 | 2.40 |
| Base Policy | 3D-DP (w/o WM) | 24.0 | 5.21 |
| + Video Gen. Post-Train | SVD† | 44.7 | 4.41 |
|  | Cosmos-P2† | 38.0 | 4.79 |

---

**Table 4: Post-training with different input contexts: front view vs. panorama.**

![Table 4 source image](p1_table4.png)

| Task | Model | Front View SR↑ | Front View Mean Traj.↓ | Panorama SR↑ | Panorama Mean Traj.↓ |
|---|---|---|---|---|---|
| AR | SVD† | 57.89 | 5.04 | 60.98 | 5.02 |
|  | Wan2.1† | 62.25 | 4.82 | 62.61 | 4.73 |
|  | Wan2.2† (5B) | 57.16 | 5.08 | 56.26 | 5.15 |
|  | Cosmos-P2† | 58.98 | 4.94 | 60.25 | 5.08 |
| ImageNav | SVD† | 38.19 | 47.0 | 43.05 | 46.0 |
|  | Wan2.1† | 48.61 | 43.8 | 45.14 | 45.8 |
|  | Wan2.2† (5B) | 40.97 | 45.8 | 38.89 | 46.7 |
|  | Cosmos-P2† | 40.97 | 47.0 | 41.67 | 45.5 |
