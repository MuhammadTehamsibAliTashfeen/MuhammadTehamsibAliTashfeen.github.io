---
layout: page
title: LLM-Assisted Program Analysis
description: Studying how large language models can triage, explain, and reason about Android bug patterns to augment static analysis workflows.
importance: 2
category: work
---

A research thread running alongside my dissertation work at WSU SAIL Lab.

**Motivation.** Static analysis tools produce large volumes of results that require human interpretation. LLMs can potentially automate the triage and explanation step — but only if their outputs are reliable and calibrated against ground truth.

**Research questions.**
- Can LLMs accurately classify whether a static analysis warning is a true positive or false positive when given relevant code context?
- How do different prompting strategies (zero-shot, chain-of-thought, retrieval-augmented) affect precision on Android bug triage?
- Where do LLMs systematically fail, and what does that reveal about the limits of in-context reasoning over program semantics?

**Stack.** Python · HuggingFace Transformers · OpenAI API · Anthropic API · PyTorch

**Status.** Active — preliminary results in progress.
