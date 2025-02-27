---
permalink: /2025/instruction-following
title: "Instruction-following Speech Processing track"
toc: true
toc_sticky: true
---

[Last update: Jan. 27, 2025]

## Description

<!-- Description the task, the languages, and the type of data -->
### Motivation
*Large language models (LLMs) have demonstrated the capability of performing several NLP tasks without the need for building 
dedicated models, offering a single solution for many applications.
While solely processing text in their initial stage, LLMs are now being enhanced by integrating 
other modalities, like vision and audio. 
In this scenario, the emerging paradigm of creating a unique architecture from speech foundation models (SFMs) and LLMs 
is gaining traction to combine the best of both worlds: the ability to process spoken language inputs with the 
always-evolving language knowledge of the LLMs. 
For this reason, this year, we introduce the first shared task at IWSLT aimed at testing general and universal models 
for the speech modality.*

### Tasks Description
Participants are asked to build a model capable to perform, depending on the track, the following tasks:
* **SHORT TRACK** (input: automatically segmented audio):
    * **Automatic Speech Recognition (ASR)**: the speech is transcribed into the same language;
    * **Speech-to-text Translation (S2TT)**: the speech is translated into the target language;
    * **Spoken Question Answering (SQA)**: textual questions have to be answered based on the spoken content in the same language and in a language different from the speech (questions and answers are always in the same language);
* **LONG TRACK** (input: long-form audio): 
    * **Automatic Speech Recognition (ASR)**: the speech is transcribed into the same language;
    * **Speech-to-text Translation (S2TT)**: the speech is translated into the target language;
    * **Spoken Question Answering (SQA)**: textual questions have to be answered based on the spoken content in the same language and in a language different from the speech (questions and answers are always in the same language);
    * **Speech-to-text Summarization (S2TSUM)**: a summary has to be provided from the spoken content in the same language and in a language different from the speech.
All tasks listed for each track are mandatory.

### Languages
English for ASR, monolingual SQA and S2TSUM, and English -> German, Italian, Chinese for S2TT, multilingual SQA and S2TSUM.

**IMPORTANT!** The results can be submitted for some or all language directions.
{: .notice--info}

## Data Conditions
<!-- Details description of the data and links to download -->

We adopt two conditions. The first is *constrained*, where a pre-defined training setting is adopted, and only a specified pre-trained SFM and LLM architecture can be used. The second is *unconstrained*, with no limitation on pre-trained models and training data.

### Constrained
Participants are allowed to use the SFM and LLM provided below, and training the system on the following data.
* **Pre-trained Models**:
    * *SFM*: [facebook/seamless-m4t-v2-large](https://huggingface.co/facebook/seamless-m4t-v2-large)
    * *LLM*: [meta-llama/Llama-3.1-8B-Instruct](https://huggingface.co/meta-llama/Llama-3.1-8B-Instruct)
* **Training Data**:
    * *ASR/S2TT*: [EuroParlST](https://www.mllp.upv.es/europarl-st/) en-it,de; [CoVoST2](https://github.com/facebookresearch/covost) en-zh,de;
    * *SQA*: [Spoken-SQuAD](https://github.com/Chia-Hsuan-Lee/Spoken-SQuAD);
    * *S2TSUM*: [IWSLT-IT2025 ACL abstracts (from 2017-2022)](https://huggingface.co/datasets/maikezu/abstract-gen-acl-17-22)
* **Validation Data**:
    * *ACL 60/60*: [downloadble here](https://aclanthology.org/attachments/2023.iwslt-1.2.dataset.zip), it contains transcripts, translations, and summaries (abstracts) can be easily retrieved using the video ID.
 
We do not provide any training data for SQA (questions and answers) and S2TSUM (summaries) in languages different from the source speech.

**IMPORTANT!** The use of the pre-trained SFM and/or LLM is *NOT* mandatory and we also accept submissions with models trained from scratch on the allowed data as well as solutions using only one of the two pre-trained models (either SFM or LLM).
{: .notice--info}

### Unconstrained 
Any model, any data.

## Evaluation
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

We release the video, the source audio, and the instructions, and participants submit their outputs. 
In SQA, questions are provided both in the same language of the speech (English) and in different languages (German, Italian, Chinese) but they always have to be replied to in the same language of the questions (e.g., an Italian question should be replied to in Italian). Questions can also be nonanswerable, in this case, only the answer “Not answerable.” will be considered correct.

The Long Track will process audio files in WAV format that are, on average, 5–6 minutes long. The Short Track will handle the same audio files, but they will be automatically segmented into 15–20 second audio segments, on average, using [SHAS](https://github.com/mt-upc/SHAS).

We provide an example for the Long track, [downloadable here](https://fbk.sharepoint.com/:u:/s/MTUnit/ESlS27NCiRNCj5kBYusDpW4BCkpCPe7cI_5ON75tIAe2hw?e=mOsdQV). ***Participants are also allowed to use it as 1-shot example for their model.***

We also provide useful scripts for parsing inputs and outputs, [downloadble here](https://drive.google.com/file/d/1o0fZ4uC3WbnZ9CVjB2uFoextkI_xTt9v/view?usp=sharing).

**Details on the metrics used for the final ranking will be given after the Evaluation period.**

## Submission

<!-- Description of expected submission format and submission instructions -->

**More details will be given soon.**


## Organizers

<!-- List of organizers' names and affiliations -->
* Sara Papi, Fondazione Bruno Kessler
* Luisa Bentivogli, Fondazione Bruno Kessler
* Marco Gaido, Fondazione Bruno Kessler
* Danni Liu, Karlsruhe Institute of Technology
* Beatrice Savoldi, Fondazione Bruno Kessler
* Maike Züfle, Karlsruhe Institute of Technology

## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair(s): Sara Papi (<spapi@fbk.eu>)

Discussion: <iwslt-evaluation-campaign@googlegroups.com>
