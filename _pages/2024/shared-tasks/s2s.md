---
permalink: /2024/s2s
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

## Evaluation

**Automatic metrics**
- **ASR-BLEU**: the speech output will be automatically transcribed with a commercial Chinese ASR system, and then COMET、BLEURT、BLEU and chrF will be computed between the produced transcript and a textual human reference. 
- **BLASER**: the text-free speech-to-speech translation evaluation metric,  [BLASER](https://github.com/facebookresearch/stopes/tree/main/stopes/eval/blaser), will be computed between the translated speech and referenced speech. 

For automatic evaluation, the submitted runs will be ranked based on COMET metric.

**Human evaluation**
- **Translation quality**: Bilingual annotators will be presented with the source audio and the target audio, and give scores between 1 and 5.
- **Output speech quality**: The quality of the speech output will also be human-evaluated along three dimensions: naturalness (voice and pronunciation), clarity of speech (understandability), and sound quality (noise and other artifacts). 

  The detailed guidelines for speech quality are as follows:    
    - **Naturalness**: Synthesized audios that sound human-like, with natural-sounding pauses, stress, and intonation, should be given a high score; Synthesized audios that sound robotic, flat, or otherwise unnatural should be given a low score.
    - **Clarity of speech**: Synthesized audios with clear speech and no mumbling and unclear phrases should be given a high score; Synthesized audios with a large amount of mumbling and unclear phrases should be given a low score.
    - **Sound quality**: Synthesized audios with clean audio and no noise and static in the background should be given a high score; Synthesized audios with a large amount of noise and static in the background should be given a low score.

- **Timbre similarity**: Evaluating the similarity of synthesized audio's timbre to that of the source language audio.

For human evaluation, the submitted runs will be ranked based on the weighted scores from the three aspects.

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

## Training Data and Data Conditions

The evaluation setting aligns with the offline track and consists of three scenarios, including **constrained**, **constrained with large language models**, **unconstrained**. For detailed information, please refer to the [offline track](https://iwslt.org/2024/offline).

For **constrained** and **constrained with large language models** settings, there are the following differences: 

This task allows all training data from the Offline task on speech-to-text translation. In addition, the following training data is allowed for the purpose of building Chinese TTS and English-Chinese speech-to-speech models (note that you can also use the Offline task data to build TTS or speech-to-speech models):
- [GigaS2S](https://github.com/SpeechTranslation/GigaS2S): target speech for the Chinese target text of [GigaST](https://arxiv.org/abs/2204.03939) which has been synthesized using an in-house TTS model.  The source speech can be obtained from [GigaSpeech](https://arxiv.org/abs/2106.06909).
- [aishell_3](https://www.aishelltech.com/aishell_3): multi-speaker Chinese TTS dataset.

## Development Data

The development set also aligns with the [offline track](https://iwslt.org/2024/offline#past-editions-development-data) and the past edition of English-to-Chinese translation set can be used as the development set. 

## Test Data
The [blind evaluation](https://drive.google.com/file/d/14i4gQwfxoskzLR_STDtqyj7z-vO6xBoU/view?usp=sharing) data can be downloaded now. The test set contains 2000 wav files named 0000.wav, 0001.wav, ..., 1999.wav. 

The corresponding audio translation of each given audio file should be produced by the speech to speech translation system.

## Segmentation

Sentence-segmented input will be provided.


## Submission

- Submissions should be compressed in a single .tar.gz file and sent as an email attachment to dongqianqian@bytedance.com. If multiple outputs are submitted, one system must be explicitly marked as primary, or the submission with the latest timestamp will be treated as primary. 
- The submission should contain one wav file per input segment and a README or README.md file briefly describing the system and explicitly stating whether the system is cascaded or end-to-end, constrained or unconstrained. 
- There are no restrictions on the number of channels or sampling rate. 

The deadline for submission has been extended to **April 20th, 2024**.

<!-- Description of expected submission format and submission instructions -->


## Organizers

<!-- List of organizers' names and affiliations -->
- Qianqian Dong (ByteDance)
- Tian Tan (ByteDance)


## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair:   
Discussion: <iwslt-evaluation-campaign@googlegroups.com>