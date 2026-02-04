# Ticket Sales Forecasting with Multivariate Linear Regression

This project explores how **ticket sales for a theater performance** can be modeled using **multivariate linear regression**, based on two key predictors:

- **Days before the show**
- **Marketing spend**

The goal is not to build a production-grade forecasting system, but to **develop intuition** for how linear regression behaves with multiple variables, how to visualize it effectively, and where its limitations become apparent.

---

## Project Motivation

As a freelance performing artist transitioning into data analysis, this project serves as a **learning exercise** to connect statistical modeling concepts with a familiar real-world context: ticket sales.

Key questions explored:
- How do multiple predictors interact in a linear regression model?
- How can we visualize a regression model with more than one variable?
- What limitations emerge when modeling bounded outcomes (e.g. venue capacity)?

---

## Dataset Overview

The dataset is **synthetically generated** to resemble realistic ticket-sales behavior.

### Features

| Column | Description |
|------|------------|
| `days_before_show` | Number of days before the performance |
| `marketing_spend` | Marketing budget (right-skewed distribution) |
| `tickets_sold` | Number of tickets sold (bounded by venue capacity) |

The data generation includes:
- A decreasing base demand as the show date approaches
- A positive marketing effect
- Random noise
- A hard capacity limit to simulate sell-outs

This structure allows exploration of **realistic patterns** while keeping full control over assumptions.

---

## Methodology

### 1. Data Generation
- NumPy used to generate predictors with controlled distributions
- Pandas used to assemble the dataset
- Random seed set for reproducibility

### 2. Model
- **Multivariate Linear Regression** using `scikit-learn`
- Predictors:
  - `days_before_show`
  - `marketing_spend`
- Target:
  - `tickets_sold`

### 3. Visualization Strategy

Because linear regression with two predictors forms a **plane**, not a single line, multiple visualization approaches are used:

- **Scatter plots** of actual ticket sales
- **Regression slices**:
  - Tickets vs days before show at fixed marketing levels
  - Tickets vs marketing spend at fixed days-before-show values

This approach keeps the visualization interpretable in 2D while still reflecting the full multivariate model.

---

## Key Learnings

- Linear regression with multiple predictors produces a **surface**, not a single line.
- To visualize one predictor, all others must be **held constant**.
- Even when a model fits mathematically, it may be **conceptually wrong** for bounded outcomes (e.g. capacity limits).
- Visualization choices are critical for understanding multivariate models.

---

## Tools & Libraries

- Python
- NumPy
- Pandas
- Matplotlib
- scikit-learn

---

## Project Scope (Intentional Limits)

- This project **intentionally stops at linear regression**.
- Logistic regression and capacity-aware models are a natural next step, but are left out to keep the focus clear and pedagogical.
- Emphasis is placed on **understanding**, not model complexity.

---

## Next Possible Extensions

- Logistic regression to model sell-out probability
- Feature scaling and coefficient interpretation
- Comparison of linear vs logistic behavior near capacity
- Interactive visualizations

---

## Author

Matt  
Freelance performing artist exploring data analysis and applied statistics through real-world analogies.

