# 🧠 ED Cognitive Reasoning Agent
## Real-Time Emergency Triage with CCIM + ACCB + RL Prevention Loop

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/iyerlatha2025-LN/ed-triage-cognitive-agent/blob/main/EmergencyTriage_ACCB_CCIM.ipynb)

A production-grade cognitive reasoning agent for Emergency Department triage — combining multi-agent AI with clinical safety frameworks and reinforcement learning.

---

## Architecture

```
Patient Input
      ↓
┌─────────────────────────────────┐
│     COGNITIVE REASONING BRAIN   │
│  VitalSigns Agent               │
│  Symptom Analysis Agent         │
│  Differential Diagnosis Agent   │
│  Risk Stratification Agent      │
└─────────────────────────────────┘
      ↓
┌─────────────────────────────────┐
│  CCIM — Context Chain Integrity │
│  Monitor (In-Flight Guardrail)  │
│  Catches agent contradictions   │
│  before they reach exit gate    │
└─────────────────────────────────┘
      ↓
┌─────────────────────────────────┐
│  ACCB — Adaptive Confidence     │
│  Circuit Breaker (Exit Gate)    │
│  Conformal prediction bounds    │
│  PROCEED / REVIEW / HALT        │
└─────────────────────────────────┘
      ↓
┌─────────────────────────────────┐
│  RL PREVENTION LOOP             │
│  Logs every human override      │
│  Updates ACCB thresholds        │
│  Brain learns — override rate   │
│  drops over time                │
└─────────────────────────────────┘
      ↓
Decision + Audit Trail + Dashboard
```

---

## Safety Framework

### CCIM — Context Chain Integrity Monitor
The in-flight guardrail. Watches agents while they reason and catches logical contradictions before they propagate to the exit gate.

- Calculates consensus score across all agents
- Flags when triage level variance exceeds threshold
- Forces conflict resolution before ACCB evaluation
- Like an editor reading chapter-by-chapter

### ACCB — Adaptive Confidence Circuit Breaker
The exit gate. Conformal prediction-based safety layer that trips before a bad decision reaches the clinician.

| Decision | Condition |
|---|---|
| ✅ PROCEED | Confidence above threshold, CCIM passed |
| ⚠️ REVIEW | Confidence borderline, or minor agent conflict |
| 🛑 HALT | Confidence below threshold, CCIM failed, or RESUSCITATION level |

Adaptive thresholds by triage level — more critical conditions require higher confidence to proceed.

**Research basis:** doi.org/10.5281/zenodo.18796466 | ORCID: 0009-0000-8755-8805

### RL Prevention Loop
Every human override teaches the Brain. Confidence thresholds tighten as the system accumulates experience. Override rate drops. Prevention strengthens.

```
Agent decides → Human reviews → Override logged →
ACCB threshold updated → Brain learns →
Next decision improves → Override rate drops
```

---

## Demo Scenarios

| Patient | Condition | Expected ACCB |
|---|---|---|
| Sarah Johnson, 34F | Minor laceration | ✅ PROCEED |
| Robert Chen, 58M | Chest pain, SOB | ⚠️ REVIEW |
| Maria Rodriguez, 72F | Unresponsive, collapsed | 🛑 HALT |

---

## Stack

- **Python** — core pipeline
- **Google Gemini** — LLM reasoning engine
- **CrewAI** — multi-agent orchestration
- **Streamlit** — real-time dashboard
- **Plotly** — ACCB confidence gauge and agent consensus charts
- **Conformal Prediction** — ACCB statistical bounds
- **pyngrok** — live demo URL

---

## How to Run

1. Open `EmergencyTriage_ACCB_CCIM.ipynb` in Google Colab
2. Add secrets to Colab:
   - `GEMINI_API_KEY` — from console.cloud.google.com
   - `NGROK_AUTH_TOKEN` — from ngrok.com
3. Runtime → Run all
4. Live dashboard URL appears at the end

---

## Dashboard Features

- Real-time vital signs status table
- ACCB confidence gauge with colour coding
- Agent consensus bar chart
- Differential diagnosis panel
- Recommendations panel
- RL feedback loop — clinician override input
- Sidebar RL metrics — override rate, accuracy trend

---

## Research

- **ACCB preprint:** [doi.org/10.5281/zenodo.18796466](https://doi.org/10.5281/zenodo.18796466)
- **PLOS publication:** In progress
- **IEEE Women's Chapter NJ:** Invited Speaker, June 4, 2026
- **ORCID:** 0009-0000-8755-8805

---

**SAI Strategic Agentic Intelligence** | Brain + Safety Net + RL Loop = Enterprise AI that earns trust over time
