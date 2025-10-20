# my-Resume

## Gradient Boosting Regressor Architecture (README.md Style)

Below is the full architecture represented in **README.md compatible code-block formatting**:

```
                               Gradient Boosting Regressor (Full Architecture)

 ┌─────────────────────────────────────────────────────────────────────────┐
 │                             INPUT LAYER                                  │
 │    • Training dataset (X, y)                                            │
 │    • Features (numeric/categorical after preprocessing)                 │
 └─────────────────────────────────────────────────────────────────────────┘
                                       │
                                       ▼
 ┌─────────────────────────────────────────────────────────────────────────┐
 │                        INITIALIZATION STEP                               │
 │    • Base learner f₀(x) = mean(y) (for regression)                      │
 │    • Creates first constant model                                       │
 └─────────────────────────────────────────────────────────────────────────┘
                                       │
                                       ▼
 ┌─────────────────────────────────────────────────────────────────────────┐
 │                 BOOSTING ITERATION (for t = 1 ... T)                     │
 └─────────────────────────────────────────────────────────────────────────┘
                                       │
                                       ▼
     ┌──────────────────────────────────────────────────────────────┐
     │ 1. LOSS FUNCTION & GRADIENT CALCULATION                      │
     │    • Compute gradient (residuals):                           │
     │         rᵢ = -∂L(yᵢ, f(xᵢ)) / ∂f(xᵢ)                          │
     │       (for MSE: residual rᵢ = yᵢ - f(xᵢ))                    │
     └──────────────────────────────────────────────────────────────┘
                                       │
                                       ▼
     ┌──────────────────────────────────────────────────────────────┐
     │ 2. TRAIN WEAK LEARNER                                         │
     │    • Fit regression tree on residuals                        │
     │    • Tree attempts to reduce current residual errors         │
     └──────────────────────────────────────────────────────────────┘
                                       │
                                       ▼
     ┌──────────────────────────────────────────────────────────────┐
     │ 3. SHRINKAGE / LEARNING RATE                                  │
     │    • Scale tree prediction:                                  │
     │         fₜ(x) = η * treeₜ(x)                                 │
     │      (η = learning rate, typically < 0.1)                    │
     └──────────────────────────────────────────────────────────────┘
                                       │
                                       ▼
     ┌──────────────────────────────────────────────────────────────┐
     │ 4. UPDATE ENSEMBLE MODEL                                     │
     │    • f(x) ← f(x) + fₜ(x)                                     │
     │    • Ensemble grows stage by stage                          │
     └──────────────────────────────────────────────────────────────┘
                                       │
                                       ▼
 ┌─────────────────────────────────────────────────────────────────────────┐
 │                              FINAL MODEL                                 │
 │     • Sum of all boosted weak learners                                  │
 │     • Strong predictive model f(x) = f₀(x) + Σ η * treeₜ(x)            │
 │     • Outputs final prediction                                          │
 └─────────────────────────────────────────────────────────────────────────┘
```
