---
permalink: /2026/offline
title: "Offline ST track"
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

The advent of large language models (LLMs) offers unprecedented opportunities to address traditional natural language processing (NLP) tasks in real-world scenarios and under diverse data conditions. Spoken Language Translation (SLT), which involves automatically translating spoken audio into text in a different language, is no exception thanks to the possibility to fine-tune powerful LLMs for specific tasks, domains, and languages, or to employ them in zero-shot settings when suitable adaptation data is unavailable. 

The goal of the **Offline Speech Translation Task** at IWSLT, the one with the longest-standing tradition at the conference, is to provide a stable evaluation framework for tracking technological advancements in SLT, with a focus on unconstrained speech translation—free from the temporal and structural constraints imposed by tasks such as simultaneous translation or subtitling. To this end, while maintaining the overall task formulation is essential, over the years the emphasis has shifted towards incrementally raising the task's difficulty to better reflect real-world needs, including the translation of new and diverse languages, domains, and speaking styles.

<!--In this spirit, this year's edition aims to: 
* include a new and challenging language, Arabic; 
* offer a varied scenario in terms of domains (news, physical training sessions, and TV series), speaking styles, and recording conditions (e.g., single speakers, multiple overlapping speakers, background noise, accent data);
* promote the development and use of flexible systems capable of operating in this multi-domain scenario, without resorting to ad-hoc, domain-specialized models. -->

<!--Similar to last year, the task will allow users to submit custom extensions (i.e. test suites) to standard offline test sets. These sets are designed to focus on specific aspects of the SLT output that traditional evaluation methods typically overlook. -->

<!--Similarly to last year, three **language directions** are proposed in the offline task. Each language direction will be tested in different evaluation scenarios:
* English -> German: TV series, scientific presentations, business news, and accent challenge data.
* English -> Arabic: business news. 
* English -> Chinese: scientific presentations. -->

In this spirit, this year's edition aims to: 
* include a new and challenging language, Japanese; 
* offer a varied scenario in terms of domains (news, physical training sessions, and TV series), speaking styles, and recording conditions (e.g., single speakers, multiple overlapping speakers, background noise, accent data);
* promote the development and use of flexible systems capable of operating in this multi-domain scenario, without resorting to ad-hoc, domain-specialized models;
* explore system's ability to operate in a "source language agnostic" scenario (**newly introduced track**, see below) where the input language is unknown. 

<!--Four **language directions** are proposed in the offline task. Each language direction will be tested in different evaluation scenarios:
* English -> German: TV series, scientific presentations, business news, and accent challenge data.
* English -> Chinese: TV series, scientific presentations, and business news.
* English -> Japanese: TV series, scientific presentations, business news.
* English -> Arabic: business news.-->

<!-- * German -> English: Jan ?? TTS??
* Czech -> English: Peter -->


<!-- The test sets are totally or partially shared with other tasks (e.g. the subtitling task).-->

Systems' performance will be evaluated with respect to their capability to produce translations similar to the target-language references. Such similarity will be measured in terms of multiple automatic metrics: COMET, BLEURT, BLEU, TER, and characTER. As in previous editions of the campaign, the submitted runs will be ranked based on the **COMET** calculated on the test set by using automatic resegmentation of the hypothesis based on the reference translation by [mwerSegmenter](https://www-i6.informatik.rwth-aachen.de/web/Software/mwerSegmenter.tar.gz). The detailed evaluation script can be found in the [SLT.KIT](https://github.com/isl-mt/SLT.KIT/blob/master/scripts/evaluate/Eval.sh). 
<!--Moreover, to meet the requests of last year's participants, a human evaluation will be performed on each participant's best-performing submission.-->
Moreover, as a complement to automatic evaluation, human evaluation will be performed on each participant's best-performing submission.


<!-- While evaluating the submitted systems to the official test sets, in this edition the organizers give the possibility to submit additional test suites. The goal of a test suite is to evaluate an SLT system on specific aspects that are generally hidden by the classic evaluation frameworks. More information will be provided in the session **Test suite**. This means that each participant will translate the official test sets and the test suites. While the official evaluation will be based only on the official test sets, the test suites will give the possibility to identify specific and challenging aspects that affect the SLT performance.  
-->

## Tracks
For this round of the Offline Speech Translation Task, we propose two tracks: language-aware and language-agnostic.

**Language-aware**: This track follows the traditional format of previous rounds, where participants are challenged with test sets covering a predefined list of language directions. Submissions may be made for any of the following directions:
* English -> German: TV series, scientific presentations, business news, and accent challenge data.
* English -> Chinese: TV series, scientific presentations, and business news.
* English -> Japanese: TV series, scientific presentations, business news.
* English -> Arabic: business news.

**Language-agnostic**: This is a newly introduced track designed to test a system's ability to translate speech when the source language is unknown. By removing the requirement for pre-defined source language labels, the track aims to catalyze the development of truly universal models capable of frictionless, human-like understanding, adapting to the speaker, regardless of the language they speak. **More information about the test data and the target languages will be released soon.**

## Evaluation Conditions

Both cascade and end-to-end models will be evaluated. We kindly ask each participant to specify at submission time if a cascade or an end-to-end model has been used.

In continuity with past rounds, we use the following definition of end-to-end model:
  * No intermediate discrete representations (e.g., source language transcripts like in cascade or target languages like in rover)
  * All parameters/parts that are used during decoding need to be trained on the end2end task (may also be trained on other tasks -> multitasking ok, LM rescoring is not ok)

All the systems will be evaluated using a combination of the different test tests (depending on the language directions) and each specific test suite, if any. It is important to note that all the test sets will be released together, but specific information to identify the different test sets will be associated with the data. Each audio file will have a clear identifier of the type of data: News_1.wav, ACL_1.wav, Press_1.wav. More detailed information will be released with the test sets.

## Test Data

<!--Coming Soon!-->

<!--All test data can be downloaded from the [SPEECHM Evaluation Server](https://iwslt2025.speechm.cloud.cyfronet.pl/test_sets), see Submission STEP 0 below. -->

<!--
The test data includes the official offline task data plus the test suite data (see below).

You can download it here:
   * [tst2024](https://bwsyncandshare.kit.edu/s/iqFZaCbQwFnQd7G)
-->


<!-- Decision to take: to uncomment when releasing the data -->
<!-- * English-German
   * [tst2023](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/IWSLT-SLT.tst2023.en-de.tgz)
 * English-Japanese
   * [tst2023](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-ja/IWSLT-SLT.tst2023.en-ja.tgz)
 * English-Chinese
   * [tst2023](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-zh/IWSLT-SLT.tst2023.en-zh.tgz)
-->


## Past Editions Development Data

* [IWST.OfflineTask](https://huggingface.co/datasets/IWSLT/IWSLT.OfflineTask)

The development data is not segmented using the reference transcript. The archives contain segmentation into sentence-like segmentation using automatic tools. However, the participants might also use a different segmentation. The data is provided as an archive with the following files:
  * $set.en-de.en.xml: Reference transcript (will not be provided for evaluation data)
  * $set.en-de.en.xml: Reference translation (will not be provided for evaluation data)
  * CTM_LIST: Ordered file list containing the ASR Output CTM Files (will not be provided for evaluation data) (Generated by ASR systems that use more data)
  * FILE_ORDER: Ordered file list containing the wav files
  * $set.yaml: This file contains the time steps for sentence-like segments. It is generated by the LIUM Speaker Diarization tool.
  * $set.h5: This file contains the 40-dimensional Filterbank features for each sentence-like segment of the test data created by XNMT.
  * The last two files are created by the following command:
python -m xnmt.xnmt_run_experiments /opt/SLT.KIT/scripts/xnmt/config.las-pyramidal-preproc.yaml
  

## Training Data and Data Conditions


A "**constrained**" setup is proposed as the official training data condition, in which the allowed training data is limited to a medium-sized framework in order to keep the training time and resource requirements manageable. In order to allow participants to leverage large language models and medium-sized resources, we propose a "**constrained with large language models**" condition, where participants can use the training data allowed in the constrained condition plus any additional LLMS as long as it is released under a permissive license. In order to allow the participation of teams equipped with high computational power and effective in-house solutions built on additional resources, an "**unconstrained**" setup without data restrictions is also proposed.

* **Constrained** training: Under this condition, the allowed training resources are the following ones (note that the list does not include any pre-trained language model):


| Data type | src lang | tgt lang | Training corpus (URL) | Version | Comment
| --- | :---: | :---: | --- | --- | --- |
| speech | en | -- | [LibriSpeech ASR corpus](http://www.openslr.org/12/) | v12 | includes translations into *pt*, not to be used
| speech | en | -- | [How2](https://github.com/srvk/how2-dataset) | na | |
| speech | en | -- | [Mozilla Common Voice](https://commonvoice.mozilla.org/en/datasets) | v11.0  | |
| speech | en | -- | [Vox Populi](https://github.com/facebookresearch/voxpopuli) | na | only translation, no transcription |
| speech-to-text-parallel | en | de, ar, zh | [CoVoST](https://github.com/facebookresearch/covost) | v2 | |
| speech-to-text-parallel | en | de | [Europarl-ST](https://www.mllp.upv.es/europarl-st/) | v1.1 | |
| text-parallel | en | ar | [UNPC](https://object.pouta.csc.fi/OPUS-UNPC/v1.0/tmx/ar-en.tmx.gz) | v1.0 | |
| text-parallel | en | de | [Europarl](https://www.statmt.org/europarl/v10/training/europarl-v10.de-en.tsv.gz) | v10 | |
| text-parallel | en | ar | [Tanzil](https://object.pouta.csc.fi/OPUS-Tanzil/v1/tmx/ar-en.tmx.gz) | v1 | |
| text-parallel | en | zh, de, ar | [NewsCommentary](https://data.statmt.org/news-commentary/v18/training) | v18 | |
| text-parallel | en | ar | [GlobalVoices](https://object.pouta.csc.fi/OPUS-GlobalVoices/v2018q4/tmx/ar-en.tmx.gz) | v2018q4 | | 
| text-parallel | en | ar, zh, de | [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles/corpus/version/OpenSubtitles) | v2018 | |
| text-parallel | en | de | [OpenSubtitles](https://apptek930-my.sharepoint.com/:u:/g/personal/ematusov_apptek_com/ESYWN8_BzeJAmBv4GcRapbsBeLpmLOd699qBc9_WG7Gifw?e=Bk6UWh) | v2018 apptek | partially re-aligned, filtered, with document meta-information on genre |
| text-parallel | en | ar, zh, de | [Tatoeba]([https://opus.nlpl.eu/Tatoeba.php](https://opus.nlpl.eu/Tatoeba/corpus/version/Tatoeba)) | v2023-04-12 | |
| text-parallel | en | ar | [ELRC_2922](https://object.pouta.csc.fi/OPUS-ELRC_2922/v1/tmx/ar-en.tmx.gz) | v1 | |
| text-parallel | en | de | [ELRC-CORDIS_News](https://object.pouta.csc.fi/OPUS-ELRC-CORDIS_News/v1/tmx/de-en.tmx.gz) | v1 | |
| text-monolingual | -- | de | [OpenSubtitles with subtitle breaks](https://fbk.sharepoint.com/:u:/s/MTUnit/Efm0lF0ITTJeBM0ZmjlAKeEBu9CE33SCvb05S1tAq2AkSA?e=FHbZci) | v2018-apptek | superset of parallel data, with subtitle breaks and document meta-info on genre, automatically predicted line breaks |

Note: this list is identical to the one available in the subtitle task. Some training data are specific for the subtitling task including subtitle boundaries (`<eob>` and `<eol>`).

* **Constrained with Large Language Models** training: Under this condition, all the constrained resources plus freely accessible large language models released under a permissive license are allowed.


* **Unconstrained** training: any resource, pre-trained language models included, can be used with the exception of evaluation sets 
 
<a id="sg"></a>
## Submission Guidelines

This year, the evaluation will be performed using the MeeTween SPEECHM centralized evaluation server:
[SPEECHM Evaluation Server](https://iwslt2025.speechm.cloud.cyfronet.pl/).

### General Guidelines

* Multiple run submissions are allowed, but participants must explicitly indicate one PRIMARY run for each track. All other run submissions are treated as CONTRASTIVE runs. In the case that none of the runs is marked as PRIMARY, the latest submission (according to the file time-stamp) for the respective track will be used as the PRIMARY run.

* Scoring will be case-sensitive and will include punctuation. Submissions have to be in plain UTF-8 text format, with one sentence per line. Tags such as applause, laughing, etc are not considered during the evaluation.


* Once logged in to the  [SPEECHM Evaluation Server](https://iwslt2025.speechm.cloud.cyfronet.pl/), the submission process requires participants to create one or more Models for each language pair they intend to participate in <!--for the Offline task--> (English-German, English-Arabic, English-Chinese, English-Japanese, X-English, X-German).

* For each chosen language pair, multiple Models can be created based on the training condition (CONSTRAINED / UNCONSTRAINED) and the submission type (PRIMARY / CONTRASTIVE).

* The created Model(s) must be used to submit runs for each of the test sets released for the chosen language pair.

  <!-- (i.e., 1 test set for English-Arabic and English-Chinese, and 4 test sets for English-German). -->

* If any issues are identified, the submitted runs can be deleted or replaced with newer runs.

### Submission Steps

Once logged in to [SPEECHM](https://iwslt2025.speechm.cloud.cyfronet.pl/), proceed through the following two steps. 

<a id="downloadTest"></a>
#### STEP 0: Download and process the test data
    0.1 Click on “Test sets” (at the top of the page).
    0.2 Click on the “offline” button associated with any of the visible test sets in the list.
    0.3 Download ALL the test sets for the language pair(s) chosen for participation.   
    0.4 Process the test data to obtain your candidate submission file (to be stored in plain UTF-8 text format, one sentence per line).
    
<!-- (4 test sets for en-de, 1 test set for en-ar, 1 test set for en-zh).-->

#### STEP 1: Create a New Model

<!-- To create a new model, follow these steps: --> 

    1.1 Click on “My submissions” (at the top of the page).
    1.2 Click on “New model” (button at the top right).
    1.3 Create a new model:
       Insert the Model Name using the standardized format:
       
         ${TEAM}_IWSLT25_Offline_${LANGUAGE_PAIR}_${CONDITION}_${SUBMISSION_TYPE}
         
          Where:
           - ${TEAM} → Short name of your team (e.g., KIT)
           - ${LANGUAGE_PAIR} → Choose from [en-de, en-ar, en-zh, en-jp, X-en, X-de]
           - ${CONDITION} → Choose from [constrained, unconstrained]
           - ${SUBMISSION_TYPE} → Choose from [primary, contrastive]

           Example Model Names:
             KIT_IWSLT25_Offline_en-de_constrained_primary  
             KIT_IWSLT25_Offline_en-de_constrained_contrastive 
     1.4 Insert Description
       Provide a brief but accurate description of your model, including:
          - General approach (e.g., cascade / end-to-end)
          - Training data used
          - Model architecture
          - Any relevant features characterizing your approach
     1.5 Consent Option (optional)
       Consider enabling “Consents” to freely release your submitted system output data.
     1.6 Select Task Compatibility
       Choose the Offline Task Id in the compatibility map.
     1.7 Click “Create Model” (a “Model created” message will appear on the top right).

#### STEP 2: Submit Your Processed Test Set

    2.1 Go to “My Submissions”.
    2.2 Click on the specific model created in STEP 1 
       (e.g., KIT_IWSLT25_Offline_en-de_constrained_primary).
    2.3 Click the “OFFLINE Hypotheses” button.
    2.4 Once you have generated the outputs with your model for each test set, click “Upload hypothesis” for the intended submission:
       ${TESTSET} / ${LANGUAGE_PAIR} (e.g., IWSLT25INSTRUCT / en-de)
    2.5 Upload your submission file (plain UTF-8 text format, one sentence per line).


### Manage Your Submission

#### Download or Delete a Submission
    1 Click on “My Submissions”.
    2 Click on the model associated with the submitted run 
       (e.g., KIT_IWSLT25_Offline_en-de_constrained_primary).
    3 Click on the “OFFLINE Hypotheses” button.
    4 Use the three-dot menu on the right to:
        - Download the submitted run (hypothesis).
        - Delete the submitted run and confirm.
        
#### Replace a Submission
    1 Delete your existing run.
    2 Submit a new run file (repeat STEP 2 of “Submission steps”).




## Contacts 
<!-- Decision to take: Add more contact here -->

Chairs: Matteo Negri (FBK, Italy), Marco Turchi (Zoom, Germany)

Discussion: <iwslt-evaluation-campaign@googlegroups.com>


## Organizers

<!-- Decision to take: Add more organizers here -->
Sebastian Stüker (Zoom, Germany)  
Jan Niehues (KIT, Germany)\
