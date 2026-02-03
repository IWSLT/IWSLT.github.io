---
permalink: /2026/simultaneous
title: "Simultaneous ST track"
toc: true
toc_sticky: true
---

<!--
Markdown notes: comments can be formed as in this example;
bulleted lines start with a - ;
if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line
-->


**📢 Announcement 📢: Baselines coming soon 🚀**

Baseline implementations and links will be published here soon.

## Description
<!-- Description the task, the languages, and the type of data -->

Simultaneous translation (also known as real-time or streaming translation) is the task of generating translations incrementally given partial input only.
Simultaneous systems are typically evaluated with respect to quality and latency.

There will be one main track and one sub-track:
- **Speech-to-Text**: simultaneously translating speech in source language into text in target language.
- **Speech-to-Text with Extra Context**: same as above, but the systems can also leverage extra context (e.g., content of the presented ACL paper).

in the following language directions (more details will be made available soon):

- English -> German
- English -> Chinese
- English -> Italian
- Czech -> English

We have three focuses this year:
- **long-form speech**: our evaluation will be conducted on *unsegmented* speech
- **large language models**: participants are allowed to use LLMs (details will be announced later)
- **extra context**: a sub-track that allows participants to use additional context. This year, we provide the ACL paper PDFs associated with the ACL talks being translated as extra context.

The test set domains are the subsets of the ones of the offline track:
- English -> German: ACL talks and accent challenge data
- English -> Chinese: ACL talks
- English -> Italian: ACL talks
- Czech -> English: dedicated dev set (will be provided soon)

## Training Data and Data Conditions

**We follow similar data conditions as in the offline track (see [here](https://iwslt.org/2026/offline#training-data-and-data-conditions)). Additionally, for the constrained submission we require the system to be runnable on a single H100 with 80GB of memory.**

<!-- Details description of the data and links to download -->
The data condition for this task is "constrained with large language models (LLMs)".
Any open-weight model with a permissive license is acceptable for use.
In addition, pretrained speech encoders and ASR models may be employed.
We also encourage participants to submit systems leveraging closed-source models/LLMs for evaluation, but such systems will be evaluated separately and will not be eligible for the main ranking.

### English-to-X
Our English-to-X training data condition follows that of the offline task.
The list is available [here](https://iwslt.org/2026/offline#training-data-and-data-conditions).
[ACL 60/60 dataset](https://aclanthology.org/2023.iwslt-1.2/) can be used as the development set.
The development data can be found [here](https://aclanthology.org/attachments/2023.iwslt-1.2.dataset.zip), while the YAML files containing the audio information (useful for metric computation) can be found [here](https://fbk.sharepoint.com/:u:/s/MTUnit/ETIMufobKrxLqfePQCvss8gBJ-2QMsFBJGqfJQEepGETfQ?e=HGwB6x) and the ACL paper PDFs (useful for the *speech-to-text with extra context* track) can be found [here](https://drive.google.com/file/d/15ZGQ2odmXeDbEVgl0h8YaNoqWcbdxmcR/view?usp=sharing).

### Czech-to-English

- ParCzech 3.0 (ASR): 
	- Allowed data: parczech-3.0-asr-train-20*.tar.gz
	- https://lindat.mff.cuni.cz/repository/xmlui/handle/11234/1-3631?show=full 
- VoxPopuli (ST)
	- Unlabeled data: cs_v2
	- Translated data (cs → en)
	- Speech-to-speech data (cs → en)
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
<!-- - 2025 Dev Set (ST)
	- https://drive.google.com/file/d/1-XicsrBQubkGK-kyBIxKO-7JAx94o_KV/view?usp=sharing  -->

<!-- ## Test set
The test sets for this year's submission are now available:
- **English -> {German, Chinese, Japanese}**: [IWSLT25Instruct](https://fbk.sharepoint.com/:u:/s/MTUnit/EbwKrywzb5xMuPiDtmItJ_wBHQozf_k8wp3BXayUHrVj0g?e=DXKXWF)
- **Czech -> English**: [IWSLT25](https://drive.google.com/file/d/138KgEoFnNwKHVjh-hCF-JwQttwMyWpzl/view?usp=sharing) -->

## Baselines
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->

Last year baselines for each language pair can be found 
[here (GitHub)](https://github.com/pe-trik/iwslt25-baselines/tree/master/experiments/acl6060_dev/de/fixed_segmenter).

We will provide updated baselines for this year soon.

## Submission
<!-- Description of expected submission format and submission instructions -->


The evaluation implementation will use the latest [SimulStream](https://github.com/hlt-mt/simulstream) toolkit (see paper [here](https://arxiv.org/abs/2512.17648)).

For the **Speech-to-Text with Extra Context** track, participants will also be given a file containing the paths to the PDF files of the ACL papers like this:
```
/path/to/paper1.pdf
/path/to/paper2.pdf
/path/to/paper3.pdf
```
Participants are allowed to preprocess the PDF files before running the simultaneous translation system.

Participants have two options for the submission:
- **(Preferred) Docker Image Submission**: the organizers run the system to compare the computation-aware latency.
- *System Log Submission:* computation-aware latency cannot be compared directly, but it will be reported along with the hardware used.

Systems submitted via Docker image are expected to run on a single NVIDIA H100 GPU with 80 GB of HBM. Additionally, participants must include a **README** with instructions on how to run the system for each *track* and *language direction*. To enable communication between evaluators and participants, a point of contact and email address should be provided in the **README** in case of issues during evaluation. Docker images should support the `linux/arm64` architecture, specified during build via the `--platform` flag.

Regardless of the submission type (Docker or log), participants must also submit results on the *development set* (i.e., ACL 60/60 or the dedicated Czech-to-English dev set) to determine the **latency regime** of their submission.

<!-- Submission link: [Dropbox Folder](https://www.dropbox.com/request/9tdIploALP4eQBScOYBq) -->

Participants will be allowed to update their submissions during the evaluation period.
If you have specific questions regarding your submission to the simultaneous shared task, please reach out via e-mail at agostinv@oregonstate.edu.

## Evaluation
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

### Metrics
The system's performance will be evaluated in two ways:

- Quality:
	- COMET
	- Additional results using other metrics (chrF, BLEURT, …)
- Latency:
    - For the main ranking, we will use [LongYAAL](https://arxiv.org/abs/2509.17349), see implementation [here](https://github.com/pe-trik/softsegmenter).
	- For consistency with the previous year, we will also include [StreamLAAL](https://github.com/hlt-mt/FBK-fairseq/blob/master/fbk_works/STREAMATT_STREAMLAAL.md).

For latency measurement, we will contrast computation aware and non computation aware latency metrics.

### Ranking
The systems will be ranked by the translation quality within the latency constraints, measured by non-computation-aware LongYAAL.
System latency regime (low/high) is based on logs with *development set* results.

This year, we have two latency regimes, **low** and **high**. 
The detailed latency constraints (non-computationally-aware LongYAAL) for each language pair will be announced soon.

<!-- The detailed latency constraints (non-computationally-aware LongYAAL) for each language pair are the following: 
- **English-to-German** and **Czech-to-English**: 0-2s (*low*), 2-4s (*high*);
- **English-to-Chinese**: 0-2.5s (*low*), 2.5-4s (*high*);
- **English-to-Japanese**: 0-3.5s (*low*), 3.5s-5s (*high*). -->

### Human Evaluation
Human evaluation will be conducted for primary submissions.

## Organizers
<!-- List of organizers' names and affiliations -->
- Peter Polák (chair, Charles University)
- Siqi Ouyang (co-chair for the Context Subtrack, Carnegie Mellon University)
- Victor Agostinelli (Oregon State University)
- Ondřej Bojar (Charles University)
- Lizhong Chen (Oregon State University)
- David Javorský (Charles University)
- Nam Hoang Luu (Charles University)
- Sara Papi (FBK)
- Katsuhito Sudoh (Nara Women’s University)

## Contact
<!-- Add chair(s) and their contact info, as well as standard google group -->
Discussion: <iwslt-evaluation-campaign@googlegroups.com>

- Peter Polák: surname@ufal.mff.cuni.cz
- Siqi Ouyang: siqiouya@andrew.cmu.edu
- Victor Agostinelli: agostinv@oregonstate.edu
- Lizhong Chen: chenliz@oregonstate.edu
