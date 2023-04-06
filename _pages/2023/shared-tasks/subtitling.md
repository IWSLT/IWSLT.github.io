---
permalink: /2023/subtitling
title: "Subtitling track"
toc: true
toc_sticky: true
---

<!--
Markdown notes: comments can be formed as in this example;
bulleted lines start with a - ;
if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line
-->

[Last update: Apr 6, 2023]


## Description

<!-- Description the task, the languages, and the type of data -->

In recent years, the task of automatically creating subtitles for audiovisual content in another language has gained a lot of attention, as we have seen a surge in the amount of movies, series and user-generated videos which are being streamed and distributed all over the world. 
The task of automatic subtitling is multi-faceted: starting from the speech, not only the translation has to be generated, but it must be segmented into subtitles compliant with constraints that ensure high-quality user experience, like a proper reading speed, synchrony with the voices, maximum number of subtitle lines and characters per line, etc.
For the first time, this year IWSLT proposes a specific task on automatic subtitling, where participants are asked to generate subtitles in German and/or Spanish of three kinds of audiovisual documents, featuring different levels of complexity, starting from English speech.

The evaluation of subtitling quality is a complex problem on its own, since both the translation quality and the compliance with subtitling constraints have to be considered at the same time. The recently proposed SubeER and Sigma metrics will be used for assessing the quality of automatically generated subtitles, together with standard translation quality metrics; moreover, they will be complemented with some explicit compliance measures, as detailed below.
Most audio visual companies define their own subtitling guidelines, which can differ slightly from each other. Participants are asked to generate subtitles according to some of the tips listed by [TED](https://www.ted.com/participate/translate/subtitling-tips), in particular:
* never use more than two lines per subtitle
* lines cannot exceed 42 characters, white spaces included
* the maximum subtitle reading speed is 21 characters / second

It is expected that participants will use only the audio track from the provided videos (dev and test sets), the video track being of low quality and provided primarily as a means to verify time synchronicity and other aspects of displaying subtitles on screen.

## Languages

The task involves the processing of audio-video documents for two language pairs: 
* English→German
* English→Spanish

## Training and Data Conditions

<!-- Details description of the data and links to download -->

A **constrained** setup is proposed as the official training data condition, in which the allowed training data is limited to a medium-sized framework in order to keep the training time and resource requirements manageable. In order to allow also the participation of teams equipped with high computational power and effective in-house solutions built on additional resources, an **unconstrained** setup without data restrictions is also proposed.

* **Constrained** training: Under this condition, the allowed training resources are the following ones (note that the list does not include any pre-trained language model):

| Data type | src lang | tgt lang | Training corpus (URL) | Version | Comment
| --- | :---: | :---: | --- | --- | --- |
| speech | en | -- | [LibriSpeech ASR corpus](http://www.openslr.org/12/) | v12 | includes translations into *pt*, not to be used
| speech | en | -- | [How2](https://github.com/srvk/how2-dataset) | na | |
| speech | en | -- | [Mozilla Common Voice](https://commonvoice.mozilla.org/en/datasets) | v11.0  | |
| speech | en | -- | [TED LIUM](https://lium.univ-lemans.fr/en/ted-lium3/) | V2/V3 | |
| speech | en | -- | [Vox Populi](https://github.com/facebookresearch/voxpopuli) | na | |
| speech-to-text-parallel | en | de | [MUST-C](https://ict.fbk.eu/must-c/) | v1.2/v2.0/v3.0 | a new version of MuST-C en-de has been released, check it out! |
| speech-to-text-parallel | en | de | [MUST-Cinema](https://ict.fbk.eu/must-cinema/) | v1.0 | with subtitle and line breaks |
| speech-to-text-parallel | en | es | [MUST-C](https://ict.fbk.eu/must-c/) | v1.2 | same as MUST-Cinema below but without subtitle breaks |
| speech-to-text-parallel | en | es | [MUST-Cinema](https://ict.fbk.eu/must-cinema/) | v1.0 | with subtitle and line breaks |
| speech-to-text-parallel | en | de | [Speech Translation TED corpus](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/corpus/iwslt-corpus.zip) | na | |
| speech-to-text-parallel | en | de | [CoVoST](https://github.com/facebookresearch/covost) | v2 | only German translation, no English transcription |
| speech-to-text-parallel | en | de | [Europarl-ST](https://www.mllp.upv.es/europarl-st/) | v1.1 | |
| speech-to-text-parallel | en | es | [Europarl-ST](https://www.mllp.upv.es/europarl-st/) | v1.1 | |
| text-parallel | en | de | [Europarl](https://www.statmt.org/europarl/v10/training/europarl-v10.de-en.tsv.gz) | v10 | |
| text-parallel | en | es | [Europarl](https://object.pouta.csc.fi/OPUS-Europarl/v8/tmx/en-es.tmx.gz) | v8 | |
| text-parallel | en | de | [NewsCommentary](https://data.statmt.org/news-commentary/v16/training/news-commentary-v16.de-en.tsv.gz) | v16 | |
| text-parallel | en | es | [NewsCommentary](https://data.statmt.org/news-commentary/v16/training/news-commentary-v16.en-es.tsv.gz) | v16 | |
| text-parallel | en | de | [OpenSubtitles](https://apptek930-my.sharepoint.com/:u:/g/personal/ematusov_apptek_com/ESYWN8_BzeJAmBv4GcRapbsBeLpmLOd699qBc9_WG7Gifw?e=Bk6UWh) | v2018 apptek | partially re-aligned, filtered, with document meta-information on genre |
| text-parallel | en | es | [OpenSubtitles](https://apptek930-my.sharepoint.com/:u:/g/personal/ematusov_apptek_com/EafNtfaI0yNKgsoDIDTsEK8BelStVZVsZIrQcwjgTx5diA?e=BT97yx) | v2018 apptek | partially re-aligned, filtered, with document meta-information on genre |
| text-parallel | en | de | [TED2020](https://object.pouta.csc.fi/OPUS-TED2020/v1/tmx/de-en.tmx.gz) | v1 | |
| text-parallel | en | es | [TED2020](https://object.pouta.csc.fi/OPUS-TED2020/v1/tmx/en-es.tmx.gz) | v1 | |
| text-parallel | en | es | [Tatoeba](https://object.pouta.csc.fi/OPUS-Tatoeba/v2022-03-03/tmx/en-es.tmx.gz) | v2022-03-03 | |
| text-parallel | en | de | [Tatoeba](https://object.pouta.csc.fi/OPUS-Tatoeba/v2022-03-03/tmx/de-en.tmx.gz) | v2022-03-03 | |
| text-parallel | en | es | [ELRC-CORDIS_News](https://object.pouta.csc.fi/OPUS-ELRC-CORDIS_News/v1/tmx/en-es.tmx.gz) | v1 | |
| text-parallel | en | de | [ELRC-CORDIS_News](https://object.pouta.csc.fi/OPUS-ELRC-CORDIS_News/v1/tmx/de-en.tmx.gz) | v1 | |
| text-monolingual | -- | de | [OpenSubtitles with subtitle breaks](https://drive.google.com/file/d/1LCU_3dff7l88k20BfoPFLydhOil3dtRl/view?usp=sharing) | v2018-apptek | superset of parallel data, with subtitle breaks and document meta-info on genre, automatically predicted line breaks |
| text-monolingual | -- | es | [OpenSubtitles with subtitle breaks](https://drive.google.com/file/d/1xxZnlvF8ds8KBnMnHnRoPzcMP0mRTkuH/view?usp=sharing) | v2018-apptek | superset of parallel data, with subtitle breaks and document meta-info on genre, automatically predicted line breaks |


* **Unconstrained** training: any resource, pre-trained language models included, can be used with the exception of evaluation sets


## Development and Evaluation Data

Participants are asked to automatically subtitle in German and/or Spanish three kinds of audio-visual documents, where the spoken language is always English, featuring different levels of complexity: (i) TED talks from the MuST-Cinema corpus, (ii) press interviews from the Multimedia Centre of the European Parliament (EUROPARLTV) and (iii) commercial contents, in particular Peloton physical training videos and ITV entertainment series.

Audio-visual documents of development and evaluation sets are and will be provided in MP4 format; subtitles of development sets are released in SRT (SubRip File Format) UTF-8 encoded files, the same format required for submissions.

* [MuST-Cinema](https://ict.fbk.eu/must-cinema/) is a Multilingual Speech-to-Subtitles corpus released in 2020. It comprises audio recordings from English TED Talks, automatically aligned at the sentence level with their manual transcriptions and translations (into seven languages including German and Spanish) marked with subtitle breaks. 
  * As **dev** set, 17 video recordings and subtitles (in English, German and Spanish) of the TED talks defining the evaluation set of the Offline Speech Translation task at IWSLT 2022 (total duration: about 4 hours) can be downloaded from [here](https://drive.google.com/file/d/1rYeHoaIXEhxVeU22Cah_EuEQOzyvK2ob/view?usp=share_link).
  * The **test** set consists of video recordings of 14 TED talks for a total duration of about 80 minutes, can be downloaded from [here](https://drive.google.com/file/d/1_q8q_8glECzvtjYAp1vLHzTx5HBm7Ov7/view?usp=share_link)

* [EUROPARLTV](https://multimedia.europarl.europa.eu/en) is a repository of video recordings related to the European Parliament activities that includes messages of the members, interviews, press conferences, debates, etc. Additional infos on the benchmark, terms for its use and contacts can be found in this [README](https://drive.google.com/file/d/1cbFrsdHWOwLegI9Nwgw23owQAfZtL_FS/view?usp=share_link). 
  * As **dev** set, 12 video recordings and subtitles (in German and Spanish; English transcriptions/subtitles are available only for 5 documents out of 12) for a total duration of about 1 hour can be downloaded from [here](https://drive.google.com/file/d/1Jm3tqAxVgATlV0S9IxxsnDxbnFLljFkZ/view?usp=share_link).
  * The **test** set consists of 10 video recordings for a total duration of about 1 hour, can be downloaded frome [here](https://drive.google.com/file/d/11uav5FKzcDS10dR4OBp7oPNdRGnLt4qa/view?usp=share_link)

* [Peloton](https://www.onepeloton.com/) is a US company that offers fitness training equipment as well as on-line fitness classes which are provided with subtitles in different languages. Peloton is interested in research related to the use of automated subtitling technology in their translation workflows. We would like to thank Peloton for providing IWSLT with samples of their videos for research and evaluation purposes and would like to ask you not to use these videos or subtitles for any commercial purposes or make them publicly available on any other website.  

  * As a **dev** set, 9 recordings of fitness training videos (mostly single-speaker - the fitness instructor) and corresponding subtitles (in English, German and Spanish) for a total duration of about 4 hours can be downloaded from [here](https://drive.google.com/file/d/1zFDJCRwD8ID-SKl1L0qCq4L4Qc7MuwYO/view?usp=sharing). **Note**: the **English** SRT files are **not** properly segmented according to the usual subtitle and line segmentation guidelines and are provided for informational purposes only. The German and Spanish SRT files are the ones created by professional subtitle translators.
  * The **test** set with 8 videos of similar content (but potentially different speakers) can be downloaded from [here](https://drive.google.com/file/d/1wIMWTtCP6K50CgnaeWNS3sKxwCULZEWL/view?usp=share_link)

* [ITV Studios](https://www.itvstudios.com/) is part of ITV Plc, which includes the UK’s largest commercial broadcaster. They create and produce a broad range of programming (drama, entertainment, factual) in 13 countries, which they distribute globally, providing high-quality subtitles. We would like to thank ITV Studios for providing IWLST with samples of their video content for research and evaluation purposes and would like to ask you not to use these videos and/or the accompanying subtitles for any commercial purposes or make them publicly available on any other website. 

  * As a **dev** set, 7 episodes of 3 different television series, with an approximate duration of 7 hours in total, can be downloaded from [here](https://drive.google.com/file/d/1LLqaq40gG8V0PpV_nLhgzrJFOG_wDNQ-/view?usp=sharing). **Note**: some of the **English** SRT files were created following different subtitling guidelines than the ones used in this evaluation (e.g. they contain subtitles with 3 lines) and are provided for informational purposes only.
  * The **test** set with 7 episodes from entertainment series, possibly, but not necessarily from the same ones, can be downloaded from [here](https://drive.google.com/file/d/18FSrKnjj7K6_d8z8cjzb4ujFUdBfetcy/view?usp=share_link)

When available, English subtitles of development sets are released only for convenience of participants; it is not required to generate them for the final evaluation.


## Submission Guidelines

<!-- Description of expected submission format and submission instructions -->

* Multiple run submissions are allowed, but participants must explicitly indicate one PRIMARY run. All other run submissions are treated as CONTRASTIVE runs. In the case that none of the runs is marked as PRIMARY, the latest submission (according to the file time-stamp) will be used as the PRIMARY run
* Submissions have to be submitted as a gzipped TAR archive (see format below)
* Each run has to be stored in SRT (SubRip File Format) UTF-8 encoded files
* For each video of test sets, provide the subtitles in an SRT file whose name includes the file identifier (number) of the video
* Scoring will be case-sensitive and will include the punctuation

TAR archive file structure:
```
< UserID >/< Set >_< VdId >.< Lang >.< UserID >.primary.srt 
  /< Set >_< VdId >.< Lang >.< UserID >.contrastive1.srt  
  /< Set >_< VdId >.< Lang >.< UserID >.contrastive2.srt  
  /...  
```
where:
```
< UserID > = user ID of participant; use the short name chosen in the registration form
< Set > = IWSLT23.Subtitling.< Domain >tst
< VdId > = numeric identifier of the video
< Domain > = one of {EPTV, TED, Peloton, ITV}
< Lang > = one of {en-de.de, en-es.es} (ISO 639-1 two-letter codes of languages)
```
Example: 
```
FBK/IWSLT23.Subtitling.TEDtst_13587.en-de.de.FBK.primary.srt
```

Submissions must be sent as an email attachment to these two addresses:  
* *cettolo AT fbk DOT eu*  
* *ematusov AT apptek DOT com*

The email should also include the following information:

* Institute/company:
* Contact Person:
* Email:
* Data condition: Constrained/Unconstrained
* Brief abstract about the system:
* Do you want to make your submissions freely available for research purposes? (yes/no)


## Automatic Evaluation

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

The evaluation will be carried out from three perspectives, subtitle quality, translation quality and subtitle compliance, through the following automatic measures:

* Subtitle quality vs. reference subtitles:
  * SubER, primary metric, used also for ranking ([paper](https://aclanthology.org/2022.iwslt-1.1.pdf), [code](https://github.com/apptek/SubER))
  * Sigma ([paper](https://aclanthology.org/2022.lrec-1.328.pdf), [code](https://github.com/fyvo/EvalSubtitle))

* Translation quality vs. reference translations:
  * BLEU, CHRF (via [sacreBLEU](https://github.com/mjpost/sacrebleu) version 2.3.1)
  * [COMET](https://github.com/Unbabel/COMET) (model: wmt20-comet-da)  
  Automatic subtitles will be realigned to the reference subtitles using [mwerSegmenter](https://www-i6.informatik.rwth-aachen.de/web/Software/mwerSegmenter.tar.gz) ([Matusov et al., 2005](https://aclanthology.org/2005.iwslt-1.19.pdf)) before running sacreBLEU and COMET

* Subtitle compliance:  
  * Rates of 
    * subtitles with more than two lines
    * lines longer than 42 characters (white spaces included)
    * subtitles with reading speed higher than 21 characters / second  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;([paper](https://arxiv.org/abs/2209.13192), [code](https://github.com/hlt-mt/FBK-fairseq/blob/master/examples/speech_to_text/scripts/subtitle_compliance.py))

## Organizers

<!-- List of organizers' names and affiliations -->

* Mauro Cettolo, FBK
* Evgeny Matusov, AppTek
* Mattia Di Gangi, AppTek
* Patrick Wiken, AppTek
* Matteo Negri, FBK
* Marco Turchi, Zoom Video Communications

## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chairs: 
* Mauro Cettolo, FBK, Italy
* Evgeny Matusov, AppTek, Germany   

Discussion: <iwslt-evaluation-campaign@googlegroups.com>
