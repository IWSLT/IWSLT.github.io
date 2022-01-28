---
permalink: /2022/speech-to-speech
title: "Offline Speech to Speech Translation"
toc: true
toc_sticky: true
---

## Description

<!-- the task, the languages, and the type of data -->

This goal of this task is to foster the development of automatic methods to translate speech in one language to speech in another target language. In particular, we are interested in comparing the performance of cascade (ASR + MT + TTS or S2T + TTS) approaches with end-to-end/direct (S2ST) approaches. For this first edition, we are restricting the scope of the task to offline systems and the English-German language direction. We may extend this task to include simultaneous systems and possibly other languages in subsequent editions.

## Evaluation

**Automatic metrics**

To automatically evaluate quality, the speech output will be automatically transcribed with an ASR system ([wav2vec2-large-xlsr-53-german](https://huggingface.co/facebook/wav2vec2-large-xlsr-53-german)), and then we will compute BLEU and chrF between the produced transcript and a textual human reference.

**Human evaluation**

- Translation quality: bilingual annotators will be presented with the source audio and the target audio, and give scores between 1 and 5.
- Output speech quality: in addition to **translation quality** (capturing meaning), the quality of the speech output will also be human-evaluated along three dimensions: **naturalness** (voice and pronunciation), **clarity of speech** (understandability), and **sound quality** (noise and other artifacts). These axes are more fine-grained than the traditional overall MOS score.

The detailed guidelines for speech quality are as follows:
- Naturalness: recordings that sound human-like, with natural-sounding pauses, stress, and intonation, should be given a high score. Recordings that sound robotic, flat, or otherwise unnatural should be given a low score.
- Clarity of speech: recordings with clear speech and no mumbling and unclear phrases should be given a high score. Recordings with a large amount of mumbling and unclear phrases should be given a low score.
- Sound quality: recordings with clean audio and no noise and static in the background should be given a high score. Recordings with a large amount of noise and static in the background should be given a low score.

## Ranking

While we will share both automatic and human evaluation scores, the systems will be ranked according to the human evaluation.

## Training and Development Data

This task allows the same training data as the [Offline task](https://iwslt.org/2022/offline).

In addition, the following training data is allowed for the purpose of building German TTS and S2ST models:
- [CSS10](https://github.com/Kyubyong/css10)
- [Synthesized MuST-C](https://dl.fbaipublicfiles.com/s2st/mustc_v2_en_de_tts.tgz): the German target text of MuST-C V2 has been synthesized using a [VITS](https://github.com/jaywalnut310/vits) model trained on the German portion of CSS10.
- A [pretrained German TTS model](https://dl.fbaipublicfiles.com/s2st/G_24000.pth) to facilitate cascaded models and dual submission with the Offline task. To use this model in inference, see this [example notebook](https://github.com/jmp84/vits/blob/main/inference_iwslt.ipynb)

## Segmentation

Sentence-segmented input will be provided.

## System Submission

TBD

## Contacts

Discussion: [iwslt-evaluation-campaign@googlegroups.com](https://groups.google.com/g/iwslt-evaluation-campaign)

## Organizers

<!-- list of names and affiliations -->

* Elizabeth Salesky (JHU)
* Marco Turchi (FBK)
* Jan Niehues (Maastricht)
* Matteo Negri (FBK)
* Sebastian Stueker (Zoom)
* Marcello Federico (Amazon)
* Juan Pino (Meta)

<!-- Markdown notes: comments can be formed as above; bulleted lines start with a - ; if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line -->

