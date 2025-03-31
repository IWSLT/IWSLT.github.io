---
permalink: /2025/instruction-following
title: "Instruction-following Speech Processing track"
toc: true
toc_sticky: true
---

[Last update: Mar. 6, 2025]

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

We release the video, the source audio, and the instructions, and participants submit their outputs. The instructions can be modified by participants to match their system's prompts.
In SQA, questions are provided both in the same language of the speech (English) and in different languages (German, Italian, Chinese) but they always have to be replied to in the same language of the questions (e.g., an Italian question should be replied to in Italian). Questions can also be nonanswerable, in this case, only the answer “Not answerable.” (and the corresponding Italian “Non è possibile rispondere.”, German “Nicht zu beantworten.”, and Chinese “无法回答。” translations) will be considered correct.

The Long Track will process audio files in WAV format that are, on average, 5–6 minutes long. The Short Track will handle the same audio files, but they will be automatically segmented into 15–20 second audio segments, on average, using [SHAS](https://github.com/mt-upc/SHAS).

We provide an example for the Long track, [downloadable here](https://fbk.sharepoint.com/:u:/s/MTUnit/ESlS27NCiRNCj5kBYusDpW4BCkpCPe7cI_5ON75tIAe2hw?e=mOsdQV). ***Participants are also allowed to use it as 1-shot example for their model.***

We also provide useful scripts for parsing inputs and outputs, [downloadble here](https://drive.google.com/file/d/1o0fZ4uC3WbnZ9CVjB2uFoextkI_xTt9v/view?usp=sharing).

**Details on the metrics used for the final ranking will be given after the Evaluation period.**

## Submission

<!-- Description of expected submission format and submission instructions -->

This year, the evaluation will be performed using the Meetween [SPEECHM Evaluation Server](https://iwslt2025.speechm.cloud.cyfronet.pl/).

### General Guidelines

* Multiple run submissions are allowed, but participants must explicitly indicate one PRIMARY run for each track. All other run submissions are treated as CONTRASTIVE runs. In the case that none of the runs is marked as PRIMARY, the latest submission (according to the file time-stamp) for the respective track will be used as the PRIMARY run.

* Once logged in to the [SPEECHM Evaluation Server](https://iwslt2025.speechm.cloud.cyfronet.pl/), the submission process requires participants to create one or more Models for each target language they intend to participate in (English -> English, German, Italian, Chinese).

* For each chosen target language, multiple Models can be created based on the training condition (CONSTRAINED / UNCONSTRAINED) and the submission type (PRIMARY / CONTRASTIVE).

* The created Model(s) must be used to submit runs, which should follow the xml format specified in [the Evaluation section](#evaluation).

* If any issues are identified, the submitted runs can be deleted or replaced with newer runs.

### Submission Steps

Once logged in to [SPEECHM Evaluation Server](https://iwslt2025.speechm.cloud.cyfronet.pl/), proceed through the following two steps. 

#### STEP 1: Create a New Model

<!-- To create a new model, follow these steps: --> 

    1.1 Click on “My submissions” (at the top of the page).
    1.2 Click on “New model” (button at the top right).
    1.3 Create a new model:
        1.3.1 Insert the Model Name using the standardized format:
       
            ${TEAM}_IWSLT25_IF_${TRACK}_${LANGUAGE_PAIR}_${CONDITION}_${SUBMISSION_TYPE}
         
            Where:
            - ${TEAM} → Short name of your team (e.g., KIT)
            - ${TRACK} → Choose from [SHORT, LONG]
            - ${LANGUAGE_PAIR} → Choose from [en-en, en-de, en-it, en-zh]
            - ${CONDITION} → Choose from [constrained, unconstrained]
            - ${SUBMISSION_TYPE} → Choose from [primary, contrastive]

            Example Model Names:
                KIT_IWSLT25_IF_SHORT_en-de_constrained_primary  
                KIT_IWSLT25_IF_SHORT_en-de_constrained_contrastive 

        1.3.2 Insert Description
            Provide a brief but accurate description of your model, including:
                - General approach (e.g., SFM and LLM used, type of integration)
                - Training data used
                - Model architecture
                - Any relevant features characterizing your approach
        1.3.3 Consent Option (optional)
            Consider enabling “Consents” to freely release your submitted system output data.
        1.3.4 Select the Task in which you want to participate
            Choose Instruction-Following Short (IFSHORT) and/or Instruction-Following Long (IFLONG) depending on which track(s) the model participates into as the Task ids in the Compatibility Map.
        1.3.5 Click on “Create Model” (button at the bottom right).

#### STEP 2: Submit the Outputs

    2.1 Go to “My Submissions”.
    2.2 Click on the specific model created in STEP 1 
       (e.g., KIT_IWSLT25_IF_SHORT_en-de_constrained_primary).
    2.3 Click the “IFSHORT/IFLONG Hypotheses” button.
    2.4 Click on "Test input" to download the test input archive (containing audios and XMLs with instructions) for each test set and language.
    2.5 Once you have generated the outputs with your model for the test set, click "Upload hypothesis" for the intended submission:
       ${TESTSET} / ${LANGUAGE_PAIR} (e.g., IWSLT25INSTRUCT / en-de)
    2.6 Upload your submission XML file.

### Manage Your Submission

#### Download or Delete a Submission
    1 Click on “My Submissions”.
    2 Click on the specific model created in STEP 1 
       (e.g., KIT_IWSLT25_IF_SHORT_en-de_constrained_primary).
    3 Click on the “IFSHORT/IFLONG Hypotheses” button.
    4 Use the three-dot menu on the right to:
        - Download the submitted run (hypothesis).
        - Delete the submitted run and confirm.
        
#### Replace a Submission
    1 Delete your existing run.
    2 Submit a new run file (repeat STEP 2 of “Submission steps”).


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
