# Differentiable and Learnable MPC : A Survey

This repository accompanies the survey **Differentiable and Learnable
Model Predictive Control: A Survey** and provides a living catalog of
research at the intersection of Model Predictive Control (MPC),
differentiable optimization, machine learning, and reinforcement learning.


## 🔥 Updates

- **Oct. 2026** — Repository initialized.
- Initial bibliography contains approximately 180 papers on differentiable,
  learnable, and reinforcement-learning-enhanced MPC.
- Introduced a three-group taxonomy based on how learning interacts with
  predictive control.
- Application domains are treated as cross-cutting metadata rather than
  mutually exclusive methodological categories.

## 📃 Introduction

Model Predictive Control provides a principled framework for optimal
decision-making under dynamics and constraints, but its practical
performance depends strongly on the predictive model, objective function,
constraints, solver, and controller parameters. Traditionally, these
components are designed and tuned manually.

Recent advances in differentiable optimization and machine learning make
it possible to learn parts of the MPC formulation directly from data and
closed-loop experience. This has led to several complementary research
directions, including differentiable MPC, differentiable predictive
control, learning-based MPC approximation, reinforcement-learning-based
MPC tuning, and hybrid MPC-RL architectures.

This repository organizes this rapidly growing literature according to
**how learning interacts with the MPC structure**, rather than only by
application domain.


## 🎯 Scope

This survey considers methods in which learning interacts directly with
Model Predictive Control, predictive optimal control, or the optimization
machinery used to construct an MPC policy.

Included topics comprise:

- differentiable MPC and differentiable optimal control;
- implicit differentiation and KKT-based MPC sensitivities;
- differentiable predictive control;
- learning MPC costs, weights, models, constraints, and terminal ingredients;
- reinforcement learning with parameterized MPC policies;
- MPC-guided and MPC-augmented reinforcement learning;
- learning-based approximation and acceleration of MPC;
- safe, robust, and certified learning-based MPC;
- differentiable and learning-based optimization methods directly relevant
  to predictive control.

Application papers are included when learning is a substantive component
of the MPC methodology rather than merely an unrelated module surrounding
a conventional MPC controller.

## 🧭 Taxonomy

We classify the literature according to the primary mechanism through which
learning interacts with predictive control.

### 1. MPC-Structured Differentiable and Learning-Based Policies

Learning is embedded in the MPC or optimization structure itself. Gradients
may propagate through the optimization problem, or a learned component may
replace, approximate, or augment part of the predictive-control formulation.

### 2. RL- and Task-Informed MPC: Hybrid Learning and Control

MPC remains a recognizable optimization-based controller, while an outer
learning mechanism tunes, guides, augments, or evaluates the MPC policy
using closed-loop or task-level performance.

### 3. Foundations, Tools, Surveys and Perspectives

This group contains the mathematical foundations, learning algorithms,
differentiable optimization techniques, software frameworks, and survey
literature required to understand and implement the methods above.


## 🔀 Classification Flow




## 📈 Publication Timeline
## 📊 Literature Distribution
## 🏷️ Application Domains
## 🔍 Literature Search Strategy
## 📚 Table of Contents

### I. MPC-Structured Differentiable and Learning-Based Policies
### II. RL- and Task-Informed MPC
### III. Foundations, Tools, Surveys and Perspectives

## 🛠️ Software and Implementations
## 🤝 Contributing
## 📜 License
## 📖 Citation
