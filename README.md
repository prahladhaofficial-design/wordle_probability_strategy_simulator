# Wordle Probability Strategy Simulator

A probability simulation project combining inverse-transform sampling, empirical CDF convergence, letter-frequency analysis, and Wordle-style strategy reasoning.

## Overview

Word games provide a practical setting for probability reasoning. This project combines sampling theory with letter-frequency analysis to explore how probabilistic evidence can guide word choices.
The notebook also demonstrates empirical-vs-theoretical CDF convergence through plots and animation.

## Project Design

- Implement inverse-transform sampling.
- Construct empirical CDFs from simulated samples.
- Compare empirical and theoretical CDFs visually.
- Load a word list and compute letter-frequency summaries.
- Use probability summaries to reason about Wordle-style choices.

## Key Capabilities

- Inverse-transform sampling implementation.
- Empirical CDF construction.
- Static CDF plots and an MP4 animation.
- Word-list loading and letter-frequency visualization.
- Probability-driven word strategy exploration.
- Optional CVXPY-based optimization tooling.

## Repository Structure

```text
notebooks/probability_wordle_simulation.ipynb  Main notebook.
datasets/wordlist.csv                          Word list dataset.
figures/                                       Generated plots.
media/                                         CDF animation.
requirements.txt                               Python dependencies.
```

## Running Locally

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook notebooks/probability_wordle_simulation.ipynb
```

## Results and Artifacts

- `figures/Histogram of letters visualization.png`.
- `figures/Static Empirical CDF vs Theoretical CDF (N=1000).png`.
- `figures/Theoretical Cumulative Distribution Function F(x).png`.
- `media/Empirical vs True CDF animation.mp4`.

## Reproducibility Notes

- Keep the word list fixed when comparing entropy or probability-based strategies.
- Recompute candidate sets after every feedback-rule change.
- Run deterministic examples when validating solver behavior against known games.
- Treat strategy scores as search-policy diagnostics rather than guarantees for every puzzle.

## Detailed Workflow

- Run the sampling section to generate empirical CDF outputs.
- Inspect the static and animated CDF comparisons.
- Load the word list and compute letter-frequency summaries.
- Use frequency information to reason about Wordle-style word selection.
- Modify the word list or scoring logic to experiment with different strategies.

## Implementation Details

- The probability section demonstrates inverse-transform sampling.
- Empirical CDFs are compared against theoretical expectations.
- The Wordle section uses a CSV word list as the analysis source.
- Letter-frequency plots summarize useful word-distribution information.
- CVXPY is available for optimization-style extensions where supported.

## Data and Inputs

- `datasets/wordlist.csv` contains the word list used by the notebook.
- Letter-frequency results depend on the exact word list.
- The sampling simulations generate their own numerical data.
- The MP4 animation is stored under `media/` for direct review.

## How To Interpret the Results

- Empirical CDF convergence improves as the number of samples increases.
- Letter-frequency histograms help identify common letters but do not fully solve the game.
- Good Wordle choices also depend on position information and feedback constraints.
- Probability summaries should be combined with game-state filtering for stronger strategy.

## Limitations and Assumptions

- The project is a probability exploration, not a complete Wordle solver.
- Word-list quality strongly affects strategy conclusions.
- Notebook execution order matters for generated simulations.
- A future CLI could make the strategy component easier to use interactively.


## Review Guide

Use this checklist when reviewing the repository on GitHub:

- Start with the overview to understand the project objective before opening notebooks or source files.
- Read the repository structure section to identify the main entry point.
- Inspect generated outputs before rerunning experiments; they provide a quick view of the current project state.
- Review scripts and notebooks together when both are present, since notebooks often explain decisions while scripts preserve reusable execution paths.
- Check the limitations section before interpreting results too strongly.
- Use the possible extensions section to understand how the project can grow without changing its core purpose.

## Troubleshooting

Common issues and fixes:

- If imports fail, confirm that the virtual environment is activated and dependencies were installed from `requirements.txt`.
- If a notebook cell fails because a variable is missing, restart the kernel and run the notebook from the first cell.
- If a script cannot find a data file, run it from the repository root unless the README gives a different working directory.
- If plots are not regenerated, check that the output folder exists and that the script has write permission.
- If a package version causes errors, create a fresh environment and reinstall dependencies before debugging the source code.
- If GPU-related packages are unavailable, run CPU-compatible sections first and treat heavier deep-learning experiments separately.

## Development Notes

The repository is organized to be understandable before it is optimized. Most code favors clear structure, visible intermediate steps, and saved artifacts over highly compressed implementations. When extending the project, prefer small changes that keep the original experiment reproducible.

Recommended development practices:

- Keep new data files under `data/`, `datasets/`, or the existing local data folder for that project.
- Keep generated figures under `figures/`, `plots/`, `outputs/`, or `results/` depending on the existing convention.
- Add new experiments as separate scripts or clearly labeled notebook sections.
- Avoid overwriting existing outputs unless the experiment is intentionally being refreshed.
- Document any new dependency in `requirements.txt`.
- Prefer relative paths so the repository works after cloning on another machine.

## Project Status

This repository is prepared as a standalone GitHub project. The current version includes the core implementation, documentation, and available artifacts needed to understand the work. Future improvements can focus on stronger automation, more tests, richer visual summaries, and cleaner packaging where appropriate.

## Possible Extensions

- Add a CLI that recommends words from the current candidate set.
- Add entropy-based scoring for guesses.
- Track constraints after green, yellow, and gray feedback.
- Add tests for sampling and filtering utilities.

## Tech Stack

Python, NumPy, Pandas, Matplotlib, CVXPY, tqdm, Jupyter Notebook.

## Author

Prahladha, IIT Hyderabad
