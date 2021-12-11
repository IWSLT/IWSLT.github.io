---
permalink: /2022/formality
title: "Special Task on Formality Control for Spoken Language Translation"
---

## Overview

Machine translation (MT) models typically return one single translation for each input segment. This means that when the input segment is ambiguous, the model must choose a translation from among various valid options, without regard to the intended use case or target audience. 

Specific problems can arise for spoken language translation from English into languages that have multiple levels of formality expressed through honorifics or “[grammatical register](http://www.qt21.eu/mqm-definition/issues-list-2015-12-30.html#grammatical-register)”. For example, the sentence ‘*Are you sure?’* can have two possible correct translations in German: ‘Sind Sie sich sicher?’ for the formal register and ‘Bist du dir sicher?’ for the informal one. For applications of spoken language translation, leaving the model to choose between different valid translation options can lead to translations that are inconsistent or use an inappropriate formality level, which can be perceived as rude or jarring for speakers from certain cultures and for certain use cases (e.g. customer support chat). 

How formality distinctions are expressed grammatically and lexically can vary widely by language. In many Indo-European languages (e.g., German, Hindi, Italian, Russian, and Spanish), the formal and informal registers are distinguished by the second person pronouns and/or verb agreement. In Japanese and other languages, distinctions that express polite, respectful, and humble speech can be more extensive: morphological markings on the main verb, as well as on some nouns and adjectives, specific lexical choices and longer sentences. We give examples of these phenomena in Table 1.

Controlling the politeness or formality level of a machine translation model has been explored in recent work [1-6] for a subset of languages (German, Japanese, Spanish, French, Czech, English), showing there is continued interest in addressing this problem. This special task invites participants to advance research on **controlling formality for a diverse set of target languages with a focus on zero-shot learning in multilingual models**. We will release annotated training and test data for four diverse language pairs — English (EN) into German (DE), Spanish (ES), Hindi (HI), and Japanese (JA) — as well as annotated test data for two additional language pairs — EN into Italian (IT) and Russian (RU).

 Relevant topics for this task include, but are not limited to, the following areas:

* Zero-shot formality learning in multilingual models
* Knowledge transfer within and across language families
* Analysing and evaluating aspects of formality beyond honorifics and grammatical register
* Language-specific insights and resources


**Table 1** Contrastive reference translations with different formality levels. Phrase-level formality markers in the target languages are annotated with [F]text[/F].

|Language	|	|Text	|
|---	|---	|---	|
|HI	|Source	|Yeah but don't blame yourself if society has it set up that way.	|
|	|Informal	|हाँ यदि समाज ने ही इस तरह स्थापित किया है तो खुद को दोष न **[F]दे[/F]**	|
|	|Formal	|हाँ यदि समाज ने ही इस तरह स्थापित किया है तो खुद को दोष न **[F]दें[/F]**	|
|DE	|Source	|Could you provide your first name please?	|
|	|Informal	|**[F]Könntest du[F]** bitte **[F]deinen[/F]** Vornamen angeben?	|
|	|Formal	|**[F]Könnten Sie[/F]** bitte **[/F]Ihren[/F]** Vornamen angeben?	|
|JA	|Source	|I'm very sorry to hear that. You may go back and see if the chef can try to make meal again.	|
|	|Informal (_Kudaketa_)	|それを聞いて大変 **[F]残念に思う[/F]** 。 **[/F]戻って[/F]** 、シェフがもう一度食事を作り直せるかどうかを **[F]確認して[/F]** 。	|
|	|Formal (_Teineigo_)	|それを聞いて大変 **[F]残念に思います[/F]** 。 **[F]戻って[/F]** 、シェフがもう一度食事を作り直せるかどうかを **[F]確認してください[/F]** 。	|
|	|High-formal (_Sonkeigo / Kenjōgo_)	|それを聞いて大変 **[F]残念に思います[/F]** 。 **[F]お戻りになって[/F]** 、シェフがもう一度食事を作り直せるかどうかを **[F]確認なさってください[/F]** 。	|



### Important dates

Tentative schedule based on the IWSLT dates.


|Date |Stage |
|---	|---	|
|Jan, 15 2022	|release of formality-annotated training and dev data	|
|Mar 14, 2022	|formality evaluation data released	|
|Mar 24, 2022	|translation submission deadline	|
|Mar 25, 2022	|formality reference translations released	|
|Apr 1, 2022	|system paper submission deadline	|
|Apr 22, 2022	|paper notification	|
|May 1, 2022	|camera ready deadline	|
|May 26-27, 2022	|IWSLT conference	|



## Dataset

### Language pairs

For the formality control task, we propose **supervised** and **zero-shot** settings focusing on text-to-text translation of spoken language.

The following language pairs will be evaluated in the supervised setting (formality-annotated training data and test data will be released):

1. English → German (EN-DE)
2. English → Spanish (EN-ES)
3. English → Hindi (EN-HI)
4. English → Japanese (EN-JA)

In addition, we will release test data **only** for the following language pairs in the zero-shot setting:

1. English → Italian (EN-IT)
2. English → Russian (EN-RU)



### Formality-annotated data

As part of this special task, we will **release novel targeted train and test sets** comprising of source segments paired with two contrastive reference translations, one for each formality level (informal and formal). Formality distinctions are expressed by the use of grammatical register or honorific language. Table 2 reports the number of source segments used for training and evaluation and the overlap between the references (informal vs. formal) as measured by BLEU. The lowest overlap is for Japanese and the highest overlap is for Hindi, indicating that the task of controlling formality is more challenging for Japanese than for Hindi.

**Table 2**. Number of source segments in the released dataset and the overlap between the references (informal vs formal) as measured by BLEU on the test set.

|setting	|language pair	|train	|test	|test reference overlap (BLEU)	|
|---	|---	|---	|---	|---	|
|supervised	|EN-JA	|TBD	|TBD	|74.3	|
|supervised	|EN-DE	|TBD	|TBD	|74.9	|
|supervised	|EN-ES	|TBD	|TBD	|78.7	|
|supervised	|EN-HI	|TBD	|TBD	|81.6	|
|zero-shot	|EN-IT	|0	|TBD	|78.7	|
|zero-shot	|EN-RU	|0	|TBD	|TBD	|

This special task will offer two training scenarios: **supervised** and **zero-shot**. For the **supervised** training scenario, participants can use the labeled training set for training and development. For the **zero-shot** task, we will release only test data.

We ask that all participants cite [citation instructions to follow]


### Additional training data

To encourage participation from groups with limited computational resources and to make it easier to compare results, we ask participants to declare whether their models fall under the “constrained” or “unconstrained” training regime.

Constrained task:

* Allowed to use formality-labeled data provided by organizers
* EN-DE, EN-ES, EN-IT, EN-RU: allowed to use the textual MuST-C v1.2 data
* EN-HI, EN-JA: allowed to use data from WMT news translation tasks
* Allowed to use multilingual data from the same dataset (e.g. using EN-FR data for training EN-ES models)

Unconstrained task: Allowed to use all the data from the constrained task, plus

* Allowed to use pre-trained models (e.g. mBERT, mBART)
* Allowed to use additional annotations from morphological analysers
* EN-DE, EN-ES, EN-IT, EN-RU: allowed to use data from WMT news translation tasks and Paracrawl v9
* EN-HI, EN-JA: allowed to use any other textual datasets as long as they are publicly available, such as WikiMatrix

Note: in all cases, **no additionally manually created formality-labeled data is allowed**. However, for the unconstrained setting, obtaining additional annotations automatically is allowed **as long as the code and data will be shared**.


### Additional test data

Overall translation quality will be evaluated on MuST-C v1.2 testsets for EN-DE, EN-ES, EN-IT, EN-RU and WMT newstest2020 for EN-JA and newstest2014 for EN-HI.


## Evaluation

This special task is **self-service**. In order to have their system included in the task and findings paper, participants must::

* evaluate their systems using the provided test sets and automatic metrics
* upload the system outputs to the dedicated github repository (MIT license)
* report their results in a system description paper, which will then be collated in the findings paper


Each system will be evaluated for formality control for the provided test set, as well as for overall translation quality on a generic test set. The organizers will provide a targeted automatic metric, leveraging phrase-level annotations in our dataset, for system-level evaluation of formality-controlled models. Overall translation quality will be measured with [SacreBLEU v2.0.0](https://pypi.org/project/sacrebleu/2.0.0/) and [COMET v1.0.1](https://pypi.org/project/unbabel-comet/1.0.1/) automatic metrics.


## Submissions

Submissions should be made to a dedicated public github repository under an MIT license. Submissions should be packed in a compressed file following the naming convention: `formality-control_[participant-name].tar.gz`. Packages should be organized per source to target language pair and per data setting (such as `En-IT/constrained`) and include:

* `README.md`: including
    * Brief description of each system submitted
    * System performance as computed by the participants
    * Training data conditions (constrained/unconstrained; full/zero-shot)
    * List of the data sources used for training the system
    * Institution and contact person
* Source and system output files for the formality control test set
    * Plaintext files, one sentence per line, pre-formatted for scoring (detokenized, detruecased)
    * For each system, one output file for each formality level, named `formality-control-[id].[formality-level].[target]` (where `id` is used to distinguish if several approaches are submitted). Example: `formality-control-1.formal.de`
* Source and system output files for the generic quality test set
    * Plaintext files, one sentence per line, pre-formatted for scoring (detokenized, detruecased)
    * One output file per system (corresponding to a generic formality level)


In addition to the system outputs, participants are required to submit the performance of their system(s) in terms of [SacreBLEU v2.0.0](https://pypi.org/project/sacrebleu/2.0.0/), [COMET v1.0.1](https://pypi.org/project/unbabel-comet/1.0.1/), and formality control (using the script provided). We invite participants to also submit a paper describing their system(s). Unconstrained and constrained systems should be evaluated separately in the system description paper.


## Organizers

Amazon AWS Translate:

* Maria Nadejde
* Anna Currey
* Benjamin Hsu
* Xing Niu
* Georgiana Dinu
* Marcello Federico

## FAQ

* Will the organizers provide a mechanism for submitting the system outputs and maintain a leaderboard?
    * No. The organizers provide the dataset, train/test splits, and a script for the automatic evaluation metrics. The participants will report their results in a system description paper which will be then summarized in the findings paper. 
* How many formality levels will be evaluated?
    * The provided dataset will have two levels — formal and informal.
* How will the system outputs be shared?
    * Participants upload their system outputs to a dedicated public Github repository with a permissive license (MIT) which allows all participants to use and evaluate the outputs.
* What training data are participants allowed to use?
    * We divide the task into **constrained** and **unconstrained** settings, with different allowed training data for each. See the "Additional training data" section for more information
* Are pre-trained models such as mBERT and mBART allowed?
    * Yes, the use of pre-trained models is allowed. 
* Can papers be submitted to multiple venues?
    * Yes, as long as they cite the dataset/findings paper.

## References

[1] Rico Sennrich, Barry Haddow, and Alexandra Birch. 2016. [Controlling Politeness in Neural Machine Translation via Side Constraints](https://aclanthology.org/N16-1005.pdf). In NAACL.<br/>
[2] Weston Feely, Eva Hasler, and Adrià de Gispert. 2019. [Controlling Japanese Honorifics in English-to-Japanese Neural Machine Translation](https://aclanthology.org/D19-5203.pdf). In WAT.<br/>
[3] Aditi Viswanathan, Varden Wang, and Antonina Kononova. 2019. [Controlling Formality and Style of Machine Translation Output Using AutoML](https://storage.googleapis.com/pub-tools-public-publication-data/pdf/120aaefb5f01e824110cfb524ff251db11bf0734.pdf). In SIM-Big.<br/>
[4] Xing Niu, Marianna Martindale, and Marine Carpuat. 2017 [A Study of Style in Machine Translation: Controlling the Formality of Machine Translation Output](https://aclanthology.org/D17-1299.pdf). In ENMLP.<br/>
[5] Xing Niu, Sudha Rao, and Marine Carpuat. 2018. [Multi-Task Neural Models for Translating Between Styles Within and Across Languages](https://aclanthology.org/C18-1086.pdf) In COLING.<br/>
[6] Andrea Schioppa, David Vilar, Artem Sokolov, Katja Filippova. 2021. [Controlling Machine Translation for Multiple Attributes with Additive Interventions](https://aclanthology.org/2021.emnlp-main.535.pdf). In EMNLP.<br/>

<!-- Markdown notes: comments can be formed as above; bulleted lines start with a - ; if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line -->
