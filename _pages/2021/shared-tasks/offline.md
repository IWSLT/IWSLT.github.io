---
permalink: /2021/offline
title: "Offline Speech Translation"
---

## Description


<!-- the task, the languages, and the type of data -->

Recent advances in deep learning are giving the possibility to address traditional NLP tasks in a new and completely different manner. One of these tasks is spoken language translation (SLT). For years, SLT has been addressed by cascading an automatic speech recognition (ASR) and a machine translation (MT) system. Recent trends rely on using a single neural network to directly translate the input audio signal in one language into a text in a different language without intermediate symbolic representations, e.g., transcriptions. \\

The goal of the **Offline Speech Translation Task** is to examine automatic methods for translating audio speech in one language into text in the target language. This has to be done either by exploiting cascaded solutions or end-to-end approaches. Last year's results of IWSLT 2020 have shown that the performance of end-to-end models is approaching and even overtaking the results of cascade solutions. Hence, the question we want to answer this year is: **is the cascaded solution still the dominant technology in spoken language translation?**

In continuity with last year, the task addresses the translation of TED talks from English into German. **One test set will be released containing the same talks, respectively with and without audio segmentation.**

The system's performance will be evaluated with respect to their capability to produce translations similar to the target-language references. Such similarity will be measured in terms of multiple automatic metrics: BLEU, TER, BEER and characTER. The submitted runs will be ranked based on the BLEU calculated on the test set by using automatic resegmentation of the hypothesis based on the reference translation by [mwerSegmenter](https://www-i6.informatik.rwth-aachen.de/web/Software/mwerSegmenter.tar.gz). The detailed evaluation script can be found in the [SLT.KIT](https://github.com/isl-mt/SLT.KIT/blob/master/scripts/evaluate/Eval.sh).


## Evaluation Conditions

Both cascade and end-to-end models will be evaluated. We kindly ask each participant to specify at submission time if a cascade or an end-to-end model has been used.

In this task, we use the following definition of end-to-end model:
  * No intermediated discrete representations (source language like in cascade or target languages like in rover)
  * All parameters/parts that are used during decoding need to be trained on the end2end task (may also be trained on other tasks -> multitasking ok, LM rescoring is not ok)


## Test Data

This year two versions of the same TED talks are released:
  - The audio files are segmented into sentence-like segmentation using automatic tools.
  - The audio files are NOT segmented.

To measure the progress in the ST field, each participant is required to translate also the 2019 test set that is still blind. Similar to this year test set, the 2019 test set will be made available with and without automatic segmentation.



## Organizers

<!-- list of names and affiliations -->


<!-- Markdown notes: comments can be formed as above; bulleted lines start with a - ; if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line -->
