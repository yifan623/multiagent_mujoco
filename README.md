# Multi-Agent Mujoco
Benchmark for Continuous Multi-Agent Robotic Control, based on OpenAI's Mujoco Gym environments.

# Installation

**Note: You require OpenAI Gym Version 10.8.0**
Simply clone this repository and put ./src on your PYTHONPATH.

# Documentation

## Environment config

* env_args.scenario: Determines the underlying single-agent OpenAI Gym Mujoco environment
* env_args.agent_conf: Determines the partitioning (see in Environment section below), fixed by n_agents x motors_per_agent
* env_args.agent_obsk: Determines up to which connection distance k agents will be able to form observations (0: agents can only observe the state of their own joints and bodies, 1: agents can observe their immediate neighbour's joints and bodies).
* env_args.k_categories: A string describing which properties are observable at which connection distance as comma-separated lists separated by vertical bars. For example, "qpos,qvel,cfrc_ext,cvel,cinert,qfrc_actuator|qpos" means k=0 can observe properties qpos,qvel,cfrc_ext,cvel,cinert,qfrc_actuator and k=1 (i.e. immediate neighbours) can be observed through property qpos.

# Environments

## Ant-v2

### Ant-v2 2x4
<img src="./docs/images/ant_2x4.png" width="200" height="200">

```python
env_args.scenario="Ant-v2"
env_args.agent_conf="4x2"
env_args.agent_obsk=1
```

### Ant-v2 2x4 diag
<img src="./docs/images/ant_2x4_diag.png" width="200" height="200">

```python
env_args.scenario="Ant-v2"
env_args.agent_conf="4x2d"
env_args.agent_obsk=1
```

### Ant-v2 4x2
<img src="./docs/images/ant_4x2.png" width="200" height="200">

```python
env_args.scenario="Ant-v2"
env_args.agent_conf="2x4"
env_args.agent_obsk=1
```
