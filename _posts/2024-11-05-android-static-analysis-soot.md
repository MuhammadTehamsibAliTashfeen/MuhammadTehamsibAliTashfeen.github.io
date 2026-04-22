---
layout: post
title: "Building a Memory Leak Benchmark for Android with Soot"
date: 2024-11-05 00:00:00 -0500
description: How I am constructing a large-scale, manually validated benchmark of Android memory leaks using the Soot static analysis framework.
tags: [Android, static analysis, Soot, memory leaks, benchmark]
categories: research
---

One of the persistent problems in Android static analysis research is benchmark quality. Many published datasets are small, synthetically generated, or lack ground-truth validation — which makes it hard to know whether a new tool is genuinely better or just overfitting to the benchmark's quirks.

My current dissertation work addresses this directly by constructing a manually validated benchmark of **650+ real Android projects** with confirmed memory leak patterns, using [Soot](https://soot-oss.github.io/soot/) as the underlying analysis framework.

**Why Soot?** Soot provides a stable intermediate representation (Jimple) for Android bytecode that survives the dex-to-IR conversion cleanly. Its call-graph construction and points-to analysis are mature enough for large-scale corpus analysis, and FlowDroid — built on top of Soot — gives us taint tracking with context, flow, and field sensitivity out of the box.

**The benchmark construction pipeline** runs in three stages:

{% include figure.liquid path="assets/img/blog/benchmark_pipeline.png" caption="Three-stage pipeline: candidate collection → static analysis pass → manual ground-truth triage." class="img-fluid rounded z-depth-1" zoomable=true %}

1. *Candidate collection* — mining open-source Android repositories on GitHub using a combination of dependency signatures and build metadata to identify projects with non-trivial activity lifecycle complexity.
2. *Static analysis pass* — running FlowDroid with a custom leak-source/sink configuration targeting `Context` and `View` objects held past their expected lifecycle boundaries.
3. *Manual triage* — reviewing each flagged case against the source code and, where possible, cross-referencing with issue trackers to confirm whether the pattern was a real leak that developers fixed.

{% include figure.liquid path="assets/img/blog/leak_distribution.png" caption="Distribution of confirmed memory leak patterns across the 650+ Android projects in the benchmark." class="img-fluid rounded z-depth-1" zoomable=true %}

The manual triage step is slow but essential. Without it, you end up with a benchmark that reflects the tool's false positive rate rather than the true distribution of Android memory bugs.

The benchmark will be released publicly alongside the paper. If you are working on Android analysis tooling and want early access or want to contribute to the triage effort, get in touch.
