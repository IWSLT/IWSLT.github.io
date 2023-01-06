---
permalink: /2023/offline
title: "Offline track"
toc: true
toc_sticky: true
---

<!--
Markdown notes: comments can be formed as in this example;
bulleted lines start with a - ;
if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line
-->

## Description

Recent advances in deep learning are giving the possibility to address traditional NLP tasks in a new and completely different manner. One of these tasks is spoken language translation (SLT). For years, SLT has been addressed by cascading an automatic speech recognition (ASR) and a machine translation (MT) system. Recent trends rely on using a single neural network to directly translate the input audio signal in one language into a text in a different language without intermediate symbolic representations, e.g., transcriptions.  

The goal of the **Offline Speech Translation Task** is to examine automatic methods for translating audio speech in one language into text in the target language. This has to be done either by exploiting cascaded solutions or end-to-end approaches. The last editions' results have confirmed that the performance of end-to-end models is approaching the results of cascade solutions, however, without identifying the best-performing technology. Moreover, all the recent evaluations have been based on test sets extracted from TED talks. In this controlled scenario, a single speaker acts out a prepared speech without background noise and interaction with other speakers.

<-- To raise the bar and to test current spoken language translation technologies in different conditions, test sets of different complexity are proposed this -->

<-- Hence, the questions we want to answer this year are: **is the cascaded solution still the dominant technology in spoken language translation?**  -->

In addition to answering the question **if the cascade solution is still the dominant technology**, this year we will address an additional research question in the evaluation:
* **Is the current spoken language translation technology able to deal with more complex scenarios (e.g. spontaneous speech, terminology, and dialogues)?** In addition to the classic TED talk test set from English into German, the task introduces two more test sets that face more challenging scenarios:
  * ACL presentations: A single speaker is presenting on a stage and interacts with the audience only in the Q&A at the end of the presentation. Although this is similar to the TED talk scenario, the speech translation system needs to deal with no-native speakers, different accents, terminology, and controlled interaction with a second speaker.
  * Press conferences and interviews: in this scenario, two persons interact on different topics. The speech translation system needs to deal with no-native speakers, different accents, controlled interaction with a second speaker, and spontaneous speeches.

  
The system's performance will be evaluated with respect to their capability to produce translations similar to the target-language references. Such similarity will be measured in terms of multiple automatic metrics: BLEU, TER, BEER and characTER. The submitted runs will be ranked based on the BLEU calculated on the test set by using automatic resegmentation of the hypothesis based on the reference translation by [mwerSegmenter](https://www-i6.informatik.rwth-aachen.de/web/Software/mwerSegmenter.tar.gz). The detailed evaluation script can be found in the [SLT.KIT](https://github.com/isl-mt/SLT.KIT/blob/master/scripts/evaluate/Eval.sh). Moreover, to meet the requests of last year's participants, a human evaluation will be performed on the best performing submission of each participant.
<!-- The guidelines for generating the human translation for TED talks were modified recently, in order to produce shorter translations that better fit for subtitling. Since this task focuses on speech translation without additional constraints, we will produce an additional reference that is generated without additional constraints for the human translators as we did last year. -->


<!-- Description the task, the languages, and the type of data -->


## Data

Data will be released in January.

<!-- Details description of the data and links to download -->


## Baselines

<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->


## Submission

<!-- Description of expected submission format and submission instructions -->


## Evaluation

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->


## Organizers

<!-- List of organizers' names and affiliations -->


## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair:   
Discussion: <iwslt-evaluation-campaign@googlegroups.com>
