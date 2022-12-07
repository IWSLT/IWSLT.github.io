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

File names for speech recognition outputs should follow the following structure:  <br>
```<participant>.asr.<condition>.<primary/contrastive1/contrastive2>.<src>.txt``` <br>
e.g.,
```gmu.asr.basic.primary.aeb.txt``` for ASR outputs.

The ```<condition>``` tag should be one of the following: 
“contstrained“ or “unconstrained”. Submissions should consist of plaintext files with one sentence per line, following the order of the test set segment file, pre-formatted for scoring (detokenized). 

Information about data and baselines are provided in each section specific to the language-pair. 

## aeb-eng: Tunisian Arabic to English 

### Data
<!-- Details description of the data and links to download -->

### Baselines
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->


### Submission
<!-- Description of expected submission format and submission instructions -->


### Evaluation
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

### Organizers
<!-- List of organizers' names and affiliations -->


## Language-Pair
### Data
<!-- Details description of the data and links to download -->

### Baselines
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->


### Submission
<!-- Description of expected submission format and submission instructions -->


### Evaluation
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

### Organizers
<!-- List of organizers' names and affiliations -->



## Language-Pair
### Data
<!-- Details description of the data and links to download -->

### Baselines
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->


### Submission
<!-- Description of expected submission format and submission instructions -->


### Evaluation
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

### Organizers
<!-- List of organizers' names and affiliations -->



## Language-Pair
### Data
<!-- Details description of the data and links to download -->

### Baselines
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->


### Submission
<!-- Description of expected submission format and submission instructions -->


### Evaluation
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

### Organizers
<!-- List of organizers' names and affiliations -->



## Language-Pair
### Data
<!-- Details description of the data and links to download -->

### Baselines
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->


### Submission
<!-- Description of expected submission format and submission instructions -->


### Evaluation
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

### Organizers
<!-- List of organizers' names and affiliations -->



## Language-Pair
### Data
<!-- Details description of the data and links to download -->

### Baselines
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->


### Submission
<!-- Description of expected submission format and submission instructions -->


### Evaluation
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

### Organizers
<!-- List of organizers' names and affiliations -->


## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair:   
Discussion: <iwslt-evaluation-campaign@googlegroups.com>
