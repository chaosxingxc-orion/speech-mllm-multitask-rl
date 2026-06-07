# RL for Multi-Task Traditional Speech Tasks

> Part of the **chaos speech-multimodal-LLM RL** series. Shares code via the
> `speechrl-common` package (installed from `../../common`).

## Idea

A single policy improved with RL across ASR, ST, speaker-ID, emotion and related speech tasks via verifiable rewards.

**RL approach:** multi-task GRPO with per-task verifiable rewards.

## Setup (WSL2)

```bash
source ~/.venvs/speechrl/bin/activate          # shared env, see ../../docs/setup.md
uv pip install -e ../../common -e .
```

## Run

```bash
bash scripts/train.sh                          # train (Hydra config in configs/)
bash scripts/train.sh rl.learning_rate=2e-6    # override any config key
bash scripts/eval.sh                           # evaluate
```

## Layout

- `src/multitask_rl/main.py` — Hydra entrypoint (fill in the RL loop)
- `configs/` — Hydra configs: `model/`, `dataset/`, `rl/`, `experiment/`
- `scripts/` — `train.sh`, `eval.sh`
- depends on `speechrl_common` for audio I/O, reward functions, MLflow tracking, prompts
