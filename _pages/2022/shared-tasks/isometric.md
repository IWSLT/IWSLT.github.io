---
permalink: /2022/isometric
title: "Isometric Spoken Language Translation"
---

<!-- the task, the languages, and the type of data -->


## Description
Isometric translation task refers to generating translations similar in length to the source. 
Despite the fast paced progress to improve quality, generating isometric translations is relatively a new problem in 
machine translation (MT) research and application. 
Isometric translation can be applied in a wide range of real world applications such as automatic dubbing 
([to achieve synchrony between source and target language utterances](https://arxiv.org/abs/2001.06785)), 
sub-titling ([to properly fit translations of one or more language in a video frame](https://arxiv.org/abs/2006.01080)), 
simultaneous translation (to translate in consideration of the listener’s cognitive effort ), and 
template preserving translation (i.e. fit the translation in a fixed width block).  
Hence, building MT models that can generate increasingly isometric translation while maintaining the 
translation quality can have a far reaching impact in diverse MT use cases.


## Language Pairs 

For this first isometric translation task, we consider a text-to-text translation track. We focus on three language directions:

1. English-French (En-Fr)
2. English-German (En-De)
3. English-Spanish (En-Es)

These language pairs exhibit different degrees of target to source length ratio in character count, 
for instance target-source length ratio for the training data from 
[MuST-C](https://iwslt.org/2021/offline#allowed-training-data) for En-Fr is 1.11, En-De is 1.12 and En-Es is 1.04. 
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
In this evaluation, LC is applied only for translations with length above 10 characters.


#### System Rating
We plot the systems on XY scatter plot with translation quality on Y axis and length compliance on X axis. 
Systems are ranked based on BERTScore*LC. 


Systems submitted for the above language pairs, will be evaluated on MuST-C (tst-COMMON) and blind test sets 
(see dataset section for more details). In addition to their primary system participants can and are encouraged to submit multiple system runs. 


### Datasets

#### Training Sets

Participants may use text-to-text training data available in the MuST-C v2 offline speech translation corpus 
(please refer to the [offline speech translation task](https://iwslt.org/2021/offline#allowed-training-data)). 
In addition participants can use the latest parallel data for each of the language pairs from 
[WMT](https://www.statmt.org/wmt21/) for their model training. 
Submission information should state what type and amount of data are used for model training. 
Given the amount of data and for a fair assessment, submission is divided into two training data regimes: 


**Constrained task**
* Allowed to use only the textual MuST-C v2 data.

**Unconstrained task**
* Allowed to use the textual MuST-C v2 data
* Allowed to use WMT data 
* Allowed to use pre-trained translation models


#### Test Sets

We will evaluate the submitted systems on a test set and a blind set:

* MuST-C test set (tst-COMMON) which is a public dataset.
* Blind set curated by the organizers for En → French, German, Spanish, which will be released after the task is over.


### System Submission

Participants are asked to submit the output of their system(s), for one or more of the evaluation language pairs. 
In addition to the system outputs, participants are required to submit the performance of their system in terms of 
both the BERTScore and LC metrics. The statistics will be used by the organizers to compare their assessment of 
submitted systems with that of participants. Details of the evaluation script will be made available when the evaluation data is released. 


Submission file should be packaged and named as `isometric_mt_participant-name.tar.gz`.  
Package should be organized per source to target language pair (such as `En-Fr`) and include: 

* `tst-COMMON.SRC`: the source file used for translation 
* `isometric-mt-id.TGT`: the output of participants isometric MT, `id`  is used to distinguish if several approaches/system runs are submitted. 
* `README.md`: should include
    * A brief description of each `*isometric-mt-id` system submitted
    * System performance as computed by the participant
    * Training data condition
    * Institution/contact person

NB: both the source and the MT output should be submitted in a detokenized format.


## Organizers

- Surafel M. Lakew (Amazon AI)
- Prashant Mathur (Amazon AI)
- Natawut Monaikul (Amazon AI)
- Marcello Federico (Amazon AI) 


## Contacts 

Question and Discussion on the task: iwslt-evaluation-campaign@googlegroups.com


<!-- list of names and affiliations -->

<!-- Markdown notes: comments can be formed as above; bulleted lines start with a - ; if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line -->


