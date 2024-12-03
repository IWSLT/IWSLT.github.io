---
permalink: /2025/instruction-following
title: "Instruction-following Speech Processing track"
toc: true
toc_sticky: true
---

<!--
Markdown notes: comments can be formed as in this example;
bulleted lines start with a - ;
if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line
-->

[Last update: Dec. 3, 2024]

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
* **TRACK SHORT** (input: automatically segmented audio):
    * **Automatic Speech Recognition (ASR)**: the speech is transcribed into the same language;
    * **Speech-to-text Translation (S2TT)**: the speech is translated into the target language;
    * **Spoken Question Answering (SQA)**: textual questions have to be answered based on the spoken content in the same language and in a language different from the speech (questions and answers are always in the same language);
* **TRACK LONG** (input: long-form audio): 
    * **Automatic Speech Recognition (ASR)**: the speech is transcribed into the same language;
    * **Speech-to-text Translation (S2TT)**: the speech is translated into the target language;
    * **Speech-to-text Summarization (S2TSUM)**: a summary has to be provided from the spoken content in the same language and in a language different from the speech.
All tasks listed for each track are mandatory.

### Languages
English for ASR, monolingual SQA and S2TSUM, and English -> German, Italian, Chinese for S2TT, multilingual SQA and S2TSUM.

**IMPORTANT!** The results can be submitted for some or all language directions.
{: .notice--info}

## Data Conditions

We adopt two conditions. The first is *constrained*, where a pre-defined training setting is adopted, and only a specified pre-trained SFM and LLM architecture can be used. The second is *unconstrained*, with no limitation on pre-trained models and training data.

**IMPORTANT!** The use of the pre-trained SFM and/or LLM is *NOT* mandatory and we also accept submissions with models trained from scratch on the allowed data as well as solutions using only one of the two pre-trained models (either SFM or LLM).
{: .notice--info}

Conditions:
* **Constrained**: Data and models will be provided soon;
* **Unconstrained**: Any model, any data.

<!-- Details description of the data and links to download -->


## Evaluation

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->
Details will be given soon.


## Submission

<!-- Description of expected submission format and submission instructions -->

Details will be given soon.


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
