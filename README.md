# Differentiable and Learnable MPC: A Survey

> A living survey of differentiable optimization, learning-based MPC,
> and reinforcement-learning-enhanced predictive control.

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

The group comprises:

1. **Differentiable MPC and Optimization-Based Policies**
2. **Differentiable Predictive Control**
3. **Structured and Learned Predictive Models for MPC**
4. **Learning-Based Approximation and Acceleration of MPC**
5. **Safe, Robust and Certified Learning-Based MPC**

### 2. RL- and Task-Informed MPC: Hybrid Learning and Control

MPC remains a recognizable optimization-based controller, while an outer
learning mechanism tunes, guides, augments, or evaluates the MPC policy
using closed-loop or task-level performance.

The group comprises:

1. **RL for MPC Parameter and Cost Tuning**
2. **RL-Guided and RL-Augmented MPC**
3. **Value Learning, Policy Optimization and MPC-Based RL**
4. **Imitation, Decision-Focused and Task-Oriented MPC Learning**

### 3. Foundations, Tools, Surveys and Perspectives

This group contains the mathematical foundations, learning algorithms,
differentiable optimization techniques, software frameworks, and survey
literature required to understand and implement the methods above.

The group comprises:

1. **Foundations of Reinforcement Learning and Optimal Control**
2. **Differentiable Optimization and Sensitivity Analysis**
3. **Software and Computational Tools**
4. **Surveys, Tutorials and Perspectives**


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
