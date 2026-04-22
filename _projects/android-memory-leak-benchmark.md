---
layout: page
title: Android Memory Leak Benchmark
description: Large-scale, manually validated benchmark of 650+ Android projects with confirmed memory leak patterns, built using Soot and FlowDroid.
importance: 1
category: work
---

A core component of my dissertation at the [Software Analysis and Intelligence Lab](https://www.wichita.edu/), Wichita State University.

**Problem.** Existing Android static analysis benchmarks are small, synthetically generated, or lack ground-truth validation — making it difficult to evaluate whether new tools represent genuine improvements.

**Approach.**
- Mined 650+ open-source Android repositories from GitHub, targeting projects with non-trivial activity lifecycle complexity
- Ran [FlowDroid](https://github.com/secure-software-engineering/FlowDroid) (built on [Soot](https://soot-oss.github.io/soot/)) with a custom leak-source/sink configuration for `Context` and `View` objects
- Manually triaged each flagged case against source code and developer issue trackers to confirm ground truth

**Stack.** Java · Soot · FlowDroid · Android SDK · Python (corpus collection) · Slurm (HPC)

**Status.** Active — benchmark and tooling will be released publicly alongside the dissertation paper.
