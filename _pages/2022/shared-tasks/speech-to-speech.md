---
permalink: /2022/speech-to-speech
title: "Offline Speech to Speech Translation"
---

## Description

<!-- the task, the languages, and the type of data -->

**Note: this is a draft and feedback on the task setup is welcome, either via iwslt-evaluation-campaign@googlegroups.com or Twitter (@iwslt)**

This goal of this task is to foster the development of automatic methods to translate speech in a language to speech in a target language. In particular, we are interested in comparing the performance of cascade (ASR + MT + TTS or S2T + TTS) approaches with end-to-end approaches. For this first edition, we are restricting the scope of the task to offline systems and the English-German language direction. We may extend this task to include simultaneous systems and possibly other languages in subsequent editions.

## Evaluation

**Automatic metric**

The output will be automatically transcribed with an ASR system provided by the organizers, then we will compute BLEU and chrF between the automatic transcript and a textual human reference.

**Human evaluation**

Bilingual annotators will give a semantic similarity score between 1 and 5 between the source audio and the target audio.
The quality of the output speech will also be evaluated along three dimensions: naturalness, clarity of speech and sound quality. These axes are more fine-grained than the traditional MOS score.

TODO: share details on guidelines.

## Ranking

The systems will be ranked according to the human evaluation.

## Training and Development Data

The offline task training data is allowed.

## Segmentation

Segmented input will be provided.

## Baseline Implementation and Example

Provide baseline?

## System Submission

TBD

## Contacts

Discussion: iwslt-evaluation-campaign@googlegroups.com

## Organizers

<!-- list of names and affiliations -->

* Marco Turchi (FBK)
* Jan Niehus (Maastricht)
* Elizabeth Salesky (JHU)
* Matteo Negri (FBK)
* Sebastian Stueker (Zoom)

<!-- Markdown notes: comments can be formed as above; bulleted lines start with a - ; if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line -->

