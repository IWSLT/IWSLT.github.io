---
permalink: /2023/low-resource
title: "Dialectal and Low-resource track"
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

The goal of this shared task is to benchmark and promote speech translation technology for a diverse range of dialects and low-resource languages.
While significant research progress has been demonstrated recently on popular datasets, many of the world's dialects and low-resource languages lack the parallel data at scale needed for standard supervised learning.
We will likely require creative approaches in leveraging disparate resources.

For example, to translate dialectal speech such as Tunisian Arabic, one may leverage existing speech and text resources in Modern Standard Arabic. 
Or, to translate a low-resource language such as Tamasheq, one may need to leverage word-level translation resources and raw audio. 

We will provide training and evaluation data for a range of language-pairs. 
Participants are free to participate in any number of language-pairs in this track. 
We encourage both dedicated systems that are designed to a single language-pair, as well as general recipes aimed at improving speech translation broadly for a wide typology of languages. 


## General Information for All Language-Pairs

The submission format will be standardized across all language-pairs.
Participants can submit systems under two conditions:
* Constrained condition: systems are trained only on the dataset provided by the organizers
* Unconstrained condition: systems can be trained with any resource, including pre-trained models. 

File names for translation outputs should follow the following structure:  <br>
```<participant>.st.<condition>.<primary/contrastive1/contrastive2>.<src>-<tgt>.txt``` <br>
e.g.,
```gmu.st.basic.primary.aeb-eng.txt``` for translation outputs. The language pair is indicated by ```<src>-<tgt>```. 

File names for speech recognition outputs (if applicable) should follow the following structure:  <br>
```<participant>.asr.<condition>.<primary/contrastive1/contrastive2>.<src>.txt``` <br>
e.g.,
```gmu.asr.basic.primary.aeb.txt``` for ASR outputs.

Submissions should consist of plaintext files with one sentence per line, following the order of the test set segment file, pre-formatted for scoring (detokenized). 
The ```<condition>``` tag should be one of the following: 
“constrained“ or “unconstrained”. 
If multiple outputs are submitted for one test set, one system must be explicitly marked as primary.
We ask that the participants include a (very) short system desciption in the submission email.

Information about data and baselines are provided in each section specific to the language-pair. 

## aeb-eng: Tunisian Arabic to English 

### Data
<!-- Details description of the data and links to download -->

The aeb-eng training data is the same as the one used in the IWSLT 2022 Dialectal Speech Translation track in the previous year: <a href="https://iwslt.org/2022/dialect">https://iwslt.org/2022/dialect</a>. 
Please follow the train/dev/test1 split instructions according to the aforementioned IWSLT 2022 webpage.

In 2022 we had three conditions: basic, dialect adaptation, and unconstrained. 
The basic condition in 2022 corresponds to the "constrained" condition in 2023; the dialect adaptation and unconstrained conditions in 2022 will be referred to as the "unconstrained" condition in 2023.
A new test set (<it>test3</it>) will be provided as part of this 2023 evaluation. 

IWSLT participants may obtain the Tunisian-English speech translation data for no cost from LDC. Please sign this [form](https://www.cs.jhu.edu/~kevinduh/j/iwslt23/IWSLT_2023_LDC_Evaluation_Agreement) and email it to ldc@ldc.upenn.edu. This 3-way parallel data corresponds to 160 hours and 200k lines worth of aligned audio in Tunisian speech, Tunisian transcripts, and English translations.
All datasets have been manually segmented at the utterance level.

### Baselines
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->

Feel free to build upon the baseline models in ESPnet provided by <a href="https://shinjiwlab.github.io">CMU WAVLab</a>. Here are the recipes for the basic condition: <a href="https://github.com/espnet/espnet/blob/master/egs2/iwslt22_dialect/asr1/RESULTS.md">ASR model</a> and
<a href="https://github.com/espnet/espnet/blob/master/egs2/iwslt22_dialect/st1/RESULTS.md">ST model</a>. The models are also downloadable from Huggingface.

If you would like to share your baseline models here for other colleagues to use during the evaluation campaign, please contact Kevin Duh.

You may also find it helpful to refer to the system description papers in 2022 from <a href="https://aclanthology.org/2022.iwslt-1.27/">CMU</a>, <a href="https://aclanthology.org/2022.iwslt-1.29/">JHU</a>, and <a href="https://aclanthology.org/2022.iwslt-1.28/">ON-TRAC</a>. 

### Submission/Evaluation
<!-- Description of expected submission format and submission instructions -->
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

Please submit your files as ```<participant>.st.<condition>.<primary/contrastive1/contrastive2>.aeb-eng.txt```.
The evaluation set will include a `segments.txt` (one utterance per line, with file-ids and start/end times) and the submission of translation outputs should be ordered in the same way. 

 Submissions should be compressed in a single .tar.gz file and emailed to x@cs.jhu.edu (where x=kevinduh), with "IWSLT 2023 Dialectal and Low-Resource Task Submission" in the title; you will receive a confirmation of receipt within a day. 

The official BLEU score will use lower-case and no punctuation, following the "norm" files in the setup [instructions](https://github.com/kevinduh/iwslt22-dialect). 

### Organizers
<!-- List of organizers' names and affiliations -->

- Kevin Duh (Johns Hopkins University)
- Paul McNamee (Johns Hopkins University)
- Kenton Murray (Johns Hopkins University)


## gle-eng: Irish to English

### Data
<!-- Details description of the data and links to download -->

### Baselines
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->


### Submission/Evaluation
<!-- Description of expected submission format and submission instructions -->
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

### Organizers
<!-- List of organizers' names and affiliations -->



## mar-eng: Marathi to English 

### Data
<!-- Details description of the data and links to download -->

### Baselines
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->


### Submission/Evaluation
<!-- Description of expected submission format and submission instructions -->
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

### Organizers
<!-- List of organizers' names and affiliations -->



## mlt-eng: Maltese to English
### Data
<!-- Details description of the data and links to download -->

### Baselines
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->


### Submission/Evaluation
<!-- Description of expected submission format and submission instructions -->
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

### Organizers
<!-- List of organizers' names and affiliations -->



## pus-fra: Pashto to French 
Pashto is spoken by approximately forty to sixty million people in the world. It is particularly spoken by the Pashtun people in the south, east and southwest of the country, as well as in the north and northwest Pakistan but also in Iran, Tajikistan and India (Uttar Pradesh and Cashmere) and one of the two official languages of Afghanistan.

### Data
<!-- Details description of the data and links to download -->
This corpus is a collection of 103 hours of Broadcast News with transcriptions in Pashto and translations in French text.

Participants can build systems for evaluation in any of these conditions:

*Basic condition:* train on Pashto-to-French distributed dataset only.
*Constrained condition:* participants may use only public resources for Pashto and French. Multilingual models beyond Pashto and French are allowed.

### Obtaining data
IWSLT participants may obtain the Pashto-French speech translation data for no cost from ELRA. Please sign this form and email it to mapelli@elda.org.

### Baseline Models
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->
Here are the recipes for the basic conditions. Baseline models are also available with Pashto-to-French dataset.


### Submission/Evaluation
<!-- Description of expected submission format and submission instructions -->
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

### Organizers
<!-- List of organizers' names and affiliations -->
Souhir Gahbiche (Airbus, France)
Khalid Choukri (ELRA, France)

## tmh-fra: Tamasheq to French

### Data
<!-- Details description of the data and links to download -->

### Baselines
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->


### Submission/Evaluation
<!-- Description of expected submission format and submission instructions -->
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

### Organizers
<!-- List of organizers' names and affiliations -->


## yum-spa: Quechua to Spanish 

### Data
<!-- Details description of the data and links to download -->

### Baselines
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->


### Submission/Evaluation
<!-- Description of expected submission format and submission instructions -->
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

### Organizers
<!-- List of organizers' names and affiliations -->



## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Although each language-pair is managed by different organizers, please use this common forum for all questions and comments: <iwslt-evaluation-campaign@googlegroups.com>
