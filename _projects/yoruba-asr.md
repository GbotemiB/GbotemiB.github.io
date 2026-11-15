---
layout: page
title: Yoruba-English Code-Switched ASR
description: Speech recognition for Yoruba-English code-switched speech
importance: 1
category: research
related_publications: true
---

Yoruba speakers routinely switch between Yoruba and English within a single sentence, and most speech recognition systems handle this poorly. At [Lyngual Labs](https://lynguallabs.org/), I work on closing that gap.

- Co-led the collection and transcription of **100 hours of Yoruba-English code-switched speech** across 10+ domains, creating one of the first open corpora for this language pair.
- Handled preprocessing, segmentation, language-boundary marking and alignment of the multilingual audio, and designed the team's evaluation strategy.
- Fine-tuned Whisper Large v3 and MMS-1B-All on code-switched speech, cutting word error rate from **72.6% to 32.2%** (a 55.8% relative reduction).

The work has produced peer-reviewed papers, including the **Best Paper Award at Deep Learning Indaba 2025** {% cite bolarinwa2025closing babatunde2025beyond %}. It has since extended to edge ASR across 19 African languages {% cite olufemi2026waxalnet %}. Three posters from this line of work were accepted at the WiML workshop at NeurIPS 2026, including YECS, a 120-hour Yoruba-English code-switching corpus with a diagnostic framework for low-resource speech recognition.
