---
permalink: /2022/speech-to-speech
title: "Offline Speech to Speech Translation"
toc: true
toc_sticky: true
---

## Description

<!-- the task, the languages, and the type of data -->

This goal of this task is to foster the development of automatic methods to translate speech in one language to speech in another target language. In particular, we are interested in comparing the performance of cascade (ASR + MT + TTS or S2T + TTS) approaches with end-to-end/direct (S2S) approaches. For this first edition, we are restricting the scope of the task to offline systems and the English-German language direction. We may extend this task to include simultaneous systems and other languages in subsequent editions.

## Constrained Track

In order to simplify the task and to be able to compare more systems together, **we will only allow one constrained track** (see training data allowed below).

## Ranking

While we will share both automatic and human evaluation scores, the systems will be ranked according to the human evaluation.

## Evaluation

**Automatic metrics**

To automatically evaluate quality, the speech output will be automatically transcribed with an ASR system ([wav2vec2-large-xlsr-53-german](https://huggingface.co/facebook/wav2vec2-large-xlsr-53-german)), and then we will compute BLEU and chrF between the produced transcript and a textual human reference.

**Human evaluation**

- **Translation quality:** bilingual annotators will be presented with the source audio and the target audio, and give scores between 1 and 5.
- **Output speech quality:** in addition to **translation quality** (capturing meaning), the quality of the speech output will also be human-evaluated along three dimensions: **naturalness** (voice and pronunciation), **clarity of speech** (understandability), and **sound quality** (noise and other artifacts). These axes are more fine-grained than the traditional overall MOS score.

The detailed guidelines for speech quality are as follows:
- **Naturalness:** recordings that sound human-like, with natural-sounding pauses, stress, and intonation, should be given a high score. Recordings that sound robotic, flat, or otherwise unnatural should be given a low score.
- **Clarity of speech:** recordings with clear speech and no mumbling and unclear phrases should be given a high score. Recordings with a large amount of mumbling and unclear phrases should be given a low score.
- **Sound quality:** recordings with clean audio and no noise and static in the background should be given a high score. Recordings with a large amount of noise and static in the background should be given a low score.


## Training and Development Data

This task allows all training data from the [Offline task](https://iwslt.org/2022/offline) on English-German speech-to-text translation.

In addition, the following training data is allowed for the purpose of building German TTS and English-German speech-to-speech models (note that you can also use the Offline task data to build TTS or speech-to-speech models):
- [Synthesized MuST-C](https://dl.fbaipublicfiles.com/s2st/mustc_v2_en_de_tts.tgz): target speech for the German target text of MuST-C V2 which has been synthesized using a [VITS](https://github.com/jaywalnut310/vits) model trained on the German portion of CSS10.
- A [pretrained German TTS model](https://dl.fbaipublicfiles.com/s2st/G_24000.pth) to facilitate cascaded models and dual submission with the Offline task. To use this model in inference, see this [example notebook](https://github.com/jmp84/vits/blob/main/inference_iwslt.ipynb) together with this [VITS fork](https://github.com/jmp84/vits) (see the [README](https://github.com/jmp84/vits#readme) for instructions).
- [CSS10](https://github.com/Kyubyong/css10): single-speaker German TTS dataset

Note that several datasets allowed for the Offline task (including Common Voice and LibriVoxDeEn) contain multi-speaker German speech and text data. 

## Segmentation

Sentence-segmented input will be provided.

## System Submission

Submissions should be compressed in a single .tar.gz file and emailed to the organizers (link to come), with "IWSLT 2022 Speech-to-Speech Submission" in the subject line.
If multiple outputs are submitted, one system must be explicitly marked as primary, or the submission with the latest timestamp will be treated as primary.

Further submission information will be posted closer to the submission date.

Test data release and system submission deadlines will follow the same [dates](/2022/#important-dates) as all shared tasks.


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

