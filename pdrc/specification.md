# PDRC — Formal Specification

Parameter-Dominance Regime Classifier (PDRC)  
AlphaGen Institute for Cognitive & Quantitative Finance Research

---

## 1. Objective

The objective of the Parameter-Dominance Regime Classifier (PDRC) is to define
market regimes as **deterministic structural states**, constructed from observable
market parameters, and to identify regime transitions via changes in parameter
dominance.

PDRC is a **diagnostic framework**, not a predictive model.

---

## 2. Observation Space

Let the market be observed at discrete times  
t ∈ {1, 2, …, T}.

Let the raw market data over an estimation window Wₜ be denoted by:

Xₜ = {Pₜ, Vₜ, Lₜ, …}

where:
- Pₜ represents price-related observations,
- Vₜ represents volume or participation measures,
- Lₜ represents liquidity or microstructure proxies.

The exact composition of Xₜ is implementation-specific but must be observable.

---

## 3. Structural Parameter Vector

From Xₜ, define a vector of structural parameters:

Θₜ = (θ₁ₜ, θ₂ₜ, …, θₙₜ)

Each parameter θᵢₜ must satisfy:

1. Observability: computable from Xₜ
2. Stability: robust under re-estimation within Wₜ
3. Interpretability: corresponds to a structural market property

Typical parameter categories include (non-exhaustive):

- Shock or volatility intensity
- Continuity vs. fragmentation
- Risk pressure or drawdown sensitivity
- Participation strength
- Temporal compression or expansion

---

## 4. Dominance Relation

Define a **dominance relation** ≻ over Θₜ such that:

θᵢₜ ≻ θⱼₜ  ⇔  θᵢₜ > θⱼₜ  under a predefined normalization

Dominance must satisfy:

- Antisymmetry
- Transitivity
- Comparability within Θₜ

Ties may be resolved via:
- secondary metrics, or
- explicit equivalence classes

---

## 5. Regime Definition

A **regime** Rₜ is defined as the ordered dominance configuration of Θₜ:

Rₜ = Ord(Θₜ)

where Ord(·) maps the parameter vector to a ranked ordering:

(θᵢₜ ≻ θⱼₜ ≻ … ≻ θₖₜ)

Thus, regimes are **discrete structural states**, not probabilistic labels.

---

## 6. Regime Persistence

Define regime persistence over a horizon H as:

S(Rₜ) = |{τ ∈ [t−H, t] : R_τ = Rₜ}| / H

This quantity measures structural stability and is independent of returns.

---

## 7. Regime Transition

A **regime transition** occurs at time t when:

Rₜ ≠ Rₜ₋₁

Transitions are therefore caused by **dominance reordering**, not noise
or latent state inference.

---

## 8. Regime Compression

Define the **regime diversity** over a horizon H as:

D(H) = |{Rₜ₋ₕ : h ∈ [0, H]}|

Regime compression is identified when D(H) collapses toward 1 under
increasing market stress, indicating loss of structural diversity.

---

## 9. Determinism and Reproducibility

Given:
- identical data Xₜ,
- identical estimation window Wₜ,
- identical parameter definitions,

PDRC produces **identical regimes and transitions**.

No stochastic components are permitted in regime assignment.

---

## 10. Scope and Constraints

PDRC explicitly excludes:

- Latent-state inference
- Probabilistic regime switching
- Model training or fitting
- Performance optimization

Its sole function is **structural regime identification**.

---

## 11. Interface with Downstream Frameworks

Let downstream frameworks depend on regime state Rₜ.

Then PDRC provides:
- Rₜ: regime identity
- S(Rₜ): regime stability
- Transition timestamps

No downstream inference may redefine regimes independently of PDRC.

---

## 12. Status

Specification status: **stable**  
Backwards compatibility: **preserved**  
Intended use: diagnostic, academic, and audit-grade analysis

---

© AlphaGen Institute for Cognitive & Quantitative Finance Research  
Independent Research Institute
