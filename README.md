# Active learning budget study

When does uncertainty sampling start to beat random sampling? On synthetic Gaussian-mixture data, the notebook finds the
crossover budget for least confidence, margin and entropy, and checks how it depends on the number of modes, mode
separation and class imbalance. Random, BADGE and farthest-first are the baselines.

## Contents

- `pipeline.ipynb`: the whole study in one notebook: data generator, query strategies, active-learning loop,
  experiments and analysis.
- `results/`: saved runs, one `.npz` per (setting, strategy, seed); created when the notebook runs; not in git.
- `figures/`: figures as PDF and PNG; created when the notebook runs.

## How to run

```bash
pip install -r requirements.txt
jupyter nbconvert --to notebook --execute --inplace pipeline.ipynb   # or open it and "Run All"
```

Set `MODE` in the configuration cell:

- `"quick"`: 5 seeds, budget up to 300; takes a few minutes.
- `"full"`: 25 seeds, budget up to 1000; for the report numbers.

Finished runs are saved to `results/` and reused on the next run, so an interrupted run picks up where it stopped.
