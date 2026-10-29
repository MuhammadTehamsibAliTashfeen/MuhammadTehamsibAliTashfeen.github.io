---
layout: page
title: LeakScope
description: Soot-based static detection framework for Android lifecycle memory-retention bugs, evaluated on 627 open-source apps. Lead-author submission to ICSE 2027.
importance: 1
category: work
---

The flagship artifact of my dissertation at the [Software Analysis and Intelligence Lab](https://www.wichita.edu/academics/engineering/SoC/research/software-intelligence-analysis-lab/index.php), Wichita State University. Advised by Dr. Zhiyong Shan.

**Problem.** Existing Android static analysis tools are evaluated on small, synthetically generated benchmarks or lack ground-truth validation — making it difficult to judge whether a new detector represents a genuine improvement over established tools like Android Lint, SpotBugs, and Infer.

---

#### Pipeline Overview

{% include figure.liquid path="assets/img/projects/ann_recognition.png" caption="Detection pipeline: source APKs → IR transformation (Soot/Jimple) → lifecycle-obligation rule matching → manual triage → ground-truth labels." class="img-fluid rounded z-depth-1" zoomable=true %}

**LeakScope** is a Soot-based framework that translates Android lifecycle obligations (e.g., unregistering listeners, releasing `Context` references, closing resources on `onDestroy`) into static rules for detecting memory-retention and resource-management patterns in compiled applications.

---

#### Evaluation

| Metric                             | Value                            |
| ---------------------------------- | -------------------------------- |
| Open-source Android apps analyzed  | 627                              |
| Apps flagged in the reported study | 485                              |
| Baselines compared                 | Android Lint, SpotBugs, Infer    |
| Analysis framework                 | Soot, Jimple IR                  |
| HPC cluster                        | NSF ACCESS / Expanse (Slurm)     |
| Programming language               | Java (Android), Python (tooling) |

---

#### Why Manual Triage Matters

Without manual validation, a benchmark reflects a tool's false-positive rate rather than the true distribution of Android memory bugs. Ground-truth labels for the underlying dataset are confirmed through manual code inspection and cross-referencing with issue trackers, supervised as part of the lab's mentorship program.

**Stack.** Java · Soot/Jimple IR · Android SDK · Python · Slurm (HPC)

**Status.** Lead-author paper — _"LeakScope: Lifecycle-Aware Static Detection of Memory Retention Patterns in Android"_ — submitted to the 49th IEEE/ACM International Conference on Software Engineering ([ICSE 2027](/publications/), Research Track). Also presented as a [tool pitch](https://github.com/MuhammadTehamsibAliTashfeen/-academic-archive/blob/main/ISSRE_Presentation_Poster_Pitch.pdf) at ISSRE 2026.
