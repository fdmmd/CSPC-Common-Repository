# CSPC — Computer Science for Physics and Chemistry

My coursework repository for the course.
Each practical lives under `PW<n>/Lab <X>/`.

## Setup

Create and activate the environment for a given lab:

```bash
conda env create -f "PW<n>/Lab <X>/environment.yml"
conda activate cspc
```

Run the tests for a lab from inside its folder:

```bash
cd "PW<n>/Lab <X>"
pytest -v
```

---

## PW1 — Lab A: Reproducible Foundations

**What I built:**
- <one or two lines: the CSPC repo, the environment, the decay simulation, the tests>

**Speed comparison (loop vs NumPy):**

| version | time (s) |
|---------|----------|
| pure-Python loop | ... |
| NumPy (vectorised) | ... |

- Speed-up: **... × faster**

**Tests:** all passing? (yes / no)

**Conclusion:**
- <2–3 sentences: what worked, what you learned, any problems you hit and how you solved them>

---

<!-- Future sessions: add a new "## PW<n> — Lab <X>" section below. -->
---

## PW1 - Lab B: Real Data and a Snakemake Pipeline

**What I built:**
Read a real radioactive-decay dataset (`decay_observed.csv`), compared it to the
analytical law N0·exp(-λt) with a side-by-side plot, and automated the figure
with a small Snakemake pipeline.

**What the data showed:**
The observed points follow the analytical decay curve closely — the decay
matches the exponential law well over the whole time range, with only small
statistical fluctuations around the curve.

**Pipeline:**
The `Snakefile` defines a rule that builds `figure.png` from
`decay_observed.csv` by running `plot.py`. Running
`snakemake --cores 1 figure.png` rebuilds the figure only when an input
changes, so the pipeline stays consistent.

**Conclusion:**
The real data confirms the analytical decay law. Snakemake makes the workflow
reproducible: one command rebuilds exactly what is out of date, nothing more.