---
permalink: /2023/s2s
title: "Speech-to-speech track"
toc: true
toc_sticky: true
---

<!--
Markdown notes: comments can be formed as in this example;
bulleted lines start with a - ;
if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line
-->

## Description

This goal of this task is to foster the development of automatic methods to translate speech in one language to speech in another target language. In particular, we are interested in comparing the performance of cascade (S2T + TTS) approaches with end-to-end/direct (S2S) approaches under large-scale data setting. We are restricting the scope of the task to offline systems and the English-Chinese language direction. 

<!-- Description the task, the languages, and the type of data -->

## Constrained Track

In order to simplify the task and to be able to compare more systems together, **we will only allow one constrained track** (see training data allowed below).

## Ranking

While we will share both automatic and human evaluation scores, the systems will be ranked according to the human evaluation.

## Evaluation

**Automatic metrics**
- **ASR-BLEU**: the speech output will be automatically transcribed with a Chinese ASR system trained on [WenetSpeech](https://github.com/wenet-e2e/wenet/blob/main/docs/pretrained_models.en.md), and then BLEU and chrF will be computed between the produced transcript and a textual human reference.
- **BLASER**: the newly proposed text-free speech-to-speech translation evaluation metric, [BLASER](https://github.com/facebookresearch/stopes/tree/main/stopes/eval/blaser), will be computed between the translated speech and referenced speech. 

**Human evaluation**
- **Translation quality**: bilingual annotators will be presented with the source audio and the target audio, and give scores between 1 and 5.
- **Output speech quality**: in addition to translation quality (capturing meaning), the quality of the speech output will also be human-evaluated along three dimensions: naturalness (voice and pronunciation), clarity of speech (understandability), and sound quality (noise and other artifacts). These axes are more fine-grained than the traditional overall MOS score.

The detailed guidelines for speech quality are as follows:
- **Naturalness**: recordings that sound human-like, with natural-sounding pauses, stress, and intonation, should be given a high score. Recordings that sound robotic, flat, or otherwise unnatural should be given a low score.
- **Clarity of speech**: recordings with clear speech and no mumbling and unclear phrases should be given a high score. Recordings with a large amount of mumbling and unclear phrases should be given a low score.
- **Sound quality**: recordings with clean audio and no noise and static in the background should be given a high score. Recordings with a large amount of noise and static in the background should be given a low score.

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

## Training Data

This task allows all training data from the Offline task on speech-to-text translation.
In addition, the following training data is allowed for the purpose of building Chinese TTS and English-Chinese speech-to-speech models (note that you can also use the Offline task data to build TTS or speech-to-speech models):
- [GigaS2S](https://github.com/SpeechTranslation/GigaS2S): target speech for the Chinese target text of [GigaST](https://arxiv.org/abs/2204.03939) which has been synthesized using an in-house TTS model.  The source speech can be obtained from [GigaSpeech](https://arxiv.org/abs/2106.06909).
- [aishell_3](https://www.aishelltech.com/aishell_3): multi-speaker Chinese TTS dataset.

## Development Data

[Development](http://lf3-nlp-opensource.bytetos.com/obj/nlp-opensource/datasets/GigaS2S/EN2ZH/DEV.zip) data can be download, which includes 5715 parallel En2Zh audio segments.

## Test Data

The [blind evaluation](http://lf3-nlp-opensource.bytetos.com/obj/nlp-opensource/datasets/GigaS2S/EN2ZH/TEST.zip) data can be downloaded now. The test set contains 2000 wav files named 0000.wav, 0001.wav, ..., 1999.wav. 

The [expanded test set](https://drive.google.com/file/d/1erxpGL7nzc3vIdm7KhipMAr4ai5mztMF/view?usp=sharing) is updated, which contains 3917 wav files named 2000.wav, ..., 5916.wav.

The corresponding audio translation of each given audio file should be produced by the speech to speech translation system.


## Segmentation

Sentence-segmented input will be provided.


## Submission

Submissions should be compressed in a single .tar.gz file and sent as an email attachment to dongqianqian@bytedance.com. If multiple outputs are submitted, one system must be explicitly marked as primary, or the submission with the latest timestamp will be treated as primary. The submission should contain one wav file per input segment and a README or README.md file briefly describing the system. There are no restrictions on the number of channels or sampling rate.
Test data release and system submission deadlines will follow the same [dates](https://iwslt.org/2023/#important-dates) as all shared tasks.

<!-- Description of expected submission format and submission instructions -->


## Organizers

<!-- List of organizers' names and affiliations -->
- Qianqian Dong (ByteDance)
- Tom Ko (ByteDance)
- Mingxuan Wang (ByteDance)


## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair:   
Discussion: <iwslt-evaluation-campaign@googlegroups.com>
