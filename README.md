# Probing Neural Networks — hands-on tutorial

A hands-on companion to the OXML Summer School 2026 lecture **“Probing Neural Networks”**
(slides: [`OXML_Summer_School_2026_Lecture.pdf`](OXML_Summer_School_2026_Lecture.pdf)).

You build the whole probing toolkit on a real transformer (GPT-2), from scratch — and, more
importantly, learn to **distrust your own probe**: baselines, **selectivity**, and the gap between a
concept being *accessible* and the model actually *using* it.

## Start here

| | open in Colab |
|---|---|
| **Tutorial** (fill in the exercises) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fbarez/probing_nns/blob/main/probing_tutorial.ipynb) |
| **Solutions** (answers filled in) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fbarez/probing_nns/blob/main/probing_tutorial_solutions.ipynb) |

Work through **`probing_tutorial.ipynb`**. Cells marked `# ✏️ EXERCISE` have a piece missing
(`raise NotImplementedError`) — fill it in, then run the **self-check** cell right after it. If it runs
without an assertion error, you’ve got it. Peek at the solutions only when you’re stuck.

Runs free on Colab (`Runtime → Change runtime type → T4 GPU`) or on a laptop CPU in a few minutes — no
API keys, no gated models.

## What you’ll build (mirrors the lecture)

0. **Setup** — load a frozen GPT-2. *Only the probe learns.*
1. **Data** — a concept with clean labels (sentiment).
2. **Representations** *(Ex 1)* — mean-pool frozen hidden states into `h ∈ ℝᵈ`.
3. **First linear probe** *(Ex 2)* — logistic regression on `h`.
4. **Layer profile** *(Ex 3)* — probe every layer; the shape is a finding.
5. **Baselines & selectivity** *(Ex 4)* — majority, random-representation, control task → **selectivity**.
6. **Linear vs MLP** *(Ex 5)* — a stronger probe that tells you *less*.
7. **Accessible ≠ used** *(Ex 6)* — ablate the concept direction; steer the running model.
8. **The real thing** *(Ex 7)* — point the pipeline at truthfulness/deception (the basis of real
   safety probes, e.g. Apollo Research’s deception probes).
9. **Capstone** — design your own study and write the honest report.

## Requirements

`transformers`, `torch`, `scikit-learn`, `datasets`, `matplotlib` (see `requirements.txt`). On Colab
they’re already installed; locally: `pip install -r requirements.txt`.

## Further reading

- The lecture slides in this repo.
- Hewitt & Liang (2019), *Designing and Interpreting Probes with Control Tasks* — the selectivity idea.
- Apollo Research (2025), *Detecting Strategic Deception Using Linear Probes*.
- EleutherAI [`mdl`](https://github.com/EleutherAI/mdl) — minimum-description-length probing (§5, advanced).
