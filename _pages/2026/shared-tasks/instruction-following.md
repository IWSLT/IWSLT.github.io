---
permalink: /2026/instruction-following
title: "Instruction Following track"
toc: true
toc_sticky: true
---

📢 **Announcement**: [Submissions are now open!](#submission)
{: .notice--info}

## Description

### Motivation
Large language models (LLMs) have demonstrated the capability of performing several NLP tasks without the need for building dedicated models, offering a single solution for many applications. While solely processing text in their initial stage, LLMs are now being enhanced by shifting towards the integration of other modalities, like vision and audio. In this scenario, the emerging paradigm of creating a unique architecture from speech foundation models (SFMs) and LLMs is gaining traction to combine the best of both worlds: the ability to process spoken language inputs with the always-evolving language knowledge of the LLMs. For this reason, and given the success of the first edition, we propose the second edition of the Instruction Following (IF) task, which is aimed at testing general models for the speech modality, which better reflects the current trends in the research community.

### Tasks Description
Participants are asked to build a model capable to perform, depending on the track, the following tasks:
* **SHORT TRACK** (input: automatically segmented audio):
    * **Automatic Speech Recognition (ASR)**: the speech is transcribed into the same language;
    * **Speech-to-text Translation (S2TT)**: the speech is translated into the target language;
    * **Spoken Question Answering (SQA)**: textual questions have to be answered based on the spoken content in the same language and in a language different from the speech (questions and answers are always in the same language);
    * **[NEW THIS YEAR!] Surprisal**: a task that is unknown at submission time but doable through in-context learning abilities of SpeechLLMs.  
* **LONG TRACK** (input: long-form audio): 
    * **All the short-form tasks, including the Surprisal**;
    * **Speech-to-text Summarization (S2TSUM)**: a summary has to be provided from the spoken content in the same language and in a language different from the speech;
    * **[NEW THIS YEAR!] Audio Chaptering (ACHAP)**: the spoken content has to be segmented into coherent sections, each labeled with a concise title summarizing its topic.

All tasks listed for each track are mandatory.

### Languages
English for ASR, monolingual SQA, ACHAP, and S2TSUM, and English -> German, Italian, Chinese for S2TT, multilingual SQA, ACHAP, and S2TSUM. English -> German, Chinese for the SURPRISAL.

**IMPORTANT!** The results can be submitted for some or all language directions.
{: .notice--info}

## Data Conditions
We adopt two conditions. The first is *constrained*, where a pre-defined training setting is adopted, and only a specified pre-trained SFM and LLM architecture can be used. The second is *unconstrained*, with no limitation on pre-trained models and training data.

### Constrained
Participants are allowed to use the SFM and LLM provided below, and training the system on the following data.
* **Pre-trained Models**:
    * *SFM*: [facebook/seamless-m4t-v2-large](https://huggingface.co/facebook/seamless-m4t-v2-large)
    * *LLM*: [Qwen/Qwen3-4B-Instruct-2507](https://huggingface.co/Qwen/Qwen3-4B-Instruct-2507)
* **Training Data**:
    * *ASR/S2TT*: [EuroParlST](https://www.mllp.upv.es/europarl-st/) en-it,de; [CoVoST2](https://github.com/facebookresearch/covost) en-zh,de; [GigaST](https://st-benchmark.github.io/resources/GigaST.html) en-de,zh;
    * *SQA*: [LibriSQA](https://github.com/ZihanZhaoSJTU/LibriSQA)
    * *S2TSUM*: [NUTSHELL](https://huggingface.co/datasets/maikezu/abstract-gen-acl-17-22)
    * *ACHAP*: [YTSeg](https://huggingface.co/datasets/retkowski/ytseg)
* **Validation Data**:
    * *ASR/S2TT/SQA/S2TSUM*: [MCIF](https://huggingface.co/datasets/FBK-MT/MCIF) (including the [IWSLT25 Instruction Following test set](https://huggingface.co/datasets/FBK-MT/MCIF/tree/IWSLT2025))
    * *ACHAP*: [YTSeg](https://huggingface.co/datasets/retkowski/ytseg)
 
We do not provide any training data for SQA, ACHAP, and S2TSUM in languages different from the source speech.

**IMPORTANT!** The use of the pre-trained SFM and/or LLM is *NOT* mandatory and we also accept submissions with models trained from scratch on the allowed data as well as solutions using only one of the two pre-trained models (either SFM or LLM).
{: .notice--info}

### Unconstrained 
Any model, any data.


## Evaluation
We release the video, the source audio, and the instructions, and participants submit their outputs. The instructions can be modified by participants to match their system's prompts.
For cross-lingual tasks, the output language should be the one used in the prompt. For instance, in SQA, questions are provided both in the same language of the speech (English) and in different languages (German, Italian, Chinese) but they always have to be replied to in the same language of the questions (e.g., an Italian question should be replied to in Italian). Questions can also be nonanswerable, in this case, only the answer “Not answerable.” (and the corresponding Italian “Non è possibile rispondere.”, German “Nicht zu beantworten.”, and Chinese “无法回答。” translations) will be considered correct.

The Long Track will process audio files in WAV format that are, on average, 6 minutes long. The Short Track will handle the same audio files, but they will be automatically segmented into 15–20 second audio segments, on average, using [SHAS](https://github.com/mt-upc/SHAS).

An example of the **input format** for the Long track is [downloadable here](https://fbk.sharepoint.com/:u:/s/MTUnit/IQDmbjFqnGRqSL7Xqd59slNvAbGzVDYsjpJ12_w9J27CwNE?e=JfLCgY). *Participants are also allowed to use it as 1-shot example for their model.*

The expected **output format** will be same of MCIF, please see the [GitHub repository](https://github.com/hlt-mt/mcif?tab=readme-ov-file#%EF%B8%8F-usage). An example of the **output format** (including ACHAP) for the Long track is [downloadable here](https://fbk.sharepoint.com/:u:/s/MTUnit/IQBBWCyVypv9QYag5rzdYp8YARIQGaKrd1W2bSAvaLIZXyw?e=7pNoir).

We also provide useful scripts for parsing inputs and outputs, [downloadble here](https://drive.google.com/file/d/1o0fZ4uC3WbnZ9CVjB2uFoextkI_xTt9v/view?usp=sharing).

Evaluation is conducted using the MCIF [GitHub repository](https://github.com/hlt-mt/mcif) for all tasks.  

## Submission

The submission will be performed using the [Meetween SPEECHM Evaluation Server](https://speechm.cloud.cyfronet.pl/). 

### General Guidelines

* Create **a single instance** for each model, report the required information, including the training condition (constrained/unconstrained), and upload the outputs for one or more target languages (English -> English, German, Italian, Chinese). Participants must provide the information required in the “Description” field, if no information is provided, the most permissive condition will be considered (e.g., unconstrained over constrained or the usage of all training data available over using CoVoST2 and/or GigaST only)

* Multiple submissions are allowed, but participants must explicitly indicate one PRIMARY run for each track. All other run submissions are treated as CONTRASTIVE runs. In the case that none of the runs is marked as PRIMARY, the latest submission (according to the file timestamp) for the respective track will be used as the PRIMARY run.

* Outputs should follow the xml format specified in the [Evaluation section](#evaluation).

* If any issues are identified, the submitted outputs can be deleted or replaced with newer ones.

### Submission Steps

Available after the Evaluation period start date.

Once logged in to [SPEECHM Evaluation Server](https://speechm.cloud.cyfronet.pl/), proceed through the following steps. 

#### STEP 1: Download Test Data
1. Click on `Test sets` (at the top of the page), and select either `IFLONG26` or `IFSHORT26` depending on the track (long and short, respectively). Alternatively, [directly access the IF task page](https://speechm.cloud.cyfronet.pl/0000005/tasks/25).
2. Download the test set (containing audios and XMLs with instructions) of the selected target language.

#### STEP 2: Create a New Model
1. Click on `My submissions` (at the top of the page) and on `New model` (button at the top right).
2. Create a new model:
    - Insert the `Name` using the standardized format:
    ```
        ${TEAM}_IWSLT26_IF_${TRACK}_${CONDITION}_${SUBMISSION_TYPE}
        
        Where:
        - ${TEAM} → Short name of your team (e.g., KIT)
        - ${TRACK} → Choose from [SHORT, LONG]
        - ${CONDITION} → Choose from [constrained, unconstrained]
        - ${SUBMISSION_TYPE} → Choose from [primary, contrastive]

        Example Model Names:
            KIT_IWSLT26_IF_SHORT_constrained_primary  
            KIT_IWSLT26_IF_SHORT_constrained_contrastive1 
            KIT_IWSLT26_IF_SHORT_constrained_contrastive2 
    ```

    - Insert `Description` by including:
    ```console
        - Data conditions: constrained/unconstrained
        - [if constrained] Training data: with CoVoST2/with GigaST/with CoVoST2 and GigaST/other combination (specify)
        - Model architecture: cascade/direct
        - Any other relevant features characterizing your approach:
    ```

    - Select `Task ids` by checking `Instruction Following (IF)`
    - Check `Consent` (optional) to freely release your submitted system output data, including for human evaluation purposes
    - Click on `Create Model` (button at the bottom right)

#### STEP 3: Submit the Outputs

- Click on `My submissions` 
- Click on the model created in STEP 2 (e.g., `KIT_IWSLT26_IF_SHORT_constrained_primary`)
- Click on `IF Hypotheses`, close to `Model info`
- Upload your XML file by clicking on the `Upload hypothesis` button corresponding to the language pair(s) you want to participate in

### Manage Your Model

#### Download or Delete the Hypothesis
- Click on `My submissions`
- Click on the model created in STEP 2 (e.g., `KIT_IWSLT26_IF_SHORT_constrained_primary`)
- Click on `IF Hypotheses`, close to `Model info`
- Use the three-dot menu on the right to either `Download` or `Delete` the submitted hypothesis
        
#### Delete a Model
You can, at any time, change the name and description of your model by clicking on its name under the `My submissions` panel. If you want to delete a model (i.e., not replacing or modifying it, but completely removing it from participating models), [please contact the task's organizers](#contact).

## Organizers
* Sara Papi, Fondazione Bruno Kessler
* Luisa Bentivogli, Fondazione Bruno Kessler
* Marco Gaido, Fondazione Bruno Kessler
* Danni Liu, Karlsruhe Institute of Technology
* Fabian Retkowski, Karlsruhe Institute of Technology
* Beatrice Savoldi, Fondazione Bruno Kessler
* Maike Züfle, Karlsruhe Institute of Technology

## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair(s): Sara Papi <sara95papi@gmail.com>;  
Discussion: <iwslt-evaluation-campaign@googlegroups.com>