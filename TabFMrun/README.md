# TabFM exploratory benchmark

This folder contains an isolated exploratory TabFM run for the ACLED protest diffusion project.

The guiding interpretation is:

> We include TabFM as an additional predictive benchmark to test whether a tabular foundation model can improve out-of-time protest-risk ranking. The substantive hypothesis tests remain based on interpretable logit specifications and the established feature comparisons.

## What this is

TabFM is used here as a predictive benchmark for the existing 100 x 100 km cell-month panel. It is not the main research model, and it does not replace the logistic regression specifications used for the substantive hypothesis tests.

The notebook asks a narrower question:

- Given the same out-of-time design, can TabFM rank future protest-risk cell-months better than the existing logit and random forest benchmarks?

## What this is not

- It is not a new main pipeline.
- It is not a causal model.
- It is not the basis for the H1, H2, or H3 hypothesis tests.
- It should not write outputs into the main `outputs/tables`, `outputs/figures`, or `outputs/panels` folders.

## Files

```text
TabFMrun/
  README.md
  tabfm_exploratory_benchmark.ipynb
  outputs/
    .gitkeep
```

Runtime outputs from the notebook are written to `TabFMrun/outputs/`.

## Google Colab

Open the notebook in Colab:

https://colab.research.google.com/github/Mat99999/acled-spatiotemporal-conflict-model/blob/main/TabFMrun/tabfm_exploratory_benchmark.ipynb

The notebook is designed for Colab. It installs TabFM inside the Colab runtime and clones this repository if the project files are not already present.

## Practical note

The full 100 km panel is large. The notebook therefore uses a configurable sampled training context for TabFM while evaluating on the out-of-time test period. Increase the context size only if the Colab runtime has enough memory.
