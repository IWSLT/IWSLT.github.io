---
permalink: /2022/speech-to-speech
title: "Offline Speech to Speech Translation"
---

## Description

<!-- the task, the languages, and the type of data -->

**Note: this is a draft and feedback on the task setup is welcome, either via iwslt-evaluation-campaign@googlegroups.com or Twitter (@iwslt)**

This goal of this task is to foster the development of automatic methods to translate speech in a language to speech in a target language. In particular, we are interested in comparing the performance of cascade (ASR + MT + TTS or S2T + TTS) approaches with end-to-end approaches. For this first edition, we are restricting the scope of the task to offline systems and the English-German language direction. We may extend this task to include simultaneous systems and possibly other languages in subsequent editions.

# Evaluation

## Automatic metric

The output will be automatically transcribed with an ASR system provided by the organizers, then we will compute BLEU and chrF between the automatic transcript and a textual human reference.

## Human evaluation

We will replace automatic components by humans: first the system output will be manually transcribed and the transcript will be compared to a textual human reference with direct assessment (1-5 scores).

Alternative: we can run direct assessment on comparing the output audio vs the reference audio (we could also break down for accuracy vs how natural the voice sounds).


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

