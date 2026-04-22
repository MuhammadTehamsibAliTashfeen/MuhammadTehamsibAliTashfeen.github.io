---
layout: post
title: "From IS Auditor to PhD Researcher: Why Industry Experience Changed How I Do Security Research"
date: 2024-04-20 00:00:00 -0500
description: Reflections on transitioning from three years in enterprise cybersecurity to a PhD program, and what the industry background actually changes about how I approach research problems.
tags: [PhD, career, cybersecurity, research]
categories: personal
---

Before starting my PhD at Wichita State, I spent three years doing cybersecurity work in industry — first as an Information Systems Auditor at The Bank of Punjab, then briefly as a Senior Consultant in Ernst & Young's Technology Risk practice. I audited core banking systems, wrote ITGC control matrices, and evaluated security posture across more than 100 banking applications against SBP regulations.

It was not the most glamorous work, but it gave me something that I think many PhD students lack early on: a concrete sense of what "security failure" actually costs in a production environment.

**What changed when I started the PhD**

The most immediate shift was in how I read papers. In industry, a false positive in an automated security scan is not an academic statistic — it is an analyst spending three hours chasing a ghost finding, or a remediation ticket that clogs the queue and delays real fixes. When I read static analysis papers now and see precision numbers in the 60–70% range described as "acceptable," I think about what that means operationally. It sharpens the questions I ask.

The second shift was in problem selection. My dissertation work on Android memory leak detection is partly motivated by what I saw in enterprise mobile application reviews — teams deploying apps with obvious lifecycle management issues that no automated scan flagged, because the benchmarks used to evaluate those scans didn't represent real-world complexity.

**What industry does not prepare you for**

Writing. The transition from audit reports (structured, templated, never more than necessary) to academic prose (precise argumentation over many pages) took most of my first year. They reward opposite instincts.

Also: the pace. Audits move on fixed quarterly cycles. Research moves on the schedule of reviewers, which is to say: unpredictably and slowly.

If you are considering a similar transition, the practical advice I would give is this — document the gap between what automated tools claim and what you actually see on the ground. That gap is where interesting research lives.
