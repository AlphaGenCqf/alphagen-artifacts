# PDRC — Algorithmic Pseudocode

Parameter-Dominance Regime Classifier (PDRC)  
AlphaGen Institute for Cognitive & Quantitative Finance Research

---

## 1. Purpose

This document describes the **algorithmic flow** of the Parameter-Dominance Regime
Classifier (PDRC) using language-neutral pseudocode.

It specifies **how regimes are constructed**, not how parameters are estimated.

No stochastic elements are used.

---

## 2. Inputs

Required inputs:

- Market data stream X
- Fixed estimation window size W
- Set of structural parameter definitions Θ
- Parameter normalization rules
- Tie-breaking rules (if applicable)

All inputs must be defined **prior to execution**.

---

## 3. Outputs

For each time index t, PDRC outputs:

- Regime identifier R_t
- Regime persistence score S(R_t)
- Regime transition flag (boolean)

---
1. Extract estimation window W_t from market data X

2. Estimate structural parameters Θ_t from W_t

3. Normalize parameters Θ_t using predefined rules

4. Rank parameters by dominance to obtain ordered list O_t

5. Assign regime R_t = hash(O_t)

6. Append R_t to regime history R

7. Compute persistence S(R_t) over recent history

8. Detect transition:
    IF R_t ≠ R_(t-1):
        flag transition at time t
    ELSE:
        no transition

---

## 5. Structural Parameter Estimation (Abstract)

Parameter estimation is treated as a **black-box procedure**:


Constraints:
- Deterministic
- Observable-only
- No adaptive fitting

---

## 6. Dominance Ordering

Dominance ordering is performed via total ordering:


Ordering rules must satisfy:
- Consistency across time
- Transitivity
- Determinism

---

## 7. Regime Assignment

A regime is assigned as a function of the ordered parameter list:


The identifier may be:
- a symbolic label
- a tuple representation
- a hashed ordering

The mapping must be one-to-one.

---

## 8. Regime Persistence Calculation

Persistence is computed over a fixed horizon H:


Persistence is independent of returns or price direction.

---

## 9. Regime Transition Detection

Transitions occur **only** due to dominance reordering.

---

## 10. Determinism Guarantee

Given:
- identical data
- identical windows
- identical parameter definitions

The algorithm will always produce:
- identical regimes
- identical transitions
- identical persistence values

No randomness is permitted at any stage.

---

## 11. Error Handling (Implementation-Level)

Implementations SHOULD:
- reject missing data silently or explicitly
- log unresolved dominance ties
- enforce parameter validity checks

Such handling must not alter regime definitions.

---

## 12. Scope

This pseudocode defines:
- regime construction
- transition logic
- persistence measurement

It does NOT define:
- parameter estimation formulas
- execution systems
- trading logic
- optimization procedures

---

## 13. Status

Pseudocode status: **stable**  
Intended use: academic reference, reviewer inspection, reproducible implementation

---

© AlphaGen Institute for Cognitive & Quantitative Finance Research  
Independent Research Institute





