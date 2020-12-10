---
permalink: /2021/low-resource
title: "Low-Resource Speech Translation"
---

## Description
<!-- the task, the languages, and the type of data -->

This shared task will focus on the problem of developing speech transcription and translation tools for under-resourced languages, to match the real-world needs of humanitarian organizations.
For the vast majority of the world's languages there exist little speech-translation parallel data at the scale needed to train speech translation models. Instead, in a real-world situation we will have access to limited, disparate resources (e.g. word-level translations, speech recognition, small parallel text data, monolingual text, raw audio, etc).

This shared task, in collaboration with the Translators without Borders, invites participants to build the best speech transcription/translation system they can for transcribing and/or translating between the following language pairs:

- Coastal Swahili (swa) to English (eng)
- Congolese Swahili (swc) to French (fra)

We will provide a list of available:
- parallel translation text corpora for any combination between {swa,swc}x{eng,fra}
- speech recognition datasets for the Swahili varieties (which will be the source side)
- small speech translation datasets for the two language pairs
- word-level terminologies and lexicons
- monolingual textual corpora on all four languages

We allow the use of any pre-trained machine translation, speech recognition, speech synthesis, or speech translation model. We will allow both constrained and unconstrained submissions (a constrained submission will be one using only the data we provide/list). The only data that will not be allowed will be the ones that will be part of the test set.

We invite participants to explore all possible research directions: from pipeline approaches, to end-to-end models, offline or online methods, using other languages through cross-lingual transfer (checkout the [shared task on multilingual speech translation](/2021/multilingual), which provides several datasets), data augmentation, and anything else you come up with.

We look forward to your creative submissions!  

Data, baselines, and evaluation scripts will be released Feb. 1, 2020.
{: .notice--warning}

## Evaluation

The primary task is translation, and hence the submissions will be evaluated using standard automatic translation metrics (e.g. BLEU, chrF++, BERTscore, YiSi, etc). 
In addition, if the participants' systems also produce transcriptions for the source utterances (which would be the case for pipeline/cascade or multitask systems), we will invite their submission and also evaluate on ASR quality using standard ASR metrics (WER).


## Organizers

- Antonios Anastasopoulos (George Mason University, USA)
- Grace Tang (Translators without Borders)
- Will Lewis (University of Washington, USA)
- Sylwia Tur (Appen, USA)
- Rosie Lazar (Appen, USA)
- Marcello Federico (Amazon, USA)
- Alex Waibel (CMU, USA)

<!-- list of names and affiliations -->


<!-- Markdown notes: comments can be formed as above; bulleted lines start with a - ; if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line -->
