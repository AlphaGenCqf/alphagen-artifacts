# PDRC — Validation Protocol

Parameter-Dominance Regime Classifier (PDRC)  
AlphaGen Institute for Cognitive & Quantitative Finance Research

---

## 1. Purpose of Validation

The purpose of this document is to describe the **validation protocol** applied to
the Parameter-Dominance Regime Classifier (PDRC).

Validation is designed to assess:
- Structural consistency
- Deterministic reproducibility
- Regime stability and transition behavior

This protocol does **not** evaluate predictive performance or trading profitability.

---

## 2. Validation Principles

Validation follows three guiding principles:

1. **Determinism**  
   Identical inputs must produce identical regime classifications.

2. **Structural Robustness**  
   Regime definitions must remain stable under reasonable variations in data
   sampling and estimation windows.

3. **Interpretability**  
   Regimes and transitions must be explainable in terms of observable dominance
   changes.

---

## 3. Data Scope

Validation was conducted using publicly available market data, including:

- Equity indices
- Liquid single-name equities
- Futures and exchange-traded instruments

Data sources were selected to ensure:
- Transparency
- Replicability
- Broad market representation

No proprietary data were used.

---

## 4. Temporal Coverage

Validation spans multiple market environments, including:

- Low-volatility regimes
- High-volatility stress periods
- Transitional phases between regimes

Time horizons were chosen to test regime persistence and transition dynamics
under varying market conditions.

---

## 5. Validation Tests

### 5.1 Deterministic Reproducibility Test

The PDRC algorithm was executed multiple times on identical datasets using
identical parameter definitions.

**Expected outcome:**  
Regime sequences, transition points, and persistence measures remain identical
across runs.

---

### 5.2 Window Sensitivity Test

Estimation window lengths were varied within a predefined range.

**Expected outcome:**  
Regime classifications remain structurally consistent, with only localized
boundary effects near transition points.

---

### 5.3 Parameter Perturbation Test

Structural parameters were perturbed within conservative bounds.

**Expected outcome:**  
Dominant regime structure persists unless perturbations materially alter
dominance ordering.

---

### 5.4 Cross-Market Consistency Test

The same PDRC framework was applied across different asset classes.

**Expected outcome:**  
Regime definitions remain interpretable and consistent, without asset-specific
retraining.

---

### 5.5 Regime Compression Stress Test

Periods of elevated market stress were analyzed for regime diversity behavior.

**Expected outcome:**  
Observable compression of regime diversity under stress, followed by expansion
during normalization.

---

## 6. Evaluation Criteria

Validation success is determined by:

- Absence of stochastic variation
- Stability of regime identity
- Traceability of regime transitions
- Consistency across assets and time

No performance metrics are used as evaluation criteria.

---

## 7. Limitations

This validation protocol does not address:

- Predictive accuracy
- Trading performance
- Optimal parameter selection
- Real-time execution constraints

Such evaluations are intentionally excluded.

---

## 8. Relationship to Publications

Validation results corresponding to this protocol are reported, where relevant,
in associated manuscripts and preprints.

This document serves as a **methodological appendix**, not a results summary.

---

## 9. Status

Validation protocol status: **complete**  
Reproducibility: **confirmed internally**  
External replication: **encouraged**

---

© AlphaGen Institute for Cognitive & Quantitative Finance Research  
Independent Research Institute
