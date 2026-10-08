---
layout: page
title: AfriLearner360
description: Culturally grounded assessment generation for Rwandan primary schools on a zero budget
importance: 3
category: research
github: https://github.com/GbotemiB/afrilearner360
related_publications: true
---

AfriLearner360 generates culturally grounded assessment items for Rwandan primary education (P1 to P5), running entirely on free-tier language models at zero API cost {% cite bolarinwa2026culturally %}.

Three constraints shaped the design: no device per learner, no budget for paid model access, and a teacher between generated content and learners. The pipeline has four stages:

1. **Item generation**: a language model writes assessment items grounded in a Rwandan cultural knowledge base, under a strict JSON schema.
2. **Response capture**: a learner splits a fixed point budget across four options per item.
3. **Scoring**: deterministic, non-AI code turns responses into an engagement-trait profile. No model output influences a score.
4. **Rendering**: a language model turns the profile into a teacher-readable summary.

Key findings:

- Every free model tested produced valid JSON, but schema adherence split them completely by declared capability. Valid JSON is not valid output.
- Scored profiles were byte-identical across 250 repeated scorings and across separate interpreters.
- A full term of content (200 generation calls) costs about $0.81 at paid rates, but takes 4 days under free-tier rate limits. Throughput, not price, is the binding constraint.

No classroom validation has been done yet. The results describe the generation and scoring pipeline, not learning outcomes.
