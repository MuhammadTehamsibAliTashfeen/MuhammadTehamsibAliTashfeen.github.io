---
layout: page
title: Android Memory Leak Benchmark
description: Large-scale, manually validated benchmark of 650+ Android projects with confirmed memory leak patterns, built using Soot and FlowDroid.
importance: 1
category: work
---

A core component of my dissertation at the [Software Analysis and Intelligence Lab](https://www.wichita.edu/), Wichita State University. Advised by Dr. Zhiyong Shan.

**Problem.** Existing Android static analysis benchmarks are small, synthetically generated, or lack ground-truth validation — making it difficult to evaluate whether new tools represent genuine improvements.

---

#### Pipeline Overview

{% include figure.liquid path="assets/img/projects/ann_recognition.png" caption="Static analysis pipeline: source APKs → IR transformation → taint/data-flow analysis → manual triage → ground-truth labels." class="img-fluid rounded z-depth-1" zoomable=true %}

**Stage 1 — Candidate Collection.** Mined 650+ open-source Android repositories from GitHub, filtering by activity lifecycle complexity and minimum build health criteria.

**Stage 2 — Static Analysis Pass.** Ran [FlowDroid](https://github.com/secure-software-engineering/FlowDroid) (built on [Soot](https://soot-oss.github.io/soot/)) with a custom source/sink configuration targeting `Context` and `View` objects held past their expected lifecycle boundaries.

**Stage 3 — Manual Triage.** Reviewed each flagged case against the source code and cross-referenced with issue trackers to confirm ground truth.

---

#### Benchmark Statistics

| Metric | Value |
|--------|-------|
| Android projects analyzed | 650+ |
| Confirmed leak patterns | In progress |
| Analysis framework | Soot + FlowDroid |
| Ground-truth method | Manual triage + issue tracker |
| HPC cluster | NSF Expanse (Slurm) |
| Programming language | Java (Android), Python (tooling) |

---

#### Why Manual Triage Matters

Without manual validation, a benchmark reflects the tool's false positive rate rather than the true distribution of Android memory bugs. Our triage step ensures every entry in the dataset has a confirmed ground-truth label, making it suitable for training and evaluating AI-based bug detection models.

**Stack.** Java · Soot · FlowDroid · Android SDK · Python · Slurm (HPC)

**Status.** Active — benchmark and tooling will be released publicly alongside the dissertation paper.
