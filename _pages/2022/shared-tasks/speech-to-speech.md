---
permalink: /2022/speech-to-speech
title: "Offline Speech to Speech Translation"
toc: true
toc_sticky: true
---

## Description

<!-- the task, the languages, and the type of data -->

**Note: this is a draft and feedback on the task setup is welcome, either via [iwslt-evaluation-campaign@googlegroups.com](iwslt-evaluation-campaign@googlegroups.com) or Twitter ([@iwslt](https://twitter.com/iwslt))**

This goal of this task is to foster the development of automatic methods to translate speech in one language to speech in another target language. In particular, we are interested in comparing the performance of cascade (ASR + MT + TTS or S2T + TTS) approaches with end-to-end (S2S) approaches. For this first edition, we are restricting the scope of the task to offline systems and the English-German language direction. We may extend this task to include simultaneous systems and possibly other languages in subsequent editions.

## Evaluation

**Automatic metrics**

To automatically evaluate quality, the speech output will be automatically transcribed with an ASR system provided by the organizers, and then we will compute BLEU and chrF between the produced transcript and a textual human reference.

**Human evaluation**

In addition to **translation quality** (capturing meaning), the quality of the speech output will also be human-evaluated along three dimensions: **naturalness** (voice and pronunciation), **clarity of speech** (understandability), and **sound quality** (noise and other artifacts). These axes are more fine-grained than the traditional overall MOS score.  
Bilingual annotators will be presented with the source audio and the target audio, and give scores between 1 and 5.

TODO: share details on guidelines.

## Ranking

While we will share both automatic and human evaluation scores, the systems will be ranked according to the human evaluation.

## Training and Development Data

This task allows the same training data as the [Offline task](https://iwslt.org/2022/offline).  
Additional training data will be provided for German TTS and S2S models:
- CSS10
- Synthesized, aligned German target audio for English—German MuST-C
- A pretrained German TTS model to facilitate cascaded models and dual submission with the Offline task

## Segmentation

Sentence-segmented input will be provided.

## Baseline Implementation and Example

TBD Provide baseline?

## System Submission

TBD

## Contacts

Discussion: [iwslt-evaluation-campaign@googlegroups.com](https://groups.google.com/g/iwslt-evaluation-campaign)

## Organizers

<!-- list of names and affiliations -->

* Juan Pino (Meta)
* Marco Turchi (FBK)
* Jan Niehues (Maastricht)
* Elizabeth Salesky (JHU)
* Matteo Negri (FBK)
* Sebastian Stueker (Zoom)

<!-- Markdown notes: comments can be formed as above; bulleted lines start with a - ; if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line -->

