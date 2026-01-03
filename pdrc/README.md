# Parameter-Dominance Regime Classifier (PDRC)

A deterministic diagnostic framework for market regime identification

---

## 1. Purpose

The **Parameter-Dominance Regime Classifier (PDRC)** is a diagnostic framework designed to identify and track market regimes using **observable structural parameters**, without relying on latent-state inference or probabilistic regime-switching models.

PDRC addresses a core limitation of conventional regime models:  
most existing approaches infer regimes indirectly through hidden states, making interpretation, auditability, and reproducibility difficult.

PDRC instead defines regimes **explicitly**, as dominance configurations among empirically measurable market parameters.

---

## 2. Conceptual Positioning

PDRC is **diagnostic, not predictive**.

It is intended to answer:

> What regime is the market currently operating in, and how stable is that regime classification?

PDRC does **not** attempt to:
- Forecast prices
- Optimize portfolios
- Generate trading signals

Its role is **measurement and classification**, not execution.

---

## 3. Core Principle: Parameter Dominance

At each observation window, a finite set of structural parameters is estimated from market data.

Let the parameter set be:
Θ = {θ₁, θ₂, …, θₙ}

A regime is defined by the **dominance ordering** among these parameters.  
For example:

θᵢ ≻ θⱼ ≻ θₖ

Changes in regime occur when this dominance ordering changes.

This construction ensures that:
- Regimes are discrete
- Regimes are interpretable
- Transitions are structurally traceable

---

## 4. Observable Parameter Classes

While specific parameter definitions are implementation-dependent, PDRC typically operates over parameter families representing:

- Volatility or shock intensity  
- Market continuity versus fragmentation  
- Risk pressure and drawdown sensitivity  
- Participation and liquidity stress  
- Temporal compression or expansion  

All parameters must be:
- Observable
- Estimable from market data
- Stable under re-estimation

---

## 5. Regime Properties

Each PDRC regime is characterized by:

- Structural identity (dominant parameter configuration)
- Stability (persistence of dominance)
- Transition sensitivity (ease of dominance reordering)
- Compression behavior (loss of regime diversity under stress)

These properties allow regimes to be compared across markets and time.

---

## 6. Methodological Advantages

PDRC avoids common pitfalls of regime modeling:

- No hidden states
- No likelihood maximization
- No training instability
- No path-dependent inference

As a result, the framework is:
- Reproducible
- Inspectable
- Suitable for peer review and auditing

---

## 7. Relationship to Other AlphaGen Frameworks

PDRC functions as a **foundational diagnostic layer** within the AlphaGen research stack.

Downstream frameworks include:
- Belief–Reality Divergence (BRD), which measures divergence conditional on regime
- Cognitive Womb, which studies strategy emergence under regime constraints
- Adaptive systems that respond to regime diagnostics rather than raw price signals

No downstream framework is defined independently of PDRC-level regime structure.

---

## 8. Planned Artifacts

This directory will evolve conservatively to include:

- Formal mathematical specifications
- Algorithmic pseudocode
- Reference implementations
- Cross-market validation studies
- Regime transition diagnostics
- Failure mode analyses

All additions will preserve backward interpretability.

---

## 9. Scientific Scope and Limitations

PDRC is intentionally limited to:
- Regime identification
- Structural diagnostics
- Stability analysis

It makes **no claims** regarding:
- Predictive superiority
- Alpha generation
- Portfolio optimization

Its contribution is **measurement fidelity**, not performance.

---

## 10. Status

- Framework maturity: stable
- Empirical validation: completed internally
- Cross-market testing: ongoing
- Publication status: preprint / submission phase

---

© AlphaGen Institute for Cognitive & Quantitative Finance Research  
Independent Research Institute
