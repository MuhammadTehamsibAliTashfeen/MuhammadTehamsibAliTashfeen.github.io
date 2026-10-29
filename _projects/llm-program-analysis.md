---
layout: page
title: LLM-Assisted Program Analysis
description: Studying how large language models can triage, explain, and reason about Android bug patterns to augment static analysis workflows.
importance: 2
category: work
---

A research thread running alongside my dissertation work at WSU SAIL Lab. Advised by Dr. Zhiyong Shan.

**Motivation.** Static analysis tools produce large volumes of results that require human interpretation. LLMs can potentially automate the triage and explanation step — but only if their outputs are reliable and calibrated against ground truth.

---

#### Transformer Architecture

{% include figure.liquid path="assets/img/projects/transformer_arch.png" caption="Transformer architecture underlying modern LLMs — the foundation for code/bug reasoning in this research." class="img-fluid rounded z-depth-1" zoomable=true %}

---

#### AI / ML / DL Relationship

{% include figure.liquid path="assets/img/projects/ai_ml_dl.png" caption="Relationship between Artificial Intelligence, Machine Learning, and Deep Learning — the research sits at the intersection of all three." class="img-fluid rounded z-depth-1" zoomable=true %}

---

#### Research Questions

| #   | Question                                                                                                       |
| --- | -------------------------------------------------------------------------------------------------------------- |
| 1   | Can LLMs accurately classify static analysis warnings (true vs. false positive) given relevant code context?   |
| 2   | How do prompting strategies (zero-shot, CoT, RAG) affect precision on Android bug triage?                      |
| 3   | Where do LLMs systematically fail, and what does that reveal about the limits of in-context program reasoning? |

---

#### Approach

- Constructed 3,152 prompt-response examples from LeakScope-flagged Android lifecycle violations
- Developed LoRA fine-tuning pipelines for CodeLlama, Llama-3, and StarCoder2
- Evaluated fine-tuned models against GPT-4o on bug triage and explanation quality

**Stack.** Python · PyTorch · Hugging Face Transformers · LoRA fine-tuning · GPT-4o evaluation

**Status.** Active — research software and benchmark data produced as part of the LeakScope dissertation work (see [Projects](/projects/)).
