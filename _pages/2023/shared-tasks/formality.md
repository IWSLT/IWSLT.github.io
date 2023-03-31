---
permalink: /2023/formality
title: "Formality track"
toc: true
toc_sticky: true
---

<!--
Markdown notes: comments can be formed as in this example;
bulleted lines start with a - ;
if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line
-->

## Description

Machine translation (MT) models typically return one single translation for each input segment. This means that when the input segment is ambiguous, the model must choose a translation among various valid options without regard to the intended use case or target audience.

Specific problems can arise for spoken language translation from English into languages that have multiple levels of formality expressed through honorifics or “[grammatical register](https://www.w3.org/community/mqmcg/mqm-top-level-2019-04-11/)”. For example, the sentence ‘Are you tired?’ can be translated in German as  ‘Sind Sie müde?’ in the formal register and as ‘Bist du müde?’ in the informal one. For applications of spoken language translation, leaving the model to choose between different valid translation options can lead to translations that are inconsistent or use an inappropriate formality level, which can be perceived as rude or jarring for speakers from certain cultures and for certain use cases (e.g. customer support chat).

How formality distinctions are expressed grammatically and lexically can vary widely by language. In many Indo-European languages (e.g., German, French, or Russian), the formal and informal registers are distinguished by the second person pronouns and/or verb agreement. In other languages like Korean, distinctions that express polite, respectful, and humble speech can be more extensive: morphological markings on the main verb, as well as on some nouns and adjectives, specific lexical choices and longer sentences. Languages might also vary stylistically from one variety to another (e.g. Portugal Portuguese and Brazilian Portuguese). Still, other languages like Vietnamese present challenges in terms of resources available.

Last year’s results confirmed that zero-shot settings and languages with many grammatical and lexical formality distinctions are challenging settings for controlling formality. This year’s special task invites participants to advance research in effective methods for bridging the gap in formality control for zero-shot cases and for languages with rich grammatical and lexical formality distinctions. For this year, we focus on Korean and Vietnamese in the supervised setting and Portugal Portuguese (to explore potential transfer between regional varieties) and Russian in the zero-shot setting.


## Data

### Accessing the data
The annotated formality training data is now available for download under the CDLA-Sharing-1.0 License at this location: [amazon-science/IWSLT2023](https://github.com/amazon-science/contrastive-controlled-mt/tree/main/IWSLT2023). 

### Language pairs

For the formality control task, we propose **supervised** and **zero-shot** settings focusing on text-to-text translation of spoken language.

The following language pairs will be evaluated in the supervised setting (formality-annotated training data and test data will be released):

1. English → Korean (EN-KO)
2. English → Vietnamese (EN-VI)

In addition, we will release test data **only** for the following language pairs in the zero-shot setting:

1. English → Portugal Portuguese (EN-PT)
2. English → Russian (EN-RU)

### Formality-annotated data

As part of this special task, we will **release novel targeted train and test sets** comprising of source segments paired with two contrastive reference translations, one for each formality level (informal and formal). Formality distinctions are expressed by the use of grammatical register or honorific language. Table 1 gives examples of annotated contrastive translations from the dataset and Table 2 reports the number of source segments used for training and evaluation.

**Table 1** Contrastive reference translations with different formality levels. Phrase-level formality markers in the target languages are annotated with [F]text[/F].

|Language	|	|Text	|
|---	|---	|---	|
|KO	|Source	|Yeah Did your mom know you were throwing the party?	|
|	|Informal	|그, 어머님은 **[F]네가[/F]** 그 파티 연 거 **[F]아셔[/F]**?|
|	|Formal	|그, 어머님은 **[F]님이[/F]** 그 파티 연 거 **[F]아세요[/F]**?|
|VI |Source	|Is the sun blocking your internet signal tonight?|
|	|Informal |Tối nay mặt trời có chặn tín hiệu internet của **[F]bạn[/F]** không? |
|	|Formal	|Tối nay mặt trời có chặn tín hiệu internet của **[F]quý vị[/F]** không **[F]ạ[/F]**?|

**Table 2**. Number of source segments in the released dataset.

|setting	|language pair	|train	|test		|
|---	|---	|---	|---		|
|supervised	|EN-KO	|400	|600		|
|supervised	|EN-VI	|400	|600		|
|zero-shot	|EN-PT	|0	|600		|
|zero-shot	|EN-RU	  |0	|600		|

This special task will offer two training scenarios: **supervised** and **zero-shot**. For the **supervised** training scenario, participants can use the labeled training set for training and development. For the **zero-shot** task, we will release only test data.

## Conditions

Participants can build systems for evaluation under the following settings:

* Constrained task: systems can be trained only on the datasets 
    * provided by the organizers 
    * [from last year’s edition under constrained conditions](https://iwslt.org/2022/formality#additional-training-data)
    * [CCMatrix](https://opus.nlpl.eu/CCMatrix.php) and [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles-v2018.php)

* Unconstrained task: participants may use any publicly available datasets and resources: the use of pre-trained language models are also allowed.


Note: in all cases, **no additionally manually created formality-labeled data is allowed**. However, for the unconstrained setting, obtaining additional annotations automatically is allowed **as long as the code and data will be shared**.


## Baselines

<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->

We will provide baselines for the **constrained supervised task** based on the transfer learning approach detailed in [Nadejde et al., 2022](https://aclanthology.org/2022.findings-naacl.47.pdf), where a generic pre-trained neural machine translation model (trained on CCMatrix) is finetuned on generic unlabelled and formality-annotated contrastive controlled datasets. Please refer to the original paper for more details.

## Submission

<!-- Description of expected submission format and submission instructions -->

Submissions should be packed in a compressed file with the following naming convention: `formality-control_[participant-name].tar.gz`. Packages should be organized per source-target language pair, per data setting, and per test set (e.g. `./EN-KO/constrained/blind-test/` or `./EN-KO/constrained/flores-test/`).

Each directory should include:
* Source and system output files for the formality control test set
    * Plaintext files, one sentence per line, pre-formatted for scoring (detokenized, detruecased) 
    * For each system, one output file for each formality level, named `formality-control-[id].[formality-level].[target]` (where id is used to distinguish if several approaches are submitted). Example: `formality-control-1.formal.ko`
* Source and system output files for the [FLORES](https://github.com/facebookresearch/flores/blob/main/flores200/README.md) test set for all the language pairs. Outputs should be formatted as:
    * Plaintext files, one sentence per line, pre-formatted for scoring (detokenized, detruecased). One output file per system (corresponding to a generic formality level), named `formality-control-[id].flores.[target]` (where id is used to distinguish if several approaches are submitted). 
* MIT license for the system outputs

The top-level directory should also include a README.md with the following information
* Brief description of each system submitted, including which system they prefer for final evaluation by the organizers (marked primary)
* Training data conditions (constrained/unconstrained; full/zero-shot)
* List of the resources used for training the system
* [Automatic evaluation](https://iwslt.org/2023/formality#evaluation) scores for their system(s)
* Institution and contact person
* Your consent to release the system outputs under MIT license for future research and human evaluation

 Submissions should be emailed to the address `sweagraw@umd.edu` and `erip@umd.edu` with the subject line: `IWSLT2023 Formality-Control Submission`. We also invite participants to submit a paper describing their system(s) via the conference submission page.

## Evaluation

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

We will evaluate the submitted system outputs along the following two dimensions:

a) The overall translation quality of the outputs will be evaluated using [SacreBLEU v2.0.0](https://pypi.org/project/sacrebleu/2.0.0/), and  [COMET](https://github.com/Unbabel/COMET) (eamt22-cometinho-da) on both the shared task-provided test sets and a generic test set. We will use [FLORES](https://github.com/facebookresearch/flores/tree/main/flores200) as our generic quality test bed for all language pairs under supervised and zero-shot settings.

b) Formality control of the models will be evaluated using:

1. [Matched-Accuracy](https://github.com/amazon-research/contrastive-controlled-mt/tree/main/IWSLT2022#evaluation) (M-Acc), a reference-based corpus-level automatic metric that leverages phrase-level formality markers from the references to classify a system-generated hypothesis as formal, informal, or neutral. The final corpus-level score is the percentage of system outputs that matches the desired formality level.
    
2. a reference-free variant of M-Acc that uses a multilingual formality classifier to label a system-generated hypothesis as formal or informal. The final corpus-level score is the percentage of system outputs that matches the desired formality level. The formality classifier will be released soon.

Details on the deciding criteria for the overall ranking of the submitted systems will be updated soon.


## Organizers

<!-- List of organizers' names and affiliations -->

- Sweta Agrawal (UMD)
- Marine Carpuat (UMD)
- Elijah Rippeth (UMD)
- Anna Currey (AWS AI Labs)
- Benjamin Hsu (AWS AI Labs)
- Phu Mon Htut (AWS AI Labs)
- Maria Nadejde (AWS AI Labs)
- Xing Niu (AWS AI Labs)

## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chairs: Benjamin Hsu, AWS AI Labs and Marine Carpuat, UMD <br>
Discussion: <iwslt-evaluation-campaign@googlegroups.com>
