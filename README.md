# ECCV-WiCV
Human-Guided Mixture-of-Experts (HG-MoE) for robust pedestrian detection under varying illumination conditions

Official implementation of **Human-Guided Mixture-of-Experts (HG-MoE)** for robust pedestrian detection under varying illumination conditions.

The framework combines human-validated hard-example adaptation with illumination-specific expert specialization. It includes three specialist experts for **Day**, **Night**, and **Dawn/Dusk** conditions, together with a **General Expert** trained on hard examples from all conditions.

## Overview

The proposed pipeline consists of:

1. Evaluating a pretrained pedestrian detector.
2. Identifying difficult pedestrian images.
3. Validating hard examples through human inspection.
4. Fine-tuning illumination-specific and general experts.
5. Routing each input to the most relevant specialist using a scene-aware gating network.
6. Combining the selected specialist with the General Expert.

During inference:


Input Image
    │
    ▼
Scene-Aware Gating Network
    │
    ▼
Selected Specialist Expert
    +
Always-Active General Expert
    │
    ▼
Prediction Fusion
    │
    ▼
Final Pedestrian Detections
