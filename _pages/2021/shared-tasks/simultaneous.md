---
permalink: /2021/simultaneous
title: "Simultaneous Speech Translation"
---

## Description

<!-- the task, the languages, and the type of data -->

This task focuses on the real time (also known as simultaneous or streaming) aspect of speech and machine translation as it enables interesting applications such as simultaneous interpretation or international conference live translations. Real-time systems are typically evaluated with respect to quality and latency. This year, we will have 3 tracks:

* Text-to-Text: translating ground-truth transcripts in real-time from English to German.
* Speech-to-Text: directly translating speech into text in real-time from English to German.
* [New] Text-to-Text Simultaneous Interpretation: translating ground-truth transcripts in real-time from English to Japanese. The reference will not be a human translation crafted offline but rather correspond to the transcript of a simultaneous interpretation.

We encourage participants to enter all tracks when possible. We also encourage participants to contrast cascaded and end-to-end solutions for the Speech-to-Text track.

## Evaluation

We will use a very similar system as last year for evaluation. The system's performance will be evaluated in two ways:

* Translation quality: we will use multiple standard metrics: BLEU, TER, and METEOR.
* Translation latency: we will make use of the recently developed metrics for simultaneous machine translation including average proportion (AP), average lagging (AL) and differentiable average lagging (DAL).

This year, the evaluation implementation will use the [SimulEval](https://github.com/facebookresearch/SimulEval) toolkit. For latency measurement, we will contrast computation aware and non computation aware latency metrics. See the [SimulEval description](https://arxiv.org/abs/2007.16193) for how those metrics are defined. Note that the definition of average lagging has been modified from the [original definition](https://www.aclweb.org/anthology/P19-1289/) (see section 3.2 in the [SimulEval description](https://arxiv.org/abs/2007.16193)).

## Training and Development Data

### Text-to-Text and Speech-to-Text Tracks

You may use the same training and development data available for the [Offline Speech Translation task](https://iwslt.org/2021/offline). Specifically, please refer to the [Allowed Training Data](https://iwslt.org/2021/offline#allowed-training-data) and the [Past Editions Development Data](https://iwslt.org/2021/offline#past-editions-development-data) sections.

### Text-to-Text Simultaneous Interpretation Track

Coming soon.

## Baseline Implementation and Example

Coming soon.

## System Submission

Coming soon.

## Contacts

Discussion: iwslt-evaluation-campaign@googlegroups.com

## Organizers

<!-- list of names and affiliations -->

* Katsuhito Sudoh (NAIST)
* Satoshi Nakamura (NAIST)
* Xutai Ma (Johns Hopkins University, Facebook)
* Maha Elbayad (Facebook)
* Changhan Wang (Facebook)
* Juan Pino (Facebook)

<!-- Markdown notes: comments can be formed as above; bulleted lines start with a - ; if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line -->
