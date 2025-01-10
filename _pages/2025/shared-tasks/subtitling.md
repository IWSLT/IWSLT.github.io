---
permalink: /2025/subtitling
title: "Subtitling track"
toc: true
toc_sticky: true
---

<!--
Markdown notes: comments can be formed as in this example;
bulleted lines start with a - ;
if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line
-->
[Last update: Jan 10, 2025]

## Description

<!-- Description the task, the languages, and the type of data -->

In recent years, the task of automatically creating subtitles for audiovisual content in another language has gained increasing attention, as we have seen a surge in the amount of movies, series, and user-generated videos that are being streamed and distributed all over the world. The task is a multi-faceted one: not only the translation has to be generated from speech, which is right on target for IWSLT, but also the subtitling constraints have to be respected (i.e. a proper reading speed, synchrony with the voices, maximum number of subtitle lines and characters per line).

As in 2024, in 2025 edition we propose two sub-tracks:
* **automatic subtitling**: participants are asked to generate subtitles in Arabic and/or German of different kinds of audiovisual documents, featuring different levels of complexity, starting from English speech
* **subtitle compression**: participants are asked to rephrase subtitles that are non-compliant with the reading speed constraint (at most 21 characters / second) to make them compliant

and two language directions:
* 🆕 English &rarr; Arabic
* English &rarr; German

### 🔵 AUTOMATIC SUBTITLING 🔵

## Training and Data Conditions
<!-- Details description of the data and links to download -->
Two training data conditions are proposed:
* **constrained**: the official training data condition, in which the allowed training data is limited to a medium-sized framework (described below) in order to keep the training time and resource requirements manageable
* **unconstrained**: a setup without data restrictions (any resource, pre-trained language models can be used) to allow also the participation of teams equipped with high computational power and effective in-house solutions built on additional resources

#### Training Data allowed for Constrained Conditions

| Data type | src lang | tgt lang | Training corpus (URL) | Version | Comment
| --- | :---: | :---: | --- | --- | --- |
| speech | en | -- | [LibriSpeech ASR corpus](http://www.openslr.org/12/) | v12 | includes translations into *pt*, not to be used
| speech | en | -- | [How2](https://github.com/srvk/how2-dataset) | na | |
| speech | en | -- | [Mozilla Common Voice](https://commonvoice.mozilla.org/en/datasets) | v11.0  | |
| speech | en | -- | [Vox Populi](https://github.com/facebookresearch/voxpopuli) | na | |
| speech-to-text-parallel | en | de | [CoVoST](https://github.com/facebookresearch/covost) | v2 | only German translation, no English transcription |
| speech-to-text-parallel | en | de, es | [Europarl-ST](https://www.mllp.upv.es/europarl-st/) | v1.1 | |
| text-parallel | en | de | [Europarl](https://www.statmt.org/europarl/v10/training/europarl-v10.de-en.tsv.gz) | v10 | |
| text-parallel | en | es | [Europarl](https://object.pouta.csc.fi/OPUS-Europarl/v8/tmx/en-es.tmx.gz) | v8 | |
| text-parallel | en | de | [NewsCommentary](https://data.statmt.org/news-commentary/v16/training/news-commentary-v16.de-en.tsv.gz) | v16 | |
| text-parallel | en | es | [NewsCommentary](https://data.statmt.org/news-commentary/v16/training/news-commentary-v16.en-es.tsv.gz) | v16 | |
| text-parallel | en | de | [OpenSubtitles](https://apptek930-my.sharepoint.com/:u:/g/personal/ematusov_apptek_com/ESYWN8_BzeJAmBv4GcRapbsBeLpmLOd699qBc9_WG7Gifw?e=Bk6UWh) | v2018 apptek | partially re-aligned, filtered, with document meta-information on genre |
| text-parallel | en | es | [OpenSubtitles](https://apptek930-my.sharepoint.com/:u:/g/personal/ematusov_apptek_com/EafNtfaI0yNKgsoDIDTsEK8BelStVZVsZIrQcwjgTx5diA?e=BT97yx) | v2018 apptek | partially re-aligned, filtered, with document meta-information on genre |
| text-parallel | en | es | [Tatoeba](https://object.pouta.csc.fi/OPUS-Tatoeba/v2022-03-03/tmx/en-es.tmx.gz) | v2022-03-03 | |
| text-parallel | en | de | [Tatoeba](https://object.pouta.csc.fi/OPUS-Tatoeba/v2022-03-03/tmx/de-en.tmx.gz) | v2022-03-03 | |
| text-parallel | en | es | [ELRC-CORDIS_News](https://object.pouta.csc.fi/OPUS-ELRC-CORDIS_News/v1/tmx/en-es.tmx.gz) | v1 | |
| text-parallel | en | de | [ELRC-CORDIS_News](https://object.pouta.csc.fi/OPUS-ELRC-CORDIS_News/v1/tmx/de-en.tmx.gz) | v1 | |
| text-monolingual | -- | de | [OpenSubtitles with subtitle breaks](https://fbk.sharepoint.com/:u:/s/MTUnit/Efm0lF0ITTJeBM0ZmjlAKeEBu9CE33SCvb05S1tAq2AkSA?e=FHbZci) | v2018-apptek | superset of parallel data, with subtitle breaks and document meta-info on genre, automatically predicted line breaks |
| text-monolingual | -- | es | [OpenSubtitles with subtitle breaks](https://fbk.sharepoint.com/:u:/s/MTUnit/EXSih5zOAUZciBlO9HiXrJYBVYjjyRuEM7EK9c9BzpKD7w?e=MllfhK) | v2018-apptek | superset of parallel data, with subtitle breaks and document meta-info on genre, automatically predicted line breaks |

#### Development and Evaluation Data
Participants are asked to automatically subtitle in German and/or Arabic two kinds of audio-visual documents, where the spoken language is always English: *(1)* ITV entertainment series and *(2)* news, news talk, financial news from the Bloomberg/Asharq platform.

Audio-visual documents of development and evaluation sets are and will be provided in MP4 format; subtitles of development sets are released in SRT (SubRip File Format) UTF-8 encoded files, the same format required for submissions.

* [ITV Studios](https://www.itvstudios.com/) is part of ITV Plc, which includes the UK’s largest commercial broadcaster. They create and produce a broad range of programming (drama, entertainment, factual) in 13 countries, which they distribute globally, providing high-quality subtitles. We would like to thank ITV Studios for providing IWLST with samples of their video content for research and evaluation purposes and would like to ask you not to use these videos and/or the accompanying subtitles for any commercial purposes or to make them publicly available on any other website. 

  * As a **dev** set, 7 episodes of 3 different television series, with an approximate duration of 7 hours in total, can be downloaded from [here](https://fbk.sharepoint.com/:u:/s/MTUnit/EZXtQE00-Z5VP5Stmbhw1Y4BI3k6WyppWs0_cSCCBbwjyQ?e=nxIqkf). **Note**: some of the **English** SRT files were created following different subtitling guidelines than the ones used in this evaluation (e.g. they contain subtitles with 3 lines) and are provided for informational purposes only.
  * The **test** set 2025, and the test sets proposed in 2023 and 2024 editions, will be released according to the evaluation campaign schedule.

* [Asharq Bloomberg](https://www.bloomberg.com/) is ... TO BE COMPLETED

* As a **dev** set, 2 recordings of about 2.5 hours each, including actual Asharq News/Bloomberg news content, can be downloaded from [here](https://fbk.sharepoint.com/:u:/s/MTUnit/ESRKAm6saCZAjgNh78K0TW0BkC7uOP7eu1iefelrJANZsA?e=yIPmkI). The archive contains audios, reference Arabic and German subtitles and YAML files which provides the audio segments for which subtitles must be created.
  
### 🔵 SUBTITLE COMPRESSION 🔵
<!-- Details description of the data and links to download -->
Also this year, we propose the simplified sub-track where participants are asked to rephrase subtitles that are non-compliant with the reading speed constraint (> 21 CPS) to make them compliant. In this sub-task, time boundaries do not have to be changed: only the text, in a given time span, has to be compressed when necessary.

The conditions for the sub-track are:
* Participants are provided with original AV docs (the same released for the Automatic Subtitling sub-track) and subtitles to be corrected
* No indication is given on which subtitles need to be corrected: all of them can be processed but participants can decide to process only a portion based on the CPS values, computed with the [subtitle compliance script](https://github.com/hlt-mt/FBK-fairseq/blob/master/examples/speech_to_text/scripts/subtitle_compliance.py) by [Papi et al., 2023](https://doi.org/10.1162/tacl_a_00607). The script computes the CPS values for each block by enabling the option `--sentence-level`. This allows participants to find the uncompliant blocks
* A wide range of solutions can be adopted, without limitations on the training data conditions, and including the use of LLM prompted for text compression (e.g. [chatGPT](https://chat.openai.com/chat))
* The original audio, though potentially helpful, can either be used or not by participants, which can also be transcribed with external tools (e.g. [Whisper](https://github.com/openai/whisper))

The following is an example of a non-conform subtitle block (dashed red) with 35 CPS, thus exceeding the 21 CPS limit, that is replaced by a conform subtitle (dashed green) with 15 CPS. Timestamps remain unchanged while the text has been compressed to not exceed the 21 CPS limit while conveying the same meaning.

<img src="https://raw.githubusercontent.com/IWSLT/IWSLT.github.io/cfaef4837f79eeed997293fb26bda69db91a4079/_pages/2024/shared-tasks/subtitle_example.png" style="max-height:600px;max-width:600px">

\* The texts present in the image are in English only for explanation purposes 

#### Development and Evaluation Data

Subtitles to be corrected will be generated by means of a non-participating system to the Automatic Subtitling track.
<!--
* As a *dev* set, we release a minimal example taken from the EuroParl Interviews (EPI) en-es test set by [Papi et al., 2023](https://doi.org/10.1162/tacl_a_00607).
  * [__The dev set can be downloaded here.__](https://drive.google.com/file/d/1KuL-qI-Sg-OqqiB-QJeN7tCWLVsxKJGn) It contains a non-compliant example with its scores (block by block and overall) and the corresponding compliant version with its score.

* The **test** set 2025 will be released according to the evaluation campaign schedule.
  -->
## Submission

### 🔵 AUTOMATIC SUBTITLING 🔵

* Multiple run submissions are allowed, but participants must explicitly indicate one PRIMARY run; all other run submissions are treated as CONTRASTIVE runs. In the case that none of the runs is marked as PRIMARY, the latest submission (according to the file timestamp) will be used as the PRIMARY run
* Submissions have to be sent as a gzipped TAR archive (see format below)
* Submissions must include both test24 and test25
* Submission files have to be stored as SRT (SubRip File Format) UTF-8 encoded files
* For each element of test sets, provide the subtitles in an SRT file whose name includes the file identifier (number) of the video

TAR archive file structure:
```
< UserID >/IWSLT25.Subtitling.< Domain >_< Set >_< VdId >.< Lang >.< UserID >.primary.srt 
  /IWSLT24.Subtitling.< Domain >_< Set >_< VdId >.< Lang >.< UserID >.contrastive1.srt  
  /IWSLT24.Subtitling.< Domain >_< Set >_< VdId >.< Lang >.< UserID >.contrastive2.srt  
  /...  
```
where:
```
< UserID > = user ID of participant; use the short name chosen in the registration form
< Set > = one of {tst25, tst24, tst23}
< VdId > = numeric identifier of the video
< Domain > = one of {ITV, Asharq}
< Lang > = one of {en-ar.ar, en-de.de} (ISO 639-1 two-letter codes of languages)
```
Example: 
```
FBK/IWSLT25.Subtitling.ITV_tst24_15.en-de.de.FBK.primary.srt
```

Submissions must be sent as an email attachment to these two addresses:  
* *cettolo AT fbk DOT eu*  
* *ematusov AT apptek DOT com*

The email should also include the following information:

* Institute/Company:
* Contact Person:
* Email:
* Track: Automatic Subtitling
* Data condition: Constrained/Unconstrained
* Brief abstract about the system:
* Do you want to make your submissions freely available for research purposes? (yes/no)

### 🔵 SUBTITLE COMPRESSION 🔵

* Submission files have to be stored as SRT (SubRip File Format) UTF-8 encoded files as the original input.
  * __ONLY CHANGES REGARDING THE TEXTUAL CONTENT ARE ADMITTED, THE TIMESTAMP OF THE SUBTITLES CAN NOT BE CHANGED!__
* For each element of test sets, provide the subtitles in an SRT file whose name includes the file identifier (number) of the video.
* Submissions have to be sent as a gzipped TAR archive.
* Multiple run submissions are allowed, but participants must explicitly indicate one PRIMARY run; all other run submissions are considered CONTRASTIVE runs. In the case that none of the runs is marked as PRIMARY, the latest submission (according to the file timestamp) will be used as the PRIMARY run.

TAR archive file structure:
```
< UserID >/IWSLT25.SubtitleCompression.< VdId >.< Lang >.< UserID >.primary.srt 
  /IWSLT25.SubtitleCompression.< VdId >.< Lang >.< UserID >.contrastive1.srt  
  /IWSLT25.SubtitleCompression.< VdId >.< Lang >.< UserID >.contrastive2.srt  
  /...  
```
where:
```
< UserID > = user ID of the participant; use the short name chosen in the registration form
< VdId > = numeric identifier of the video
< Lang > = one of {en-ar.ar, en-de.de} (ISO 639-1 two-letter codes of languages)
```
Example: 
```
FBK/IWSLT25.SubtitleCompression.15.en-de.de.FBK.primary.srt
```

Submissions must be sent as an email attachment to these two addresses:  
* *cettolo AT fbk DOT eu*  
* *ematusov AT apptek DOT com*

The email should also include the following information:

* Institute/Company:
* Contact Person:
* Email:
* Track: Subtitle Compression
* Brief abstract about the system/method:
* Do you want to make your submissions freely available for research purposes? (yes/no)


## Evaluation

__DISCLAIMER__: It is expected that participants will use only the audio track from the provided videos (dev and test sets), the 
video track being of low quality and provided primarily as a means to verify time synchronicity and other aspects of displaying s
ubtitles on the screen.

### 🔵 AUTOMATIC SUBTITLING 🔵

The evaluation of subtitling quality is a complex problem on its own since both the translation quality and the compliance with subtitling constraints have to be considered at the same time. 
We adopt the following metrics, where limits of acceptability for the conformity metrics (LPB, CPS, CPL) are set following the [TED guidelines](https://www.ted.com/participate/translate/subtitling-tips):
* [**SubER**](https://github.com/apptek/SubER): the **primary metric** of the task, for measuring the overall quality of automatically generated subtitles
* [**BLEU**](https://github.com/mjpost/sacrebleu) and [**BLEURT**](https://github.com/google-research/bleurt): for measuring the translation quality, automatic subtitles will be realigned to the reference subtitles using [mwerSegmenter](https://www-i6.informatik.rwth-aachen.de/web/Software/mwerSegmenter.tar.gz) ([Matusov et al., 2005](https://aclanthology.org/2005.iwslt-1.19.pdf)) before running these metrics
* **LPB**: the percentage of subtitles not exceeding 2 lines per subtitle, computed with the [subtitle compliance script](https://github.com/hlt-mt/FBK-fairseq/blob/master/examples/speech_to_text/scripts/subtitle_compliance.py) ([Papi et al., 2023](https://doi.org/10.1162/tacl_a_00607))
*  **CPS**: the percentage of subtitles not exceeding 21 characters per second, computed with the [subtitle compliance script](https://github.com/hlt-mt/FBK-fairseq/blob/master/examples/speech_to_text/scripts/subtitle_compliance.py) ([Papi et al., 2023](https://doi.org/10.1162/tacl_a_00607))
  
Scoring will be case-sensitive and will include the punctuation.

### 🔵 SUBTITLE COMPRESSION 🔵

For the subtitle compression sub-track, the following metrics will be used:
* **CPS**: the percentage of subtitles not exceeding 21 characters per second, computed with the [subtitle compliance script](https://github.com/hlt-mt/FBK-fairseq/blob/master/examples/speech_to_text/scripts/subtitle_compliance.py) ([Papi et al., 2023](https://doi.org/10.1162/tacl_a_00607));
* [**BLEURT**](https://github.com/google-research/bleurt) for measuring the translation quality.
  
BLEURT and CPS will be both considered as **primary scores** since the texts should be compressed without significantly impacting their quality.

Scoring will be case-sensitive and will include the punctuation.

## Organizers

<!-- List of organizers' names and affiliations -->
* Mauro Cettolo, FBK
* Evgeny Matusov, AppTek
* Matteo Negri, FBK
* Marco Turchi, Zoom Video Communications
* Patrick Wilken, AppTek


## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair(s):   
* Mauro Cettolo, FBK, Italy
* Evgeny Matusov, AppTek, Germany

Discussion: <iwslt-evaluation-campaign@googlegroups.com>
