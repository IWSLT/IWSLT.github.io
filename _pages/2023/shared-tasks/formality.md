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

Machine translation (MT) models typically return one single translation for each input segment. This means that when the input segment is ambiguous, the model must choose a translation from among various valid options, without regard to the intended use case or target audience.

Specific problems can arise for spoken language translation from English into languages that have multiple levels of formality expressed through honorifics or “[grammatical register](https://www.w3.org/community/mqmcg/mqm-top-level-2019-04-11/)”. For example, the sentence ‘Are you tired?’ can have two possible correct translations in German: ‘Sind Sie müde?’ for the formal register and ‘Bist du müde?’ for the informal one. For applications of spoken language translation, leaving the model to choose between different valid translation options can lead to translations that are inconsistent or use an inappropriate formality level, which can be perceived as rude or jarring for speakers from certain cultures and for certain use cases (e.g. customer support chat).

How formality distinctions are expressed grammatically and lexically can vary widely by language. In many Indo-European languages (e.g., German, French, or Russian), the formal and informal registers are distinguished by the second person pronouns and/or verb agreement. In other languages like Korean, distinctions that express polite, respectful, and humble speech can be more extensive: morphological markings on the main verb, as well as on some nouns and adjectives, specific lexical choices and longer sentences. Languages might also vary stylistically from one variety to another (e.g. Portugal Portuguese and Brazilian Portuguese). Still other languages like Vietnamese present challenges in terms of resources available.

Last year’s result confirmed that zero-shot settings and languages with many grammatical and lexical formality distinctions are challenging settings for controlling formality. This year’s special task invites participants to advance research in effective methods for bridging the gap in formality control for zero-shot cases and for languages with rich grammatical and lexical formality distinctions. For this year, we focus on Korean and Vietnamese in the supervised setting and Portugal Portuguese (to explore potential transfer between regional varieties) and Russian in the zero-shot setting. 


## Data

### Accessing the data
The annotatated formality training data is now available for download under the CDLA-Sharing-1.0 License at this location: [amazon-science/IWSLT2023](https://github.com/amazon-science/contrastive-controlled-mt/tree/main/IWSLT2023). 

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


## Baselines

<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->


## Submission

<!-- Description of expected submission format and submission instructions -->


## Evaluation

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->


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
Chair:   
Discussion: <iwslt-evaluation-campaign@googlegroups.com>
