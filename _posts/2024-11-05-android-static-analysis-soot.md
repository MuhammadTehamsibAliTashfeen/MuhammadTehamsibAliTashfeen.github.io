---
layout: post
title: "Building a Memory Leak Benchmark for Android with Soot"
date: 2024-11-05 00:00:00 -0500
description: How I am constructing a large-scale, manually validated benchmark of Android memory leaks using the Soot static analysis framework.
tags: [Android, static analysis, Soot, memory leaks, benchmark]
categories: research
---

One of the persistent problems in Android static analysis research is benchmark quality. Many published datasets are small, synthetically generated, or lack ground-truth validation — which makes it hard to know whether a new tool is genuinely better or just overfitting to the benchmark's quirks.

My dissertation work addresses this by constructing a manually validated benchmark of **650+ real Android projects** with confirmed memory leak patterns, using [Soot](https://soot-oss.github.io/soot/) as the underlying analysis framework.

---

#### Why Soot?

Soot provides a stable intermediate representation (Jimple) for Android bytecode that survives the dex-to-IR conversion cleanly. FlowDroid — built on top of Soot — gives us taint tracking with context, flow, and field sensitivity out of the box.

| Property | Soot / FlowDroid | Alternative Tools |
|---|---|---|
| IR stability | Jimple (stable) | Varies |
| Context sensitivity | ✓ | Partial |
| Flow sensitivity | ✓ | Partial |
| Field sensitivity | ✓ | Rare |
| Android lifecycle model | ✓ (FlowDroid) | Limited |
| Open source | ✓ | Mixed |

---

#### The Benchmark Construction Pipeline

{% include figure.liquid path="assets/img/blog/benchmark_pipeline.png" caption="Static analysis pipeline: source APKs → Soot IR transformation → FlowDroid taint analysis → flagged results → manual triage → ground-truth labels." class="img-fluid rounded z-depth-1" zoomable=true %}

The pipeline runs in three stages:

1. **Candidate collection** — mining 650+ open-source Android repositories from GitHub using dependency signatures and build metadata.
2. **Static analysis pass** — running FlowDroid with a custom leak source/sink configuration targeting `Context` and `View` objects held past lifecycle boundaries.
3. **Manual triage** — reviewing each flagged case against source code and issue trackers to confirm ground truth.

---

#### Benchmark Statistics

| Metric | Value |
|---|---|
| Projects collected | 650+ |
| Analysis framework | Soot + FlowDroid |
| Leak pattern targets | `Context`, `View`, `Activity` lifecycle |
| Ground-truth method | Manual triage + issue tracker |
| Compute | NSF Expanse HPC (Slurm) |

---

{% include figure.liquid path="assets/img/blog/leak_distribution.png" caption="Relationship between AI, ML, and Deep Learning — the methodological stack used for LLM-assisted triage of static analysis results." class="img-fluid rounded z-depth-1" zoomable=true %}

---

#### Why Manual Triage Is Non-Negotiable

Without it, a benchmark reflects the tool's false positive rate rather than the true distribution of Android memory bugs. Our triage step ensures every entry has a confirmed ground-truth label — making it suitable for training and evaluating AI-based bug detection models.

The benchmark will be released publicly alongside the paper. If you are working on Android analysis tooling and want early access, get in touch.
