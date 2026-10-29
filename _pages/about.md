---
layout: about
title: about
permalink: /
subtitle: >
  PhD Candidate · Electrical Engineering & Computer Science ·
  <a href="https://www.wichita.edu/" target="_blank">Wichita State University</a>

profile:
  align: right
  image: prof_pic.jpg
  image_circular: true
  more_info: >
    <p>Software Analysis &amp; Intelligence Lab</p>
    <p>256 Jabara Hall</p>
    <p>Wichita State University</p>
    <p>Wichita, Kansas 67260</p>

announcements:
  enabled: true
  scrollable: true
  limit: 5
selected_papers: true
social: true
---

I am a PhD candidate in the [School of Computing](https://www.wichita.edu/academics/engineering/SoC/) at Wichita State University, working in the [Software Analysis and Intelligence Laboratory](https://www.wichita.edu/academics/engineering/SoC/research/software-intelligence-analysis-lab/index.php) under the supervision of [Dr. Zhiyong Shan](https://www.wichita.edu/profiles/academics/engineering/SoC/01_Faculty/Shan-Zhiyong.php). My dissertation, _"Automated Detection of Android Lifecycle Anti-Patterns: From Static Analysis to Fine-Tuned Large Language Models,"_ develops principled techniques for finding reliability and security defects in mobile software by combining static program analysis with domain-adapted code language models.

I designed and built **LeakScope**, a Soot-based static analysis framework that translates Android lifecycle obligations into detection rules for memory-retention and resource-management anti-patterns. In our large-scale empirical study, LeakScope analyzed 627 open-source Android applications and flagged 485, with app-level detection coverage compared against Android Lint, SpotBugs, and Infer. In a parallel line of work, I constructed 3,152 prompt-response examples and developed LoRA fine-tuning pipelines for CodeLlama, Llama-3, and StarCoder2, evaluated against GPT-4o, to investigate whether open-source LLMs can reliably identify lifecycle violations from source code.

Prior to my doctoral studies, I spent three years in industry cybersecurity, including roles as a Senior Consultant (Technology Risk) at Ernst & Young Ford Rhodes and an Information Systems Auditor at The Bank of Punjab, where I evaluated security controls across 100+ enterprise systems and led audits for major telecommunications and financial institutions. I hold a BS in Electrical Engineering from [FAST-NUCES](https://www.nu.edu.pk), Peshawar.

#### Research Interests

- AI-assisted software engineering
- Static program analysis
- Android application reliability and security
- Domain adaptation of code language models
- Empirical software engineering and reproducible evaluation
