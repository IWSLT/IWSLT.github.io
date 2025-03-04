---
permalink: /2025/simultaneous
title: "Simultaneous track"
toc: true
toc_sticky: true
---

<!--
Markdown notes: comments can be formed as in this example;
bulleted lines start with a - ;
if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line
-->

## Description
<!-- Description the task, the languages, and the type of data -->

Simultaneous translation (also known as real-time or streaming translation) is the task of generating translations incrementally given partial input only.
Simultaneous translation enables interesting applications such as automatic simultaneous interpretation or international conference translations.
Simultaneous systems are typically evaluated with respect to quality and latency.

There will be two tracks:
- Text-to-Text: simultaneously translating text in source language into text in target language. Participants will employ an ASR agent of their choice to produce the text, so as to respect computational latency constraints.
- Speech-to-Text: simultaneously translating speech in source language into text in target language.

in the following language directions (more details will be made available soon):

- English -> German
- ~~English -> Arabic (new)~~ (cancelled in the simultaneous track)
- English -> Chinese
- English -> Japanese
- Czech -> English

We have two focuses this year: 
- **long-form speech**: our evaluation will be conducted on *unsegmented* speech
- **large language models**: participants are allowed to use LLMs (details will be announced later)

The test set domains are the subsets of the ones of the offline track:
- English -> German: ACL talks and accent challenge data
- ~~English -> Arabic: business news~~ (cancelled)
- English -> Chinese: ACL talks
- English -> Japanese: ACL talks
- Czech -> English: 

## Data
<!-- Details description of the data and links to download -->
The data condition for this task is "constrained with large language models (LLMs)".

### English-to-X
Our English-to-X training data condition follows the one in the offline task.
The list is available [here](https://iwslt.org/2025/offline#training-data-and-data-conditions).
[ACL 60/60 dataset](https://aclanthology.org/2023.iwslt-1.2/) can be the development test set.

### Czech-to-English
Details will be available later.

## Baselines
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->
Baselines will be provided later, including automatic speech segmentation for long-form speech.

## Submission
<!-- Description of expected submission format and submission instructions -->
The evaluation implementation will use the latest [SimulEval](https://github.com/facebookresearch/SimulEval) toolkit.
Participants have two options for the submission:
- Docker image submission; the organizers run the system to compare the computation-aware latency
- System log submission; the computation-aware latency cannot be compared directly but will be reported with its hardware difference

Details will be provided later.

## Evaluation
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

### Metrics
The system's performance will be evaluated in two ways:

- Translation quality metrics:
  - BLEU
  - Additional results using neural metrics (COMET, BLEURT, …)
- Translation latency:
  - Average Lagging
  - Length Adaptive Average Lagging
  - Average Token Delay

For latency measurement, we will contrast computation aware and non computation aware latency metrics.
See the [SimulEval description](https://arxiv.org/abs/2007.16193) for how those metrics are defined.
Note that the definition of average lagging has been modified from the [original definition](https://www.aclweb.org/anthology/P19-1289/) (see section 3.2 in the [SimulEval description](https://arxiv.org/abs/2007.16193)).

### Ranking
The systems will be ranked by the translation quality within the latency constraints.
The detailed constraint for each track will be announced later.

### Human Evaluation
Human evaluation will be conducted for primary submissions.

## Organizers
<!-- List of organizers' names and affiliations -->
- Victor Agostinelli (Oregon State University)
- Lizhong Chen (Oregon State University)
- Sara Papi (FBK)
- Peter Polák (Charles University)
- Katsuhito Sudoh (Nara Women’s University)

## Contact
<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair(s): Katsuhito Sudoh (Nara Women’s University)

Discussion: <iwslt-evaluation-campaign@googlegroups.com>
