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

## Description

<!-- Description the task, the languages, and the type of data -->

In recent years, the task of automatically creating subtitles for audiovisual content in another language has gained a lot of attention, as we have seen a surge in the amount of movies, series and user-generated videos which are being streamed and distributed all over the world. 
The task of automatic subtitling is multi-faceted: starting from the speech, not only the translation has to be generated, but it must be segmented into subtitles compliant with constraints that ensure high-quality user experience, like a proper reading speed, synchrony with the voices, maximum number of subtitle lines and characters per line, etc.
For the first time, this year IWSLT proposes a specific task on automatic subtitling, where participants are asked to generate subtitles in German and/or Spanish of three kinds of audiovisual documents, featuring different levels of complexity, starting from English speech.

The evaluation of subtitling quality is a complex problem on its own, since both the translation quality and the compliance with subtitling constraints have to be considered at the same time. The recently proposed SubeER and Sigma are the automatic metrics that will be used for assessing the quality of automatically generated subtitles, together with standard translation quality metrics; moreover, they will be complemented with some explicit compliance measures, as detailed below.
Most audio visual companies define their own subtitling guidelines, which can differ slightly from each other. Participants are asked to generate subtitles following some of the tips listed by [TED](https://www.ted.com/participate/translate/subtitling-tips), in particular:
* never use more than two lines per subtitle
* lines cannot exceed 42 characters, white spaces included
* the maximum subtitle reading speed is 21 characters / second

## Languages

The task involves the processing of audio-video documents for two language pairs: English→German and English→Spanish

## Training and Data Conditions

<!-- Details description of the data and links to download -->

A **constrained** setup is proposed as the official training data condition, in which the allowed training data is limited to a medium-sized framework in order to keep the training time and resource requirements manageable. In order to allow also the participation of teams equipped with high computational power and effective in-house solutions built on additional resources, an **unconstrained** setup without data restrictions is also proposed.

* **Constrained** training: Under this condition, the allowed training resources are the following ones (note that the list does not include any pre-trained language model):
  * Speech translation corpora
    * TDB
  * Corpora for ASR training with English transcripts only
    * TBD
  * Parallel text-only corpora
    * TDB
  * Monolingual corpora with subtitle boundaries
    * TBD

* **Unconstrained** training: any resource, pre-trained language models included, can be used with the exception of evaluation sets



## Baselines

<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->


## Submission Guidelines

<!-- Description of expected submission format and submission instructions -->

* Multiple run submissions are allowed, but participants must explicitly indicate one PRIMARY run. All other run submissions are treated as CONTRASTIVE runs. In the case that none of the runs is marked as PRIMARY, the latest submission (according to the file time-stamp) will be used as the PRIMARY run
* Submissions have to be submitted as a gzipped TAR archive (see format below) and sent as an email attachment to TBD
* Each run has to be stored in an SRT (SubRip File Format)
* Scoring will be case-sensitive and will include the punctuation

TAR archive file structure:
```
< UserID >/< Set >.< LangDir >.< UserID >.primary.srt 
  /< Set >.< LangDir >.< UserID >.contrastive1.srt  
  /< Set >.< LangDir >.< UserID >.contrastive2.srt  
  /...  
```
where:
```
< UserID > = user ID of participant; use the short name chosen in the registration form
< Set > = IWSLT23.Subtitling.< Domain >tst
< Domain > = one of {EPTV,TED,Peloton,ITV}
< LangDir > = en-de/es (ISO 639-1 two-letter codes of languages)
```
Example: 
```
FBK/IWSLT23.Subtitling.TEDtst.en-de.FBK.primary.srt
```

All the submissions must be sent to this address: TBD

The email should include the following information:

* Institute/company:
* Contact Person:
* Email:
* Data condition: Constrained/Unconstrained
* Brief abstract about the system:
* Do you want to make your submissions freely available for research purposes? (yes/no)


## Automatic Evaluation

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

* Subtitle quality vs. reference subtitles:
  * SubER, primary metric, used also for ranking ([paper](https://aclanthology.org/2022.iwslt-1.1.pdf), [code](https://github.com/apptek/SubER))
  * Sigma ([paper](https://aclanthology.org/2022.lrec-1.328.pdf), [code](https://github.com/fyvo/EvalSubtitle))

* Translation quality vs. reference translations:
  * BLEU, CHRF (via [sacreBLEU](https://github.com/mjpost/sacrebleu) version 2.3.1)
  * [COMET](https://github.com/Unbabel/COMET) (model: wmt20-comet-da)
  * Automatic subtitles will be realigned to the reference subtitles using mwerSegmenter ([Matusov et al., 2005](https://aclanthology.org/2005.iwslt-1.19.pdf)) before running sacreBLEU and COMET

* Subtitle compliance:
    * Rate of subtitles with more than two lines
    * Rate of lines longer than 42 characters (white spaces included)
    * Rate of subtitles with reading speed higher than 21 characters / second


## Organizers

<!-- List of organizers' names and affiliations -->

* Mauro Cettolo, Fondazione Bruno Kessler
* Evgeny Matusov, AppTek
* Mattia Di Gangi, AppTek
* Patrick Wiken, AppTek
* Matteo Negri, Fondazione Bruno Kessler
* Marco Turchi, Zoom Video Communications

## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair:   
Discussion: <iwslt-evaluation-campaign@googlegroups.com>
