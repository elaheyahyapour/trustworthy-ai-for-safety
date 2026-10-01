# Trustworthy AI for Safety

This repository presents selected visualizations and demonstrations from my Ph.D. research on **trustworthy AI for transportation safety**.

The work studies how AI systems can support transportation decision-making while keeping safety-relevant evidence interpretable and auditable.

The dissertation connects four research directions:

- **Reliable perception** — improving recognition of underrepresented but safety-relevant roadway features.
- **Physics-grounded decision-making** — using interpretable physical evidence to support safer action selection.
- **Contract-bounded driver coaching** — combining scene interpretation with explicit physical safety rules.
- **Driver-aware coaching** — studying how driver engagement can modify coaching conservatism without weakening physical safety constraints.

---

## Interactive Dissertation Constellation

The interactive knowledge constellation shows how the four studies connect across:

**Perception → Decision-Making → Explanation → Driver-Aware Coaching**

Open the interactive visualization:

[Launch the Trustworthy AI Research Constellation](./index.html)

The visualization can be rotated, zoomed, searched, and explored by chapter.

---

# Cue2Act

Cue2Act is a driver-coaching framework that combines two complementary sources of information:

1. **Scene interpretation** — identifies relevant roadway hazards and provides an explanation.
2. **Physical safety reasoning** — evaluates measurable conditions such as time-to-collision, gap, speed, right-of-way, and crosswalk context.

These sources are combined by the **Cue2Act Governor**, where explicit physical safety rules define the safety boundary for the final recommendation.

The output is one of three coaching actions:

**PROCEED · SLOW · STOP**

The human driver remains in control.

## Cue2Act Architecture

![Cue2Act architecture](assets/figures/cue2act.png)

The architecture separates flexible scene interpretation from the physical safety contract.

The physical contract acts as a binding safety floor, while the advisory branch provides scene interpretation, hazard information, and driver-facing explanation.

---

## Cue2Act Demonstration

The following demonstration compares system recommendations under driving scenes and illustrates the relationship between advisory reasoning, physical safety constraints, and the final governed action.

https://github.com/user-attachments/assets/REPLACE_WITH_GITHUB_VIDEO_URL

**Video:** `assets/videos/cue2act_comparison.mp4`

---

# Cue2Act with Driver Engagement

The driver-engagement extension studies whether the level of coaching should change when the same roadway situation is considered under different **counterfactual driver-engagement conditions**.

The evaluated engagement states are:

- **HIGH**
- **NORMAL**
- **LOW**

Driver engagement does **not** replace or weaken the physical safety contract.

Instead, lower engagement can make coaching more conservative when additional caution is appropriate.

The physical safety boundary remains unchanged.

## Architecture with Driver Engagement

![Cue2Act with Driver Engagement](assets/figures/cue2act_driver_engagement.png)

The additional branch represents:

- driver engagement
- scene ambiguity
- operational uncertainty

These contextual factors can influence coaching conservatism while the **Physical Safety Contract** continues to constrain the final action.

---

## Driver-Engagement Comparison

This demonstration shows the same driving context under different counterfactual engagement states.

https://github.com/user-attachments/assets/REPLACE_WITH_GITHUB_VIDEO_URL

**Video:** `assets/videos/cue2act_driver_engagement_comparison.mp4`

The purpose of this experiment is to examine **policy sensitivity**, not to claim real-time measurement of driver gaze or attention.

---

# Human Audit of Cue2Act Recommendations

The human audit evaluates whether Cue2Act recommendations are not only consistent with the system's reasoning, but also useful and understandable to a driver.

![Cue2Act human audit criteria](assets/figures/cue2act_human_audit.svg)

Five concepts are evaluated:

### Visible Hazard

**What in the roadway scene should the driver pay attention to?**

Examples include a lead vehicle, pedestrian, crosswalk, traffic signal, occlusion, or another relevant roadway condition.

### Physical Trigger

**What measurable safety condition caused or constrained the intervention?**

Examples include:

- time-to-collision
- available gap
- stopping feasibility
- headway
- right-of-way
- pedestrian or crosswalk conditions

### Faithfulness

**Does the explanation accurately reflect the scene evidence, physical safety reasoning, and final governed action?**

A faithful explanation should not invent hazards or provide a rationale that contradicts the final recommendation.

### Helpfulness

**Does the explanation actually help the driver understand what to do and why?**

A technically correct explanation may still be unhelpful if it does not provide useful, actionable guidance.

### Novice Suitability

**Can an inexperienced driver understand and use the guidance quickly?**

The recommendation should translate technical safety reasoning into clear, concise, and actionable language.

---

# Research Progression

The dissertation is organized around a progression of transportation-safety questions:

```text
Reliable Roadway Perception
            ↓
Interpretable Physical Evidence
            ↓
Safety-Aligned Decision-Making
            ↓
Contract-Bounded Driver Coaching
            ↓
Driver-Aware Coaching
```

The studies are conceptually connected, but they should not be interpreted as one single end-to-end deployed vehicle-control system.

---

# Selected Research Outputs

### Study I — Reliable Perception

**Fairness-Aware Boosting Model for Imbalanced 3D Point Cloud Segmentation in Autonomous Driving**

Elahe Yahyapour, Chengbo Ai  
**CVPR Workshops, 2025**

---

### Study II — Physics-Grounded Decision-Making

**Less Is More: Agentic Prompt Design for Safe VLM Action Selection**

Elahe Yahyapour, Chengbo Ai  
**WACV Workshops, 2026**

---

### Study III — Cue2Act

**Cue2Act: Contract-Bounded Vision-Language Coaching for Novice Drivers Under Scene Ambiguity and Model Uncertainty**

Elahe Yahyapour, M. Porumerab, Chengbo Ai  
**WiML @ NeurIPS 2026 — Abstract Accepted**

This accepted version does not include the driver-engagement extension.

---

### Study IV — Cue2Act with Driver Engagement

**Cue2Act with Driver Engagement: Contract-Bounded Vision-Language Coaching Under Driver Inattention, Scene Ambiguity, and Model Uncertainty**

Elahe Yahyapour, M. Porumerab, Anuj Pradhan, Chengbo Ai  
**PhysWorldAI @ NeurIPS 2026 — Under Review**

---

# Notes

- Cue2Act is a **driver-coaching framework**, not an autonomous vehicle controller.
- The human driver retains control of the vehicle.
- Physical safety rules remain authoritative over advisory language-model reasoning.
- Driver engagement in the reported sensitivity experiments is **counterfactual** rather than directly measured from gaze or eye-tracking data.
- Application examples are intended to demonstrate the research framework and should not be interpreted as production deployment.

---

## Author

**Elahe (Ellie) Yahyapour**  
Ph.D., Transportation Engineering  
University of Massachusetts Amherst