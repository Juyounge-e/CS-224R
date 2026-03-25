# CS224R Study Repo(LastUpdate:260325)

This repository is my study workspace for CS224R.
I am using it to understand imitation learning by implementing the homework code myself and keeping short notes on experiments and debugging.

## Topics

- Week 1: Behavior Cloning (BC), DAgger
- TBU

## Goal

My goal is not just to finish the homework, but to understand how BC and DAgger work in code.

## Current Status

- [x] Read through the main training flow
- [x] Implement the major TODO sections for HW1
- [x] Mark edited sections with `# CHECKLIST:`
- [x] Get BC and DAgger code paths into a runnable state
- [ ] Verify edited functions
- [ ] Run BC and DAgger experiments
- [ ] Tune hyperparameters
- [ ] Finish the remaining PDF tasks

## Setup

See [installation.md](../installation.md).

## Main Files

- `infrastructure/bc_trainer.py`
- `policies/MLP_policy.py`
- `infrastructure/replay_buffer.py`
- `infrastructure/utils.py`
- `infrastructure/pytorch_util.py`

## Run Experiments

Tip: use `--video_log_freq -1` while debugging for faster runs.

### Behavior Cloning

```bash
python cs224r/scripts/run_hw1.py \
  --expert_policy_file cs224r/policies/experts/Ant.pkl \
  --env_name Ant-v4 \
  --exp_name bc_ant \
  --n_iter 1 \
  --expert_data cs224r/expert_data/expert_data_Ant-v4.pkl \
  --video_log_freq -1
```

### DAgger

```bash
python cs224r/scripts/run_hw1.py \
  --expert_policy_file cs224r/policies/experts/Ant.pkl \
  --env_name Ant-v4 \
  --exp_name dagger_ant \
  --n_iter 10 \
  --do_dagger \
  --expert_data cs224r/expert_data/expert_data_Ant-v4.pkl \
  --video_log_freq -1
```

## TensorBoard

```bash
tensorboard --logdir data --port 6006
```

Open [http://localhost:6006](http://localhost:6006).

Main metrics:
- `Eval_AverageReturn`
- `Eval_StdReturn`
- `Train_AverageReturn`
- `Training Loss`

## Notes

### BC Baseline
- Environment:
- Hyperparameters:
- Eval average return:
- Expert ratio:
- Notes:

### DAgger Baseline
- Environment:
- Hyperparameters:
- Final eval average return:
- Comparison to BC:
- Notes:
