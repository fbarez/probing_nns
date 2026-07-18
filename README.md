<h1 align="center">Probing Neural Networks</h1>

<p align="center">
  A hands-on tutorial on reading concepts out of a language model’s internal representations.<br>
  Companion to the OXML Summer School 2026 lecture
  <a href="OXML_Summer_School_2026_Lecture.pdf"><em>Probing Neural Networks</em></a>.
</p>

<p align="center">
  <a href="https://colab.research.google.com/github/fbarez/probing_nns/blob/main/probing_tutorial.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open the tutorial in Colab"></a>
  &nbsp;·&nbsp;
  <a href="https://colab.research.google.com/github/fbarez/probing_nns/blob/main/probing_tutorial_solutions.ipynb">Solutions</a>
</p>

---

You will build the probing toolkit on a real transformer (GPT-2), from scratch — and, just as
importantly, learn to interrogate your own results. The difference between a careful probing study and
a misleading one comes down to three things, and you will implement all of them: **baselines**,
**selectivity**, and the gap between information a model makes *accessible* and information it actually
*uses*.

## Getting started

Open **`probing_tutorial.ipynb`** in Colab (button above) and work through it top to bottom — no
setup, no API keys, no gated models. Each exercise is a small gap to fill, marked `# ✏️ EXERCISE`, and
is followed by a self-check that confirms your answer before you move on. Reach for the solutions only
once you’ve tried.

> Prefer local? `pip install -r requirements.txt`, then open the notebook in Jupyter. It runs on a
> laptop CPU in a few minutes; a free Colab T4 GPU is faster.

## What the tutorial covers

The arc follows the lecture, but every idea becomes code you write and a result you have to interpret.

| Section | You implement | The idea it teaches |
|---|---|---|
| **Representations** | mean-pooled frozen hidden states | a concept becomes a vector, `h ∈ ℝᵈ` |
| **A linear probe** | logistic regression on `h` | is the concept a *direction*? |
| **Layer profile** | a sweep over every layer | *where* a concept lives is a finding |
| **Baselines & selectivity** | majority · random-representation · control task | why raw accuracy misleads |
| **Linear vs. MLP** | a higher-capacity probe | a stronger probe can tell you *less* |
| **Accessible ≠ used** | ablate the direction; steer the model | probing shows access; intervention shows use |
| **Truthfulness / deception** | the same pipeline, pointed at honesty | the basis of real safety probes |
| **Capstone** | your own study, honestly reported | the full method, end to end |

## Contents

| File | |
|---|---|
| `probing_tutorial.ipynb` | the tutorial — exercises to complete |
| `probing_tutorial_solutions.ipynb` | the same notebook with answers |
| `OXML_Summer_School_2026_Lecture.pdf` | the lecture slides |
| `requirements.txt` | dependencies |

## References

- The lecture slides in this repository.
- Hewitt & Liang (2019), *Designing and Interpreting Probes with Control Tasks* — the selectivity idea.
- Apollo Research (2025), *Detecting Strategic Deception Using Linear Probes*.
- EleutherAI [`mdl`](https://github.com/EleutherAI/mdl) — minimum-description-length probing.
