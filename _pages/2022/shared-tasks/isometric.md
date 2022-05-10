---
permalink: /2022/isometric
title: "Isometric Spoken Language Translation"
---

<!-- the task, the languages, and the type of data -->

### Updates
- March 25: Deadline for the shared task submission is extended until March 29 (AoE)
- March 25: The blind test set references will be released on March 29 (previously March 25).
- March 11: Blind test set (_only the source_) and evaluation script 
will be released by March 14 on [Isometric SLT repo](https://github.com/amazon-research/isometric-slt). 
See [System Submission](isometric.md#system-submission) section for more details.


## Description
Isometric translation task refers to generating translations similar in length to the source. 
Despite the fast paced progress to improve quality, generating isometric translations is relatively a new problem in 
machine translation (MT) research and application. 
Isometric translation can be applied in a wide range of real world applications such as automatic dubbing 
([to achieve synchrony between source and target speech](https://www.amazon.science/publications/from-speech-to-speech-translation-to-automatic-dubbing)), 
sub-titling ([to fit the video frame](https://arxiv.org/abs/2006.01080)), 
simultaneous speech translation (to control the reading or listening effort), and 
layout constrained translation (i.e. document table or database field). Hence, building MT models that can generate increasingly isometric translation while maintaining the 
translation quality can have a far reaching impact in diverse MT use cases.


*Example translations from an English source to German using a Baseline and an Isometric MT model
demonstrates how the latter can better fit the source length template, while preserving meaning.*


|    Systems    |                                                                                                                                                                       |
|:-------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  __Source__   | *It is actually the true integration of the man and the machine.*                                                                                                     |
|  Baseline MT  | Es ist tatsächlich die wahre Integration von Mensch und Maschine.                                                                                                     |
| Isometric MT  | Es ist die wirkliche Integration von Mensch und Maschine.                                                                                                             |                                                                            |
|  __Source__   | *But still it was a real footrace against the other volunteers to get to the captain in charge to find out what our assignments would be.*                            |
|  Baseline MT  | Aber es war trotzdem ein echtes Rennen gegen die anderen Freiwilligen, um zum verantwortlichen Kapitän zu kommen, um herauszufinden, was unsere Aufgaben sein würden. |
| Isometric MT  | Aber es war ein Wettlauf gegen die anderen Freiwilligen, um zum verantwortlichen Kapitän zu kommen, um unsere Aufgaben herauszufinden.                                |


## Language Pairs 

For this first isometric translation task, we consider a text-to-text translation track. We focus on three language directions:

1. English-French (En-Fr)
2. English-German (En-De)
3. English-Spanish (En-Es)

These language pairs exhibit different degrees of target to source length ratio in character count, 
for instance target-source length ratio for the training data from 
[MuST-C](https://iwslt.org/2021/offline#allowed-training-data) for En-Fr is `1.11`, En-De is `1.12` and En-Es is `1.04`. 
These ratios make it ideal to assess the generalization capability of proposed isometric MT approaches. 
Participants are encouraged to evaluate their approaches using all language pairs.

## Evaluation

Given the requirement of isometric translation, submitted systems are evaluated along two dimensions, translation quality and length compliance. 

#### Translation Quality (TQ)

As the goal in isometric MT is to control the translation length, an ideal translation quality evaluation metric 
should be robust to any length variations in the translations. We considered the n-gram based metric 
[BLEU](https://aclanthology.org/P02-1040.pdf) and embedding based metrics [COMET](https://aclanthology.org/2020.emnlp-main.213.pdf) 
and [BERTScore](https://arxiv.org/abs/1904.09675), and our analysis showed that BERTScore is more robust to length variations 
in the hypotheses as compared to BLEU and COMET, both of which tend to penalize short translations, even if the semantics is preserved. 
Thus, we will use BERTScore to measure translation quality.


#### Length Compliance (LC)

We define length compliance (LC) as the percentage of translations in a given test set falling in a predefined length 
threshold of ±10% of the number of characters in the source sentence. That is, if the source length is 50 characters, 
a length compliant translation is between 45 to 55 characters. We calculate how many translations fall in this bracket 
and report the percentage over a test set. This threshold is motivated by 
[recent finding](https://www.amazon.science/publications/machine-translation-verbosity-control-for-automatic-dubbing), 
that shows that if the translation length stays within a ±10% range, 
it is easier to synchronize source and target speech for use cases like automatic dubbing. 
In this evaluation, LC is applied only for source samples with length above 10 characters.


#### System Ranking
All submissions will be ranked based on a combination of BERTScore and Length Compliance.

Systems submitted for the above language pairs, will be evaluated on MuST-C (`tst-COMMON`) and blind test sets 
(see dataset section for more details). In addition to their primary system, participants are encouraged to submit 
multiple contrastive runs.


## Datasets

### Training Sets

Participants may use text-to-text training data available in the MuST-C v1.2 offline speech translation corpus 
(please refer to the [offline speech translation task](https://iwslt.org/2021/offline#allowed-training-data) for more detail), or 
the dataset is available [here](https://ict.fbk.eu/must-c/). 
In addition participants can use the latest parallel data for each of the language pairs from 
[WMT](https://www.statmt.org/wmt21/) for their model training. 
Submission information should state what type and amount of data are used for model training. 
Depending on the used data, submissions are divided into two training data regimes: 


**Constrained task**
* Can only use the textual MuST-C v1.2 language pair specific parallel data.

**Unconstrained task**
* Can use the textual MuST-C v1.2 data.
* WMT data, multilingual data from other pairs, and pre-trained translation models.


### Test Sets

We will evaluate the submitted systems on a test set and a blind set:

* MuST-C test set (`tst-COMMON`) which is a public dataset.
*  Blind set is curated by the organizers for En → Fr, De, Es. 
Participants will get access to the English source sentences when evaluation starts and references will be released 
after the shared task is completed.


## System Submission

Participants are asked to submit the output of their system(s), for one or more of the evaluation language pairs. 
In addition to the system outputs, participants are required to submit the performance of their system(s) in terms of 
[BERTScore v0.3.11](https://pypi.org/project/bert-score/0.3.11/) (_only for the test set with reference_), 
and LC metric. The statistics will be used by the organizers to compare their assessment of submitted systems with that of participants. 
Details of the evaluation script will be made available when the evaluation data is released. 

Submissions should be emailed to the address `iwslt2022-shared-task@amazon.com` with the  subject line: 
`IWSLT2022 Isometric-SLT Submission`. Submissions should be packed 
in a compressed file with the following naming convention: 
`isometric-slt_[participant-name].tar.gz`. Packages should be organized per 
source-target language pair, per data setting, and per test set (e.g. `./EN-FR/constrained/[mustc-test/blind-test]`).

Each directory should include:
* Source `test.[target]` and system output files for the Isometric SLT blind test set and the MuST-C v1.2, formatted as
    * Plaintext files, one sentence per line, pre-formatted for scoring (detokenized, detruecased)
    * For each system output, one file named `isometric-slt-[id].[target]`, where `id` is used to 
    distinguish if several approaches are submitted. (e.g. `isometric-slt-01.fr`)

* README.md with the following information
    * Brief description of each system submitted, if submitting multiple system indicate which one to use as a primary system for evaluation by the organizers
    * System performance as computed by the participant
    * Training data conditions (constrained, unconstrained)
    * List of the data sources used for training the system
    * Institution and contact person
    * Do you consent to make your submission freely available under MIT license for research purposes and human evaluation? (YES/NO)
* LICENSE 
    * If responding YES for the consent request in the README, include MIT license file (see [sample file](https://opensource.org/licenses/MIT))


In addition to the system outputs, we invite participants to submit a paper describing their system(s) via the 
conference submission page. Check the [system paper submission deadline](https://iwslt.org/2022/#important-dates).  
Unconstrained and constrained systems should be evaluated separately in the system description paper.

_To access blind test set and evaluation scripts, please refer to the [Isometric SLT](https://github.com/amazon-research/isometric-slt) repo._


## FAQ

- Is it allowed to use multilingual data in the constrained task?
  - No, only language pair specific parallel data is allowed for the constrained task. For instance, for En-De, only 
the En-De MuST-C parallel data should be used. If using multilingual data from other language pairs, please consider the
unconstrained task.

## Organizers

- Surafel M. Lakew, AWS AI Labs
- Prashant Mathur, AWS AI Labs
- Yogesh Virkar, AWS AI Labs
- Marcello Federico, AWS AI Labs


## Contacts 

Question and Discussion on the task: iwslt-evaluation-campaign@googlegroups.com


<!-- list of names and affiliations -->

<!-- Markdown notes: comments can be formed as above; bulleted lines start with a - ; if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line -->


