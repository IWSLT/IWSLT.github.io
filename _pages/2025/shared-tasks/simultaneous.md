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

### ANNOUNCEMENT
🥁 The test sets for this year are available under [Test Set](#test-set) and submission is **now open**! 🥁

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
- Czech -> English: dedicated dev set (see below)

## Data
<!-- Details description of the data and links to download -->
The data condition for this task is "constrained with large language models (LLMs)". Any model that is open-weights with a permissive license is acceptable for use. In addition, pretrained speech encoders and ASR models may be employed. 

### English-to-X
Our English-to-X training data condition follows the one in the offline task.
The list is available [here](https://iwslt.org/2025/offline#training-data-and-data-conditions).
[ACL 60/60 dataset](https://aclanthology.org/2023.iwslt-1.2/) can be the development test set.
The development data can be found [here](https://aclanthology.org/attachments/2023.iwslt-1.2.dataset.zip) while the yaml files containing the audio information (useful for metrics computation) can be found [here](https://fbk.sharepoint.com/:u:/s/MTUnit/ETIMufobKrxLqfePQCvss8gBJ-2QMsFBJGqfJQEepGETfQ?e=HGwB6x).

### Czech-to-English

Allowed data:

- ParCzech 3.0 (ASR): 
  - Allowed data: parczech-3.0-asr-train-20*.tar.gz
  - https://lindat.mff.cuni.cz/repository/xmlui/handle/11234/1-3631?show=full 
- VoxPopuli (ST)
  - Unlabelled Data: cs_v2
  - translated data Cs -> En data
  - speech-to-speech Cs -> En data
  - https://github.com/facebookresearch/voxpopuli
- Common Voice Corpus 20.0 (ASR)
  - Czech ASR data
  - CV version: 20.0
  - https://commonvoice.mozilla.org/en/datasets
- Czeng 2.0 (MT)
  - https://ufal.mff.cuni.cz/czeng
- OpenSubtitles v2018 (MT)
  - https://opus.nlpl.eu/OpenSubtitles/cs&en/v2018/OpenSubtitles 
- Europarl (MT)
  - https://www.statmt.org/europarl/ 
- MOSEL (transcripts only)
  - automatic transcripts for unlabeled VoxPopuli audio
  - https://huggingface.co/datasets/FBK-MT/mosel 
- Dev Set	(ST)
  - https://drive.google.com/file/d/1-XicsrBQubkGK-kyBIxKO-7JAx94o_KV/view?usp=sharing 

## Test set
The test sets for this year's submission are now available:
- **English -> {German, Chinese, Japanese}**: [IWSLT25Instruct](https://fbk.sharepoint.com/:u:/s/MTUnit/EbwKrywzb5xMuPiDtmItJ_wBHQozf_k8wp3BXayUHrVj0g?e=DXKXWF)
- **Czech -> English**: [IWSLT25](https://drive.google.com/file/d/138KgEoFnNwKHVjh-hCF-JwQttwMyWpzl/view?usp=sharing)

## Baselines
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->

The baselines for each language pair can be found 
[here (GitHub)](https://github.com/pe-trik/iwslt25-baselines/tree/master/experiments/acl6060_dev/de/fixed_segmenter).

## Submission
<!-- Description of expected submission format and submission instructions -->
The evaluation implementation will use the latest [SimulEval](https://github.com/facebookresearch/SimulEval) toolkit.
Participants have two options for the submission:
- *Docker image submission*: the organizers run the system to compare the computation-aware latency
- *System log submission:* the computation-aware latency cannot be compared directly but will be reported with its hardware difference

Systems submitted via docker image are expected to run on a single NVIDIA A100 GPU with 80 GB of HBM. Additionally, participants must include a **README** with instructions on how to run the system for each *track* and *language direction*. To enable communication between evaluators and participants, a point-of-contact and e-mail should be provided in the **README** in case of issues with evaluating the submitted system.

Regardless of the submission type (Docker or log), participants must also submit results on the *development set* (i.e., ACL 60/60 or the dedicated Czech-to-English dev set) to determine the **latency regime** of their submission.

Submission link: [Dropbox Folder](https://www.dropbox.com/request/9tdIploALP4eQBScOYBq)

Participants can update their submissions during the evaluation period. If you have specific questions regarding your submission to the simultaneous shared task, please reach out via e-mail at agostinv@oregonstate.edu.

## Evaluation
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

### Metrics
The system's performance will be evaluated in two ways:

- Quality:
  - BLEU
  - Additional results using neural metrics (COMET, BLEURT, …)
- Latency:
  - [StreamLAAL](https://github.com/hlt-mt/FBK-fairseq/blob/master/fbk_works/STREAMATT_STREAMLAAL.md)

For latency measurement, we will contrast computation aware and non computation aware latency metrics.

### Ranking
The systems will be ranked by the translation quality within the latency constraints, measured by non-computation-aware StreamLAAL.

This year, we have two latency regimes, **low** and **high**. 

The detailed latency constraints (non-computationally-aware StreamLAAL) for each language pair are the following:
- **English-to-German** and **Czech-to-English**: 0-2s (*low*), 2-4s (*high*);
- **English-to-Chinese**: 0-2.5s (*low*), 2.5-4s (*high*);
- **English-to-Japanese**: 0-3.5s (*low*), 3.5s-5s (*high*).

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
