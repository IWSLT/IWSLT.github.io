---
permalink: /2026/subtitling
title: "Subtitling track"
toc: true
toc_sticky: true
---

<!--
Markdown notes: comments can be formed as in this example;
bulleted lines start with a - ;
if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line
-->
<span style="color:red">**PAGE UNDER CONSTRUCTION** </span>

[Last update: Jan 15, 2026]

## Description

<!-- Description the task, the languages, and the type of data -->

In recent years, the task of automatically creating subtitles for audiovisual content in another language has gained increasing attention, as we have seen a surge in the amount of movies, series, and user-generated videos that are being streamed and distributed all over the world. The task is a multi-faceted one: not only the translation has to be generated from speech, which is right on target for IWSLT, but also the subtitling constraints have to be respected (i.e. a proper reading speed, synchrony with the voices, maximum number of subtitle lines and characters per line).

As in past editions, in 2026 we propose the <span style="color:blue">**Automatic Subtitling**</span> track, where participants are asked to generate subtitles of different kinds of audiovisual documents, starting from English speech. 
The novelty this year is the set of target languages: in addition to **Arabic** and **German**, already offered in edition 2025, this year **Chinese** and **Japanese** have been added.

## Training and Data Conditions

Two training data conditions are proposed:
* **constrained**: the official training data condition, in which the allowed training data is limited to a medium-size
d framework (described below) in order to keep the training time and resource requirements manageable
* **unconstrained**: a setup without data restrictions (any resource, pre-trained language models can be used) to allow
 also the participation of teams equipped with high computational power and effective in-house solutions built on addit
ional resources

### Training Data allowed for Constrained Conditions

| Data type | src lang | tgt lang | Training corpus (URL) | Version | Comment |
| --- | :---: | :---: | --- | --- | --- |
| speech | en | -- | [LibriSpeech ASR corpus](http://www.openslr.org/12/) | v12 | includes translations into *pt*, not 
to be used |
| speech | en | -- | [How2](https://github.com/srvk/how2-dataset) | na | |
| speech | en | -- | [Mozilla Common Voice](https://commonvoice.mozilla.org/en/datasets) | v11.0  | |
| speech | en | -- | [Vox Populi](https://github.com/facebookresearch/voxpopuli) | na | |
| speech-to-text-parallel | en | ar, de, zh | [CoVoST](https://github.com/facebookresearch/covost) | v2 | only translations, no English transcription |
| speech-to-text-parallel | en | de | [Europarl-ST](https://www.mllp.upv.es/europarl-st/) | v1.1 | |
| text-parallel | en | ar | [UNPC](https://object.pouta.csc.fi/OPUS-UNPC/v1.0/tmx/ar-en.tmx.gz) | v1.0 | |
| text-parallel | en | de | [Europarl](https://www.statmt.org/europarl/v10/training/europarl-v10.de-en.tsv.gz) | v10 | |
| text-parallel | en | ar | [Tanzil](https://object.pouta.csc.fi/OPUS-Tanzil/v1/tmx/ar-en.tmx.gz) | v1 | |
| text-parallel | en | ar, de, zh | [NewsCommentary](https://data.statmt.org/news-commentary/v16/training/news-commentary-v18.ar-en.tsv.gz) | v18 | |
| text-parallel | en | ar | [GlobalVoices](https://object.pouta.csc.fi/OPUS-GlobalVoices/v2018q4/tmx/ar-en.tmx.gz) | v2018q4 | | 
| text-parallel | en | ar, de, zh | [OpenSubtitles](https://object.pouta.csc.fi/OPUS-OpenSubtitles/v2018/tmx/ar-en.tmx.gz) | v2018 | |
| text-parallel | en | de | [OpenSubtitles](https://apptek930-my.sharepoint.com/:u:/g/personal/ematusov_apptek_com/ESYWN8_BzeJAmBv4GcRapbsBeLpmLOd699qBc9_WG7Gifw?e=Bk6UWh) | v2018 apptek | partially re-aligned, filtered, with document meta-information on genre |
| text-parallel | en | ar, de, zh | [Tatoeba](https://object.pouta.csc.fi/OPUS-Tatoeba/v2023-04-12/tmx/ar-en.tmx.gz) | v2023-04-12 | |
| text-parallel | en | ar | [ELRC_2922](https://object.pouta.csc.fi/OPUS-ELRC_2922/v1/tmx/ar-en.tmx.gz) | v1 | |
| text-parallel | en | de | [ELRC-CORDIS_News](https://object.pouta.csc.fi/OPUS-ELRC-CORDIS_News/v1/tmx/de-en.tmx.gz) | v1 | |
| text-monolingual | -- | de | [OpenSubtitles with subtitle breaks](https://fbk.sharepoint.com/:u:/s/MTUnit/Efm0lF0ITTJeBM0ZmjlAKeEBu9CE33SCvb05S1tAq2AkSA?e=FHbZci) | v2018-apptek | superset of parallel data, with subtitle breaks and document meta-info on genre, automatically predicted line breaks |

## Development and Evaluation Data

Participants are asked to automatically subtitle three kinds of audio-visual documents, where the spoken language is always English: 
* **ITV** entertainment series, to be subtitled in **Chinese**, **German** and/or **Japanese**
* news programs from the **Asharq-Bloomberg** platform, to be subtitled in **Arabic**, **Chinese**, **German** and/or **Japanese**
* recordings from the **YODAS** YouTube dataset, to be subtitled in **Chinese**, **German** and/or **Japanese**

Audio-visual documents of development and evaluation sets are and will be provided in MP4 format; subtitles of development sets are released in SRT (SubRip File Format) UTF-8 encoded files, the same format required for submissions.

* [ITV Studios](https://www.itvstudios.com/) is part of ITV Plc, which includes the UK's largest commercial broadcaster. They create and produce a broad range of programming (drama, entertainment, factual) in 13 countries, which they distribute globally, providing high-quality subtitles. We would like to thank ITV Studios for providing IWLST with samples of their video content for research and evaluation purposes and would like to ask you not to use these videos and/or the accompanying subtitles for any commercial purposes or to make them publicly available on any other website. 

  * As a **dev** set, 7 episodes of 3 different television series, with an approximate duration of 7 hours in total, can be downloaded from [here](https://fbk.sharepoint.com/:u:/s/MTUnit/EZXtQE00-Z5VP5Stmbhw1Y4BI3k6WyppWs0_cSCCBbwjyQ?e=nxIqkf). **Note 1**: some of the **English** SRT files were created following different subtitling guidelines than the ones used in this evaluation (e.g. they contain subtitles with 3 lines) and are provided for informational purposes only. **Note 2**: reference Spanish subtitles can be ignored since **German** is the only target language considered for ITV.
  * The **test** set 2026 will be released according to the scheduling.

* [Asharq Business with Bloomberg](https://asharqbusiness.com/) is part of SRMG, the largest integrated media group in the MENA (Middle East and North Africa) region. An exclusive content agreement with 'Bloomberg Media' powers this distinguished business news multi-platform, drawing on Bloomberg's comprehensive coverage from more than 2,700 journalists and analysts globally. Asharq Business with Bloomberg is a leading source for Arabic economic news rich in context and content and unparalleled market data, delivered through a TV channel and across digital and social media platforms.

  * As a **dev** set, 2 recordings of about 2.5 hours each, including actual Asharq-Bloomberg news content, can be downloaded from [here](https://fbk.sharepoint.com/:u:/s/MTUnit/ESRKAm6saCZAjgNh78K0TW0BkC7uOP7eu1iefelrJANZsA?e=yIPmkI). The archive contains a README file with important infos, audios, reference **Arabic** and **German** subtitles, and YAML files which provide the audio segments for which subtitles must be created.
  * The **test** set 2026 will be released according to the scheduling.

* [YODAS](https://huggingface.co/datasets/espnet/yodas) (YouTube-Oriented Dataset for Audio and Speech) is *"a large-scale, multilingual dataset comprising currently over 500k hours of speech data in more than 100 languages, sourced from both labeled and unlabeled YouTube speech datasets.*" Refer to this [paper](https://ieeexplore.ieee.org/abstract/document/10389689) for more details.
  * The **test** set 2026 will be released according to the scheduling.

## Submission

* Multiple run submissions are allowed, but participants must explicitly indicate one PRIMARY run; all other run submissions are treated as CONTRASTIVE runs. In the case that none of the runs is marked as PRIMARY, the latest submission (according to the file timestamp) will be used as the PRIMARY run
* Submissions have to be sent as a gzipped TAR archive (see format below)
* Submissions must include test26 and progressive test sets: for the ITV section, test23, test24 and test25; for the Asharq section, test25
* Submission files have to be stored as SRT (SubRip File Format) UTF-8 encoded files
* For each element of test sets, provide the subtitles in an SRT file whose name includes the file identifier (number) of the video

TAR archive file structure:
```
<UserID>/IWSLT26.Subtitling.<Domain>_<Set>_<VdId>.<Lang>.<UserID>.primary.srt 
  /IWSLT26.Subtitling.<Domain>_<Set>_<VdId>.<Lang>.<UserID>.contrastive1.srt  
  /IWSLT26.Subtitling.<Domain>_<Set>_<VdId>.<Lang>.<UserID>.contrastive2.srt  
  /...  
```
where:
```
<UserID> = user ID of participant; use the short name chosen in the registration form
<Domain> = one of {ITV, Asharq}
<Set>    = one of {tst26, tst25, tst24, tst23} if <Domain>=ITV
         = one of {tst26, tst25} if <Domain>=Asharq
         = tst26 if <Domain>=YODAS
<VdId>   = numeric identifier of the video
<Lang>   = one of {en-de.de,en-ja.ja,en-zh.zh} if <Domain>=ITV or YODAS
         = one of {en-ar.ar,en-de.de,en-ja.ja,en-zh.zh} if <Domain>=Asharq
           (ISO 639-1 two-letter codes of languages)
```
Example: 
```
FBK/IWSLT26.Subtitling.ITV_tst25_22.en-de.de.FBK.primary.srt
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
* Do you agree that the IWSLT organizers may release your submitted system output data under an Apache 2.0 or similar license (depending on licensing details of test sets), to encourage future research? We may exclude your submissions from human evaluation without this consent. (yes/no)



## Evaluation

__DISCLAIMER__: It is expected that participants will use only the audio track from the provided videos (dev and test sets), the  video track being of low quality and provided primarily as a means to verify time synchronicity and other aspects of displaying subtitles on the screen.

The evaluation of subtitling quality is a complex problem on its own since both the translation quality and the compliance with subtitling constraints have to be considered at the same time. 
We adopt the following metrics, where limits of acceptability for the conformity metrics (LPB, CPS, CPL) are set following the [TED guidelines](https://www.ted.com/participate/translate/subtitling-tips):
* [**SubER**](https://github.com/apptek/SubER): the **primary metric** of the task, for measuring the overall quality of automatically generated subtitles
* [**BLEU**](https://github.com/mjpost/sacrebleu) and [**BLEURT**](https://github.com/google-research/bleurt): for measuring the translation quality, automatic subtitles will be realigned to the reference subtitles using [mweralign](https://github.com/mjpost/mweralign) ([Post and Hoang, 2025](https://aclanthology.org/2025.iwslt-1.7/)), which implements a variant of the AS-WER algorithm ([Matusov et al., 2005](https://aclanthology.org/2005.iwslt-1.19.pdf)), before running these metrics
* **LPB**: the percentage of subtitles not exceeding 2 lines per subtitle, computed with the [subtitle compliance script](https://github.com/hlt-mt/FBK-fairseq/blob/master/examples/speech_to_text/scripts/subtitle_compliance.py) ([Papi et al., 2023](https://doi.org/10.1162/tacl_a_00607))
*  **CPS**: the percentage of subtitles not exceeding 21 characters per second, computed with the [subtitle compliance script](https://github.com/hlt-mt/FBK-fairseq/blob/master/examples/speech_to_text/scripts/subtitle_compliance.py) ([Papi et al., 2023](https://doi.org/10.1162/tacl_a_00607))
*  **CPL**: the percentage of subtitles not exceeding 42 characters per line, computed with the [subtitle compliance script](https://github.com/hlt-mt/FBK-fairseq/blob/master/examples/speech_to_text/scripts/subtitle_compliance.py) ([Papi et al., 2023](https://doi.org/10.1162/tacl_a_00607))
  
Scoring will be case-sensitive and will include the punctuation.


## Organizers

* Mauro Cettolo, FBK
* Evgeny Matusov, AppTek
* Matteo Negri, FBK
* Marco Turchi, Zoom Video Communications
* Patrick Wilken, AppTek


## Contact
Chair(s):   
* Mauro Cettolo <cettolo@fbk.edu>, FBK, Italy, 
* Evgeny Matusov <ematusov@apptek.com>, AppTek, Germany

Discussion: <iwslt-evaluation-campaign@googlegroups.com>
