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

Data will be released in January.

<!-- Details description of the data and links to download -->


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
