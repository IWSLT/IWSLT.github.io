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
  * SubER, primary metric, used also for ranking (paper, code)
  * Sigma (paper, code)

* Translation quality vs. reference translations:
  * BLEU, CHRF (via sacrebleu version 2.3.1)
  * COMET (model: wmt20-comet-da)
  * Automatic subtitles will be realigned to the reference subtitles using mwerSegmenter (Matusov et al., 2005) before running sacrebleu and COMET

* Subtitle compliance:
  * Rates of:
    * subtitles with more than two lines
    * lines longer than 42 characters (white spaces included)
    * subtitles with reading speed higher than 21 characters / second


## Organizers

<!-- List of organizers' names and affiliations -->


## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair:   
Discussion: <iwslt-evaluation-campaign@googlegroups.com>
