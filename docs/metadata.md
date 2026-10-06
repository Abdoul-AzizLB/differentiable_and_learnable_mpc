# Metadata Vocabulary

This document defines the controlled metadata vocabulary used in the
**Differentiable and Learnable MPC: A Survey** repository.

The purpose of this metadata is to provide a consistent and reproducible
description of the literature beyond conventional bibliographic information.

Each paper is assigned a single **primary methodological classification**,
while additional methodological characteristics and application-specific
information are represented through secondary labels and cross-cutting metadata.

The metadata are designed to answer five complementary questions:

1. **Where does learning enter the MPC framework?**
2. **What component of the MPC framework is learned?**
3. **How is it learned?**
4. **How is the resulting controller trained and deployed?**
5. **Where is it applied and what guarantees are provided?**

---

## 1. Metadata Structure

Each paper is described using the following fields:

```yaml
classification:
  primary_group:
  primary_family:
  secondary_methods: []

learning:
  learned_component: []
  learning_paradigm: []
  learning_algorithm: []
  learning_stage:

deployment:
  online_optimization:

application:
  application_domain: []
  system_platform: []

guarantees:
  safety_property: []

resources:
  paper_url:
  code_url:
  project_url:
```

Fields represented by `[]` may contain multiple labels.

---

# 2. Primary Classification

The primary classification determines where a paper appears in the main
literature catalog.

Each paper must have exactly:

- one `primary_group`;
- one `primary_family`.

The primary classification should reflect the **main methodological
contribution of the paper**, rather than its application domain.

## 2.1 `primary_group`

Allowed values:

| Label | Description |
|---|---|
| `mpc-structured` | Learning is embedded in, differentiated through, or directly structured around the MPC/optimal-control formulation. |
| `rl-task-informed` | An external learning or task-level mechanism tunes, guides, augments, or evaluates an MPC controller. |
| `foundations` | Foundational algorithms, optimization methods, software tools, surveys, tutorials, or perspectives supporting differentiable and learnable MPC. |

---

## 2.2 `primary_family`

The allowed family depends on the selected `primary_group`.

### `mpc-structured`

Allowed values:

- `differentiable-mpc`
- `differentiable-predictive-control`
- `learned-predictive-models`
- `approximation-acceleration`
- `safe-certified-mpc`

### `rl-task-informed`

Allowed values:

- `parameter-cost-tuning`
- `rl-guided-mpc`
- `policy-value-learning`
- `decision-focused-learning`

### `foundations`

Allowed values:

- `rl-optimal-control-foundations`
- `differentiable-optimization`
- `software-tools`
- `surveys-perspectives`

The `primary_group` and `primary_family` must always be consistent.

For example:

```yaml
primary_group: mpc-structured
primary_family: differentiable-mpc
```

is valid, whereas

```yaml
primary_group: foundations
primary_family: differentiable-mpc
```

is not.

---

# 3. Secondary Methodological Labels

## `secondary_methods`

This field records important methodological characteristics that are not
used as the paper's primary classification.

A paper may contain zero, one, or several secondary methodological labels.

Examples include:

- `differentiable-mpc`
- `differentiable-optimization`
- `reinforcement-learning`
- `policy-learning`
- `value-learning`
- `actor-critic`
- `imitation-learning`
- `weights-varying-mpc`
- `economic-mpc`
- `robust-mpc`
- `stochastic-mpc`
- `koopman-mpc`
- `residual-learning`
- `predictive-safety-filter`
- `control-barrier-function`
- `lyapunov-based-control`

Example:

```yaml
secondary_methods:
  - weights-varying-mpc
  - policy-learning
```

Secondary labels do **not** determine where the paper appears in the main
literature catalog.

---

# 4. What Is Learned?

## `learned_component`

This field identifies which component or components of the predictive-control
framework are learned from data, demonstrations, simulation, or closed-loop
interaction.

Allowed values:

- `cost-weights`
- `cost-function`
- `dynamics-model`
- `residual-dynamics`
- `constraints`
- `terminal-cost`
- `value-function`
- `reference`
- `trajectory`
- `control-policy`
- `solver`
- `solver-initialization`
- `optimization-update`
- `uncertainty-model`
- `safety-function`
- `other`
- `none`

Multiple labels should be used when several components are learned.

For example:

```yaml
learned_component:
  - cost-weights
  - residual-dynamics
```

Do not use a generic `multiple` label when the individual learned components
can be identified explicitly.

For foundational or survey papers where no particular MPC component is
learned, use:

```yaml
learned_component:
  - none
```

---

# 5. How Is It Learned?

Learning is described at two complementary levels:

- `learning_paradigm`: the broad learning principle;
- `learning_algorithm`: the specific algorithm or differentiation mechanism.

## 5.1 `learning_paradigm`

Allowed values:

- `gradient-based-learning`
- `reinforcement-learning`
- `imitation-learning`
- `supervised-learning`
- `self-supervised-learning`
- `unsupervised-learning`
- `system-identification`
- `decision-focused-learning`
- `derivative-free-learning`
- `other`
- `none`

Multiple paradigms may be assigned when appropriate.

Example:

```yaml
learning_paradigm:
  - reinforcement-learning
  - imitation-learning
```

---

## 5.2 `learning_algorithm`

This field provides a more specific description of the learning or
differentiation mechanism.

Suggested controlled values include:

### Differentiation and gradient-based methods

- `implicit-differentiation`
- `kkt-differentiation`
- `automatic-differentiation`
- `backpropagation-through-solver`
- `backpropagation-through-dynamics`
- `gradient-descent`
- `gauss-newton`
- `quasi-newton`

### Reinforcement learning

- `policy-gradient`
- `deterministic-policy-gradient`
- `actor-critic`
- `PPO`
- `SAC`
- `DDPG`
- `TD3`
- `Q-learning`
- `value-iteration`

### Other learning approaches

- `behavioral-cloning`
- `inverse-learning`
- `bayesian-optimization`
- `zeroth-order-optimization`
- `system-identification`
- `other`
- `none`

Multiple values may be used.

For example:

```yaml
learning_paradigm:
  - reinforcement-learning

learning_algorithm:
  - actor-critic
  - policy-gradient
```

or:

```yaml
learning_paradigm:
  - gradient-based-learning

learning_algorithm:
  - implicit-differentiation
  - kkt-differentiation
```

---

# 6. Learning Stage

## `learning_stage`

This field specifies when learning or adaptation occurs relative to controller
deployment.

Allowed values:

- `offline`
- `online`
- `offline-online`
- `not-applicable`

### Definitions

**`offline`**  
Learning is completed before deployment.

**`online`**  
Controller parameters or learned components continue to be updated during
deployment or closed-loop operation.

**`offline-online`**  
The method uses offline pretraining followed by online adaptation or
fine-tuning.

**`not-applicable`**  
Used for foundational, software, survey, or other papers for which this
classification is not meaningful.

---

# 7. Online Optimization Requirement

## `online_optimization`

This field describes whether deployment still requires solving an optimization
problem online.

Allowed values:

- `required`
- `reduced`
- `not-required`
- `not-applicable`

### `required`

An MPC or optimal-control problem is still solved online during deployment.

Typical example:

```text
Differentiable MPC
```

### `reduced`

Learning reduces the computational burden but some online optimization remains.

Examples include:

- learned warm starts;
- learned active sets;
- shortened horizons;
- learned solver iterations;
- compressed MPC formulations.

### `not-required`

The learned controller is deployed explicitly without solving the original MPC
optimization problem online.

Typical example:

```text
Differentiable Predictive Control (DPC)
```

### `not-applicable`

Used for foundational algorithms, surveys, or tools where this distinction does
not apply.

---

# 8. Application Domain

## `application_domain`

This field describes the broad application area of the paper.

Allowed values:

- `canonical-control`
- `robotics`
- `autonomous-driving`
- `aerial-robotics`
- `legged-robotics`
- `mobile-robotics`
- `buildings-hvac`
- `process-control`
- `power-electronics`
- `power-energy-systems`
- `traffic-transportation`
- `aerospace`
- `industrial-systems`
- `other`
- `general`

Multiple labels may be assigned when a paper evaluates the method in several
domains.

The application domain does **not** determine the primary methodological
classification.

---

# 9. System or Platform

## `system_platform`

This field identifies the physical system, dynamical benchmark, or experimental
platform used for evaluation.

Suggested values include:

- `pendulum`
- `cartpole`
- `double-integrator`
- `quadrotor`
- `fixed-wing-uav`
- `autonomous-vehicle`
- `mobile-robot`
- `legged-robot`
- `robotic-manipulator`
- `building-hvac`
- `cstr`
- `chemical-process`
- `power-converter`
- `power-grid`
- `traffic-network`
- `spacecraft`
- `simulation-benchmark`
- `multiple`
- `other`
- `not-applicable`

This vocabulary may be extended when genuinely new classes of systems appear
in the literature.

Avoid creating excessively specific labels when an existing broader label is
sufficient.

For example, use:

```yaml
application_domain:
  - aerial-robotics

system_platform:
  - quadrotor
```

rather than introducing a new application label such as
`quadrotor-racing-control`.

---

# 10. Safety and Theoretical Guarantees

## `safety_property`

This field records explicit safety, stability, robustness, feasibility, or
uncertainty guarantees provided or enforced by the method.

Allowed values:

- `constraint-satisfaction`
- `stability`
- `lyapunov-stability`
- `control-barrier-function`
- `robust-constraints`
- `chance-constraints`
- `uncertainty-quantification`
- `predictive-safety-filter`
- `recursive-feasibility`
- `probabilistic-guarantees`
- `formal-guarantees`
- `other`
- `none`

Multiple values may be used.

Example:

```yaml
safety_property:
  - lyapunov-stability
  - constraint-satisfaction
```

A paper should only receive a safety label when the corresponding property is
explicitly addressed by the method or analysis. Safety should not be inferred
merely because MPC contains constraints.

---

# 11. Resources

The following fields provide direct links to relevant resources.

## `paper_url`

URL of the publication, DOI landing page, or arXiv page.

## `code_url`

URL of an official or author-provided implementation.

Leave empty when no implementation is known.

## `project_url`

URL of the official project page, if available.

Example:

```yaml
resources:
  paper_url: https://...
  code_url: https://github.com/...
  project_url: https://...
```

---

# 12. Complete Example

A paper on differentiable weights-varying MPC could be represented as:

```yaml
classification:
  primary_group: mpc-structured
  primary_family: differentiable-mpc
  secondary_methods:
    - weights-varying-mpc
    - policy-learning

learning:
  learned_component:
    - cost-weights

  learning_paradigm:
    - gradient-based-learning

  learning_algorithm:
    - implicit-differentiation
    - backpropagation-through-solver

  learning_stage: offline

deployment:
  online_optimization: required

application:
  application_domain:
    - autonomous-driving

  system_platform:
    - autonomous-vehicle

guarantees:
  safety_property:
    - constraint-satisfaction

resources:
  paper_url: https://...
  code_url:
  project_url:
```

---

# 13. Classification Principles

To ensure consistency across the database, the following rules should be
applied.

### Rule 1 — One primary classification

Each paper receives exactly one `primary_group` and one `primary_family`.

### Rule 2 — Classify by scientific contribution

Primary classification is determined by the paper's main methodological
contribution, not simply by the algorithms or terminology appearing in the
paper.

### Rule 3 — Preserve hybrid characteristics

When a paper combines multiple paradigms, additional methods are recorded using
`secondary_methods` rather than duplicating the paper across primary
categories.

### Rule 4 — Applications are cross-cutting

Application domains and systems do not determine the primary methodological
classification.

### Rule 5 — Use controlled labels

Existing labels should be reused whenever possible. New labels should only be
introduced when the existing vocabulary cannot accurately describe a recurring
concept in the literature.

### Rule 6 — Prefer explicit information

Metadata should reflect claims, methods, experiments, and guarantees explicitly
described in the paper. Properties should not be inferred solely from the
general characteristics of MPC, reinforcement learning, or a particular
application.

---

# 14. Metadata Version

**Current metadata schema:** `v0.1`

The vocabulary will initially be tested on a representative subset of papers
covering:

- Differentiable MPC;
- Differentiable Predictive Control;
- RL-based MPC tuning;
- hybrid MPC-RL;
- learning-based MPC approximation;
- safety-certified learning-based MPC;
- foundational differentiable optimization;
- surveys and software tools.

After this validation phase, the vocabulary will be revised and frozen as
`v1.0` before full-scale classification of the literature.
