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

<!-- To raise the bar and to test current spoken language translation technologies in different conditions, test sets of different complexity are proposed this -->

<!-- Hence, the questions we want to answer this year are: **is the cascaded solution still the dominant technology in spoken language translation?**  -->

In addition to answering the question **if the cascade solution is still the dominant technology**, this year we will address an additional research question in the evaluation:
* **Is the current spoken language translation technology able to deal with more complex scenarios (e.g. spontaneous speech, terminology, and dialogues)?** In addition to the classic TED talk test set from English into German, the task introduces two more test sets that face more challenging scenarios:
  * ACL presentations: a single speaker is presenting on a stage. Although this is similar to the TED talk scenario, the speech translation system needs to deal with non-native speakers, different accents, various recording quality, terminology, and controlled interaction with a second speaker.
  * Press conferences and interviews: in this scenario, two persons interact on different topics. The speech translation system needs to deal with non-native speakers, different accents, controlled interaction with a second speaker, and spontaneous speeche.

  
The system's performance will be evaluated with respect to their capability to produce translations similar to the target-language references. Such similarity will be measured in terms of multiple automatic metrics: BLEU, TER, BEER and characTER. The submitted runs will be ranked based on the BLEU calculated on the test set by using automatic resegmentation of the hypothesis based on the reference translation by [mwerSegmenter](https://www-i6.informatik.rwth-aachen.de/web/Software/mwerSegmenter.tar.gz). The detailed evaluation script can be found in the [SLT.KIT](https://github.com/isl-mt/SLT.KIT/blob/master/scripts/evaluate/Eval.sh). Moreover, to meet the requests of last year's participants, a human evaluation will be performed on the best performing submission of each participant.
<!-- The guidelines for generating the human translation for TED talks were modified recently, in order to produce shorter translations that better fit for subtitling. Since this task focuses on speech translation without additional constraints, we will produce an additional reference that is generated without additional constraints for the human translators as we did last year. -->


<!-- Description the task, the languages, and the type of data -->


## Evaluation Conditions

Both cascade and end-to-end models will be evaluated. We kindly ask each participant to specify at submission time if a cascade or an end-to-end model has been used.

In this task, we use the following definition of end-to-end model:
  * No intermediated discrete representations (source language like in cascade or target languages like in rover)
  * All parameters/parts that are used during decoding need to be trained on the end2end task (may also be trained on other tasks -> multitasking ok, LM rescoring is not ok)


## Test Data

More information about the test data will be released in January.
{: .notice--info}

<!-- Details description of the data and links to download -->


## Past Editions Development Data

The development data is not segmented using the reference transcript. The archives contain segmentation into sentence-like segmentation using automatic tools. But the participants might also use a different segmentation. The data provided as an archive with the following files ($set e.g. IWSLT.TED.dev2010):
  * $set.en-de.en.xml: Reference transcript (will not be provided for evaluation data)
  * $set.en-de.en.xml: Reference translation (will not be provided for evaluation data)
  * CTM_LIST: Ordered file list containing the ASR Output CTM Files (will not be provided for evaluation data) (Generated by ASR systems that use more data)
  * FILE_ORDER: Ordered file list containing the wav files
  * $set.yaml: This file contains the time steps for sentence-like segments. It is generated by the LIUM Speaker Diarization tool.
  * $set.h5: This file contains the 40-dimensional Filterbank features for each sentence-like segment of the test data created by XNMT.
  * The last two files are created by the following command:
python -m xnmt.xnmt_run_experiments /opt/SLT.KIT/scripts/xnmt/config.las-pyramidal-preproc.yaml

**Development data:**

(Please note that system generated the provided ASR scripts use more training data than allowed for this year's evaluations)
  * [dev2010](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/preprocessed/IWSLT-SLT.dev2010.en-de.tgz)
  * [tst2010](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/preprocessed/IWSLT-SLT.tst2010.en-de.tgz)
  * [tst2013](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/preprocessed/IWSLT-SLT.tst2013.en-de.tgz)
  * [tst2014](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/preprocessed/IWSLT-SLT.tst2014.en-de.tgz)
  * [tst2015](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/preprocessed/IWSLT-SLT.tst2015.en-de.tgz)
  * [tst2018](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/IWSLT-SLT.tst2018.en-de.tgz)
  * [tst2019](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/IWSLT-SLT.tst2019.en-de.tgz)
  * [tst2020](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/IWSLT-SLT.tst2020.en-de.tgz)


## Allowed Training Data

More information will be released in January.
{: .notice--info}

## Submission Guidelines

  * Multiple run submissions are allowed, but participants must explicitly indicate one PRIMARY run for each track. All other run submissions are treated as CONTRASTIVE runs. In the case that none of the runs is marked as PRIMARY, the latest submission (according to the file time-stamp) for the respective track will be used as the PRIMARY run.
  * Submissions have to be submitted as a gzipped TAR archive (see format below) and sent as an email attachment to  <iwslt_offline_task_submission@fbk.eu>.
  * The TAR archive should include in the file name the type of system (cascade/end-to-end) used to generate the submission
  * Each run has to be stored in a plain text file with one sentence per line
  * Scoring will be case-sensitive and including the punctuation. Submissions have to be in UTF-8. Tags such as applause, laughing etc are not considered during the evaluation.

TAR archive file structure:
```
< UserID >/< Set >.< LangDir >.< Task >.< UserID >.primary.txt  
  /< Set >.< LangDir >.< Task >.< UserID >.contrastive1.txt  
  /< Set >.< LangDir >.< Task >.< UserID >.contrastive2.txt  
  /...  
```
where:  
`< UserID >` = user ID of participant used the short name chosen in the registration form (e.g. the name of your institution)  
`< Set >` = IWSLT21.SLT.tst2021  
`< LangDir >` = en-de/zh/ja, using language identifiers (LIDs) as given by ISO 639-1 codes  
`< Task >` =  OfflineTask.  
For example, `FBK/IWSLT21.SLT.tst2021.en-de.OfflineTask.FBK.primary.txt`  

All the submissions should be sent to this address: <iwslt_offline_task_submission@fbk.eu>

The email should include the following information:
  * Institute:
  * Contact Person:
  * Email:
  * Data condition: Constrained/Unconstrained
  * Segmentation: Own/Given
  * Brief abstract about the system:
  * Multilingual: Yes/No 
  * Do you want to make your submissions freely available for research purposes? (yes/no)


## Contacts 

Chairs: Marco Turchi (Matteo Negri, FBK, Italy and Marco Turchi, Zoom, Germany). 

Discussion: <iwslt-evaluation-campaign@googlegroups.com>


## Organizers

Sebastian Stüker (Zoom, Germany)  
Jan Niehues (KIT, Germany)  
Roldano Cattoni (FBK, Italy) 




