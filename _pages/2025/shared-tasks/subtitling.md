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
[Last update: Nov 11, 2024]

## Description

<!-- Description the task, the languages, and the type of data -->

In recent years, the task of automatically creating subtitles for audiovisual content in another language has gained increasing attention, as we have seen a surge in the amount of movies, series, and user-generated videos that are being streamed and distributed all over the world. The task is a multi-faceted one: not only the translation has to be generated from speech, which is right on target for IWSLT, but also the subtitling constraints have to be respected (i.e. a proper reading speed, synchrony with the voices, maximum number of subtitle lines and characters per line).

As in 2024, we propose two sub-tracks:
* **automatic subtitling**: participants are asked to generate subtitles in Arabic and/or German of different kinds of audiovisual documents, featuring different levels of complexity, starting from English speech
* **subtitle compression**: participants are asked to rephrase subtitles that are non-compliant with the reading speed constraint (at most 21 characters / second) to make them compliant

and two language directions:
* 🆕 English &rarr; Arabic
* English &rarr; German

## Training and Data Conditions

### 🔵 AUTOMATIC SUBTITLING 🔵
<!-- Details description of the data and links to download -->
Data will be released in January.

### 🔵 SUBTITLE COMPRESSION 🔵
<!-- Details description of the data and links to download -->
Data will be released in January.

## Submission

<!-- Description of expected submission format and submission instructions -->
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
< Set > = one of {tst25, tst24}
< VdId > = numeric identifier of the video
< Domain > = one of {Peloton, ITV}
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

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

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
