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

Details coming very soon!

<!-- Description the task, the languages, and the type of data -->

In recent years, the task of automatically creating subtitles for audiovisual content in another language has gained a lot of attention, as we have seen a surge in the amount of movies, series and user-generated videos which are being streamed and distributed all over the world. 
The task of automatic subtitling is multi-faceted: starting from the speech, not only the translation has to be generated, but it must be segmented into subtitles compliant with constraints that ensure high-quality user experience, like a proper reading speed, synchrony with the voices, maximum number of subtitle lines and characters per line, etc.
For the first time, this year IWSLT proposes a specific task on automatic subtitling, where participants are asked to generate subtitles in German and/or Spanish of three kinds of audiovisual documents, featuring different levels of complexity, starting from English speech.

The evaluation of subtitling quality is a complex problem on its own, since both the translation quality and the compliance with subtitling constraints have to be considered at the same time. The recently proposed SubeER and Sigma are the automatic metrics that will be used for assessing the quality of automatically generated subtitles, together with standard translation quality metrics; moreover, they will be complemented with some explicit compliance measures, as detailed below.
Most audio visual companies define their own subtitling guidelines, which can differ slightly from each other. Participants are asked to generate subtitles following some of the tips listed by [TED](https://www.ted.com/participate/translate/subtitling-tips), in particular:
* never use more than two lines per subtitle
* lines cannot exceed 42 characters, white spaces included
* the maximum subtitle reading speed is 21 characters / second


## Data

Data will be released in January.

<!-- Details description of the data and links to download -->


## Baselines

<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->


## Submission

<!-- Description of expected submission format and submission instructions -->


## Automatic Evaluation

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

* Subtitle quality vs. reference subtitles:
  * SubER, primary metric, used also for ranking ([paper](https://aclanthology.org/2022.iwslt-1.1.pdf), [code](https://github.com/apptek/SubER))
  * Sigma ([paper](https://aclanthology.org/2022.lrec-1.328.pdf), [code](https://github.com/fyvo/EvalSubtitle))

* Translation quality vs. reference translations:
  * BLEU, CHRF (via [sacrebleu](https://github.com/mjpost/sacrebleu) version 2.3.1)
  * [COMET](https://github.com/Unbabel/COMET) (model: wmt20-comet-da)
  * Automatic subtitles will be realigned to the reference subtitles using mwerSegmenter ([Matusov et al., 2005](https://aclanthology.org/2005.iwslt-1.19.pdf)) before running sacrebleu and COMET

* Subtitle compliance:
    * Rate of subtitles with more than two lines
    * Rate of lines longer than 42 characters (white spaces included)
    * Rate of subtitles with reading speed higher than 21 characters / second


## Organizers

<!-- List of organizers' names and affiliations -->


## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair:   
Discussion: <iwslt-evaluation-campaign@googlegroups.com>
