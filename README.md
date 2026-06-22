# RL for Multi-Task Traditional Speech Tasks

> **Status: 🟡 Skeleton.** Hydra scaffold + shared-lib wiring in place; RL loop to be filled in.
> Use W1 ([speech-mllm-training-free-rl](https://github.com/chaosxingxc-orion/speech-mllm-training-free-rl))
> as the reference pattern.
>
> Part of the **chaos speech-multimodal-LLM RL** series. Shares code via the
> `speechrl-common` package (installed from `../../common`).
> Umbrella: [exploring-l4-intelligence](https://github.com/chaosxingxc-orion/exploring-l4-intelligence).

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

## Status & roadmap

Skeleton. Next: wire per-task verifiable rewards from `speechrl_common.rl`, then multi-task sampling
and evaluation. Track progress on the umbrella Wiki's
[Per-Work-Status](https://github.com/chaosxingxc-orion/exploring-l4-intelligence/wiki/Per-Work-Status).

---

## 中文

单一策略，用可验证奖励跨 ASR/ST/说话人识别/情感等语音任务做 RL。**当前是骨架**：Hydra 脚手架与共享库
接线已就位，RL 主循环待实现，请以 W1 为参考范式。环境与命令见上（详见 `../../docs/setup.md`）。
