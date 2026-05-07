# COMET

This repository contains the implementation of **COMET** (**C**ausal **O**bject-centric **M**odel for **E**fficient **T**ree search).

We introduce COMET, a model-based reinforcement learning algorithm that performs Monte Carlo Tree Search in a slot-structured latent space. COMET pairs a frozen unsupervised object-centric encoder with a transformer-based world model, where actions are bound to objects through a novel action-slot fusion mechanism used in slot transition prediction. Policy and value heads use object-causal attention, modulating token interactions by learned per-slot relevance scores so decision-making focuses on task-relevant entities. COMET adds an explicit object-level inductive bias to MuZero-style latent planning. Across eight visually and dynamically diverse tasks from the Object-Centric Visual RL benchmark, ManiSkill, Robosuite, and VizDoom, COMET achieves a higher mean normalized score during early training compared to object-centric and monolithic baselines.

## Requirements

- `python==3.9`

## Installation

```bash
pip install -e .
```

## Run COMET

### Object-Centric Visual RL benchmark

Discrete tasks:

```bash
python3 -u zoo/ocrl/config/ocrl_objectzero_segment_config.py
```

You can choose a specific environment with `--env`:

- `TargetEnv-v0` (Object Goal Task)
- `PushEnv-v0` (Object Interaction)
- `OddOneOutEnvObject-v0` (Object Comparison Task)
- `OddOneOutEnvProperty-v0` (Property Comparison Task)

Continuous task:

```bash
python3 -u zoo/causal_world/config/causalworld_soz_segment_config.py
```

### ManiSkill

```bash
python3 -u zoo/maniskill/config/maniskill_soz_segment_config_slotcontrast.py
```

### Robosuite

```bash
python3 -u zoo/robosuite/config/robosuite_soz_segment_config.py
```

### VizDoom

```bash
python3 -u zoo/vizdoom/config/vizdoom_objectzero_segment_config.py
```