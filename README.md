# my-Resume

```text
                         Gradient Boosting Regressor – Full Architecture

1) INPUT LAYER
   • Training dataset (X, y)
   • Features after preprocessing

       │
       ▼

2) INITIALIZATION
   • Base model f₀(x) = mean(y)  (for regression)

       │
       ▼

3) BOOSTING ITERATIONS (for t = 1 ... T)
   ┌───────────────────────────────────────────────┐
   │ a) Compute Gradient / Residuals               │
   │    rᵢ = yᵢ - f(xᵢ)   (for squared loss)        │
   │                                               │
   │ b) Fit Weak Learner (Tree)                    │
   │    Train regression tree on residuals         │
   │                                               │
   │ c) Apply Learning Rate (η)                    │
   │    fₜ(x) = η * treeₜ(x)                       │
   │                                               │
   │ d) Update Ensemble                            │
   │    f(x) ← f(x) + fₜ(x)                         │
   └───────────────────────────────────────────────┘

       │
       ▼

4) FINAL MODEL
   • Strong learner = sum of all weak learners
   • f(x) = f₀(x) + Σ (η * treeₜ(x))

       │
       ▼

5) PREDICTION
   • Final prediction returned for regression output
```
