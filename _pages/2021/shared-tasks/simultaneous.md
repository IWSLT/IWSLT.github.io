---
permalink: /2021/simultaneous
title: "Simultaneous Speech Translation"
---

## Description

<!-- the task, the languages, and the type of data -->

This task focuses on the real time (also known as simultaneous or streaming) aspect of speech and machine translation as it enables interesting applications such as simultaneous interpretation or international conference live translations. Real-time systems are typically evaluated with respect to quality and latency. This year, we will have 3 tracks:

* Text-to-Text: translating ground-truth transcripts in real-time from English to German.
* Speech-to-Text: directly translating speech into text in real-time from English to German.
* [New] Text-to-Text Simultaneous Interpretation: translating ground-truth transcripts in real-time from English to Japanese. The reference will not be a human translation crafter offline but rather correspond to the transcript of a simultaneous interpretation.

We encourage participants to enter all tracks when possible.

We will use a very similar system as last year for evaluation. The system's performance will be evaluated in two ways:

* Translation quality: we will use multiple standard metrics: BLEU, TER, and METEOR.
* Translation latency: we will make use of the recently developed metrics for simultaneous machine translation including average proportion (AP), average lagging (AL) and differentiable average lagging (DAL).

The evaluation implementation will use [SimulEval](https://github.com/facebookresearch/SimulEval).

## Organizers

<!-- list of names and affiliations -->

* Katsuhito Sudoh (NAIST)
* Satoshi Nakamura (NAIST)
* Xutai Ma (Johns Hopkins University, Facebook)
* Maha Elbayad (Facebook)
* Changhan Wang (Facebook)
* Juan Pino (Facebook)

<!-- Markdown notes: comments can be formed as above; bulleted lines start with a - ; if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line -->
