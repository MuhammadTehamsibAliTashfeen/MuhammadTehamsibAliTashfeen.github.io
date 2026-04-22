---
layout: post
title: "From IS Auditor to PhD Researcher: Why Industry Experience Changed How I Do Security Research"
date: 2024-04-20 00:00:00 -0500
description: Reflections on transitioning from three years in enterprise cybersecurity to a PhD program, and what the industry background actually changes about how I approach research problems.
tags: [PhD, career, cybersecurity, research]
categories: personal
---

Before starting my PhD at Wichita State, I spent three years doing cybersecurity work in industry — first as an Information Systems Auditor at The Bank of Punjab, then briefly as a Senior Consultant in Ernst & Young's Technology Risk practice. I audited core banking systems, wrote ITGC control matrices, and evaluated security posture across more than 100 banking applications against SBP regulations.

It was not the most glamorous work, but it gave me something that many PhD students lack early on: a concrete sense of what "security failure" actually costs in a production environment.

---

#### My Career Path

| Period | Role | Organization |
|---|---|---|
| Jan 2020 – Nov 2020 | Executive Engineer | Iron Bridge Systems |
| Nov 2020 – Mar 2023 | Information Systems Auditor | The Bank of Punjab |
| Mar 2023 – Jun 2023 | Senior Consultant, Technology Risk | Ernst & Young |
| Aug 2023 – Present | PhD Researcher | Wichita State University (SAIL Lab) |

---

#### What Changed When I Started the PhD

**How I read papers.** In industry, a false positive in an automated security scan is not an academic statistic — it is an analyst spending three hours chasing a ghost finding. When I see precision numbers in the 60–70% range described as "acceptable" in a paper, I think about what that means operationally. It sharpens the questions I ask.

**Problem selection.** My dissertation work on Android memory leak detection is partly motivated by what I saw in enterprise mobile application reviews — teams deploying apps with obvious lifecycle management issues that no automated scan flagged, because the benchmarks used to evaluate those scans didn't represent real-world complexity.

---

#### Industry vs. Research: Key Differences

| Dimension | Industry (IS Audit) | PhD Research |
|---|---|---|
| Output format | Structured audit report | Academic paper |
| Timelines | Fixed quarterly cycles | Reviewer-driven (unpredictable) |
| Precision expectation | Zero tolerance for false positives | Accepted with caveats |
| Problem scope | Defined by client/regulation | Self-directed |
| Writing style | Concise, templated | Precise, argumentative |
| Validation method | Compliance frameworks | Empirical evaluation |

---

#### What Industry Does Not Prepare You For

**Writing.** The transition from audit reports to academic prose took most of my first year. They reward opposite instincts — brevity vs. completeness, templated vs. argumentative.

**Pace.** Audits move on fixed quarterly cycles. Research moves on the schedule of reviewers — unpredictably and slowly.

**Ambiguity.** In audit work, the scope is defined by the client and the regulation. In research, you define the problem — and the hardest skill is learning to scope it correctly.

---

If you are considering a similar transition, the practical advice I would give: document the gap between what automated tools claim and what you actually see on the ground. That gap is where interesting research lives.
