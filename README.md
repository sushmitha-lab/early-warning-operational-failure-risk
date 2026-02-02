# early-warning-operational-failure-risk
Interpretable ML system for predicting equipment failure risk and maintenance decisions
# Early-Warning Operational Failure Risk System

## Overview
Unplanned equipment failures lead to significant operational downtime and cost.  
This project builds an interpretable machine learning system that predicts **equipment failure risk** and translates predictions into **actionable maintenance decisions**.

Instead of relying on binary predictions, the solution outputs a **continuous risk score** and maps it to operational actions such as monitoring, inspection, or shutdown.

---

## Business Problem
Maintenance teams need early warning signals to prioritize inspections and prevent costly failures while minimizing unnecessary interventions.

Key challenges:
- Failures are rare (class imbalance)
- Missing failures is costly
- Models must be interpretable for operational trust

---

## Dataset
**AI4I 2020 Predictive Maintenance Dataset**

- ~10,000 machine records
- Sensor readings and operational metrics
- Binary failure label and machine type

Each row represents a machine operating instance with associated sensor measurements.

---

## Approach

### 1. Data Understanding & EDA
- Analyzed failure distribution and machine-type behavior
- Identified key operational stress patterns
- Observed strong signals in tool wear, thermal stress, and mechanical load

### 2. Feature Engineering
- Thermal stress: temperature difference
- Mechanical stress: speed × torque interaction
- Wear indicators and risk flags
- Machine type encoding

### 3. Modeling
- Logistic Regression with class-weight balancing
- Stratified train-test split
- Recall-focused evaluation

### 4. Risk Scoring & Decision Framework
- Generated failure risk scores (0–1)
- Defined action thresholds:
  - **Monitor** (low risk)
  - **Schedule Inspection** (medium risk)
  - **Shutdown / Immediate Inspection** (high risk)

---

## Results

- ~87% recall on failure cases
- High-risk bucket enriched with ~24% actual failures
- Less than 0.5% failures in low-risk (monitor) category

The system effectively prioritizes machines requiring attention while minimizing missed failures.

---

## Key Insights
- High tool wear and mechanical load are the strongest failure drivers
- Thermal stress significantly increases failure probability
- Risk-based decision systems outperform binary classification for maintenance planning

---

## Tools & Technologies
- Python (pandas, numpy)
- scikit-learn
- matplotlib
- Google Colab

---

## Conclusion
This project demonstrates an end-to-end applied data science workflow, combining interpretable machine learning with decision-focused risk scoring to support proactive maintenance strategies.

