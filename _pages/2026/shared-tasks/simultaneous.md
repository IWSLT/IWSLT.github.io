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

📢 **Announcement**: 
[Latency regimes constraints announced!](#ranking)!

[Update on the list of English-to-X training data](#english-to-x)!

[*Speech-to-Text with Extra Context* Baseline available](#baselines) and Speech-to-Text Baselines coming soon!
{: .notice--info}

## Description
<!-- Description the task, the languages, and the type of data -->

Simultaneous translation (also known as real-time or streaming translation) is the task of generating translations incrementally given partial input only.
Simultaneous systems are typically evaluated with respect to quality and latency.

This year, there is one main track and one sub-track:
- **Speech-to-Text**: simultaneously translating speech in source language into text in target language.
- **Speech-to-Text with Extra Context**: same as above, but the systems can also leverage extra context (e.g., content of the presented ACL paper).

in the following language directions:

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
- Czech -> English: political conference talks

## Training Data and Data Conditions

**We follow the same data conditions as in the offline track (see [here](https://iwslt.org/2026/offline#training-data-and-data-conditions)). Additionally, for the Docker submission, we require the system to be runnable on a single H100 with 80GB of memory.**

<!-- Details description of the data and links to download -->
The data condition for this task is "constrained with large language models (LLMs)".
Any open-weight model with a permissive license is acceptable for use.
In addition, pretrained speech encoders and ASR models may be employed.
We also encourage participants to submit systems leveraging closed-source models/LLMs for evaluation, but such systems will be evaluated separately and will not be eligible for the main ranking.

### English-to-X
Our English-to-X training data condition follows that of the offline, the full list of datasets is presented below. All listed datasets can be automatically transated with the models allowed in the [Constrained with Large Language Models settings](https://iwslt.org/2026/offline#training-data-and-data-conditions).
[MCIF](https://huggingface.co/datasets/FBK-MT/MCIF) is the official development data. [A derived version including audio, references, YAML files with the audio information (useful for metric computation), and PDFs useful for the *speech-to-text with extra context* track) can be found here](https://fbk.sharepoint.com/:u:/s/MTUnit/IQCPqOBxtZXTTKHJrxIK1Om2AYNRrW_Gtj3IfqhtDNab8_A?e=f6vURw).

| Data type | src lang | tgt lang | Training corpus (URL) | Version | Comment
| --- | :---: | :---: | --- | --- | --- |
| speech | en | en | [LibriSpeech ASR corpus](http://www.openslr.org/12/) | v12 | includes translations into *pt*, not to be used
| speech | en | en | [How2](https://github.com/srvk/how2-dataset) | na | |
| speech | en | en | [Mozilla Common Voice](https://datacollective.mozillafoundation.org/datasets?q=english) | v24  | |
| speech | en | en | [Vox Populi](https://github.com/facebookresearch/voxpopuli) | na |  |
| speech-to-text-parallel | en | de, zh | [CoVoST](https://github.com/facebookresearch/covost) | v2 | |
| speech-to-text-parallel | en | de, it | [Europarl-ST](https://www.mllp.upv.es/europarl-st/) | v1.1 | |
| speech-to-text-parallel | en | en | [MOSEL](https://huggingface.co/datasets/FBK-MT/mosel) | v1, v2 | |
| text-parallel | en | de, it | [Europarl](https://www.statmt.org/europarl/v10/training/europarl-v10.de-en.tsv.gz) | v10 | |
| text-parallel | en | de, it, zh | [NewsCommentary](https://data.statmt.org/news-commentary/v18/training) | v18 | |
| text-parallel | en | de, it, zh | [OpenSubtitles](https://opus.nlpl.eu/datasets/OpenSubtitles) | v2024 | |
| text-parallel | en | de | [OpenSubtitles](https://apptek930-my.sharepoint.com/:u:/g/personal/ematusov_apptek_com/ESYWN8_BzeJAmBv4GcRapbsBeLpmLOd699qBc9_WG7Gifw?e=Bk6UWh) | v2018 apptek | partially re-aligned, filtered, with document meta-information on genre |
| text-parallel | en | de, it, zh | [Tatoeba](https://opus.nlpl.eu/datasets/Tatoeba) | v2023-04-12 | |
| text-parallel | en | de | [ELRC-CORDIS_News](https://object.pouta.csc.fi/OPUS-ELRC-CORDIS_News/v1/tmx/de-en.tmx.gz) | v1 | |

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
 - 2025 Dev Set (ST)
	- [https://drive.google.com/file/d/1-XicsrBQubkGK-kyBIxKO-7JAx94o_KV/view?usp=sharing](https://drive.google.com/file/d/1-XicsrBQubkGK-kyBIxKO-7JAx94o_KV/view?usp=sharing)
- 2026 Dev Set (ST)
    - Native speakers with translations and timing info for unsegmented evaluation
    - [http://ufallab.ms.mff.cuni.cz/~polak/iwslt26-cs-dev.zip](http://ufallab.ms.mff.cuni.cz/~polak/iwslt26-cs-dev.zip)

<!-- ## Test set
The test sets for this year's submission are now available:
- **English -> {German, Chinese, Japanese}**: [IWSLT25Instruct](https://fbk.sharepoint.com/:u:/s/MTUnit/EbwKrywzb5xMuPiDtmItJ_wBHQozf_k8wp3BXayUHrVj0g?e=DXKXWF)
- **Czech -> English**: [IWSLT25](https://drive.google.com/file/d/138KgEoFnNwKHVjh-hCF-JwQttwMyWpzl/view?usp=sharing) -->

## Baselines
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->

Last year baselines for each language pair can be found 
[here (GitHub)](https://github.com/pe-trik/iwslt25-baselines/tree/master/experiments/acl6060_dev/de/fixed_segmenter).

Baseline implementations of *Speech-to-Text with Extra Context* can be found [here](https://github.com/owaski/iwslt-2026-baselines).
We will provide other baselines for this year soon.

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
- **(Preferred) Docker Image Submission**: the organizers run the system to compare the computation-aware latency. [Example on how to build a Docker Image can be found in the dedicated SimulStream README.](https://github.com/hlt-mt/simulstream/tree/main/examples/http_docker)
- *System Log Submission:* computation-aware latency cannot be compared directly, but it will be reported along with the hardware used.

Systems submitted via Docker image are expected to run on a single NVIDIA H100 GPU with 80 GB of HBM. Additionally, participants must include a **README** with instructions on how to run the system for each *track* and *language direction*. To enable communication between evaluators and participants, a point of contact and email address should be provided in the **README** in case of issues during evaluation. 

Regardless of the submission type (Docker or log), participants must also submit results on the *development set* (i.e., MCIF or the dedicated Czech-to-English dev set) to determine the **latency regime** of their submission.

Submission link: [Dropbox Folder](https://www.dropbox.com/scl/fo/xh1wt6dij47v4wj7a811a/AGDu3FWu1B7bnTFLJ2lyVtk?rlkey=s400bh5z6b7rr51d4h3sa8yf3&st=3qqzeg9e&dl=0)

Participants will be allowed to update their submissions during the evaluation period.
If you have specific questions regarding your submission to the simultaneous shared task, please reach out via e-mail at agostinv@oregonstate.edu.

## Evaluation
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

### Metrics
The system's performance will be evaluated in two ways:

- Quality:
	- COMET-XL (`Unbabel/XCOMET-XL`)
	- Additional results using other metrics (chrF, BLEURT, …)
- Latency:
    - For the main ranking, we will use [LongYAAL](https://arxiv.org/abs/2509.17349), implemented within [OmniSTEval](https://github.com/pe-trik/OmniSTEval).
	- For consistency with the previous year, we will also include [StreamLAAL](https://github.com/hlt-mt/FBK-fairseq/blob/master/fbk_works/STREAMATT_STREAMLAAL.md).

For latency measurement, we will contrast computation aware and non computation aware latency metrics.

### Ranking
The systems will be ranked by the translation quality within the latency constraints.
System latency regime (low/high) is based on logs with *development set* results.

This year, we have two latency regimes, **low** and **high**. 
The latency constraing are shared across all language pairs, measured by non-computation-aware LongYAAL:
- **Low**: 0-2 seconds,
- **High**: 2-4 seconds.

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

- Peter Polák: [surname]@ufal.mff.cuni.cz
- Siqi Ouyang: siqiouya@andrew.cmu.edu
- Victor Agostinelli: agostinv@oregonstate.edu
- Lizhong Chen: chenliz@oregonstate.edu
