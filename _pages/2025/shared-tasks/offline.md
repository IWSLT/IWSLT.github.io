---
permalink: /2025/offline
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


<!-- Description the task, the languages, and the type of data -->

The advent of large language models (LLMs) offers unprecedented opportunities to address traditional natural language processing (NLP) tasks in real-world scenarios and under diverse data conditions. Spoken Language Translation (SLT), which involves automatically translating spoken audio into text in a different language, is no exception thanks to the possibility to fine-tune powerful LLMs for specific tasks, domains, and languages, or to employ them in zero-shot settings when suitable adaptation data is unavailable. 

The goal of the **Offline Speech Translation Task** at IWSLT, the one with the longest-standing tradition at the conference, is to provide a stable evaluation framework for tracking technological advancements in SLT, with a focus on unconstrained speech translation—free from the temporal and structural constraints imposed by tasks such as simultaneous translation or subtitling. To this end, while maintaining the overall task formulation is essential, over the years the emphasis has shifted towards incrementally raising the task's difficulty to better reflect real-world needs, including the translation of new and diverse languages, domains, and speaking styles.

In this spirit, this year's edition aims to: 
* include a new and challenging language, Arabic (the full list of the new language directions will be made available soon); 
* offer a varied scenario in terms of domains (news, physical training sessions, and TV series), speaking styles, and recording conditions (e.g., single speakers, multiple overlapping speakers, background noise, accent data);
* promote the development and use of flexible systems capable of operating in this multi-domain scenario, without resorting to ad-hoc, domain-specialized models. 

Similar to last year, the task will provide the opportunity to submit custom extensions to standard offline test sets. These sets are designed to focus on specific aspects of the SLT output that are typically overlooked by traditional evaluation methods.

The system's performance will be evaluated with respect to its capability to produce translations similar to the target-language references. Such similarity will be measured in terms of multiple automatic metrics: COMET, BLEURT, BLEU, TER, and characTER. The submitted runs will be ranked based on the **COMET** calculated on the test set by using automatic resegmentation of the hypothesis based on the reference translation by [mwerSegmenter](https://www-i6.informatik.rwth-aachen.de/web/Software/mwerSegmenter.tar.gz). The detailed evaluation script can be found in the [SLT.KIT](https://github.com/isl-mt/SLT.KIT/blob/master/scripts/evaluate/Eval.sh). Moreover, to meet the requests of last year's participants, a human evaluation will be performed on the best-performing submission of each participant.

<!-- While evaluating the submitted systems to the official test sets, in this edition the organizers give the possibility to submit additional test suites. The goal of a test suite is to evaluate an SLT system on specific aspects that are generally hidden by the classic evaluation frameworks. More information in the session **Test suite**. This means that each participant will translate the official test sets and the test suites. While the official evaluation will be based only on the official test sets, the test suites will give the possibility to identify specific and challenging aspects that affect the SLT performance.  
-->

## Evaluation Conditions

Both cascade and end-to-end models will be evaluated. We kindly ask each participant to specify at submission time if a cascade or an end-to-end model has been used.

In this task, we use the following definition of end-to-end model:
  * No intermediate discrete representations (e.g., source language transcripts like in cascade or target languages like in rover)
  * All parameters/parts that are used during decoding need to be trained on the end2end task (may also be trained on other tasks -> multitasking ok, LM rescoring is not ok)

All the systems will be evaluated on the combination of the different test tests (depending on the language directions) and each specific test set. It is important to note that all the test sets will be released together, but specific information to identify the different test sets will be associated with the data. Each audio file will have a clear identifier of the type of data: e.g. TEDtalk_1.wav, ACL_1.wav, Press_1.wav. More detailed information will be released with the test sets.

## Test Data

Coming Soon!

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

<!--### Test Suite

Test suites are custom extensions to standard offline test sets constructed so that they can focus on particular aspects of the SLT output. The goal of the test suite is to investigate specific aspects that are generally omitted by the classic evaluation strategies. Test suites also evaluate these aspects in their custom way.
The particular test suite composition and its evaluation are fully on the test suite provider.

If you are interested in submitting a test suite, please send us a link to the data including the audio and a textual file describing the goal of the test suite. The format of the audio files is similar to the format of the test audio in the previous editions: a folder with the WAV files and a textual file containing the order in which the audio files will be processed. To share the test suite link, please use the following email: <iwslt_offline_task_submission@fbk.eu>

All the test suites will then be merged and made available to the participants in the test set section. Once the translations are received, they will be split according to the test suites and forwarded to the owners of the test suites. An evaluation is expected to be performed on time to be included in the findings paper.

Important date:
* The test suite should be submitted by the **1st of March**.

For more information about the test suite: <iwslt-evaluation-campaign@googlegroups.com>
-->
<!--Move here the part on accent
Add the part on the additional test sets. Deadline 1st of March -> only the audio. Evaluation performed by the persons who submitted the data. About the format, Marco contacts Jan. We force them to translate everything by merging the additional test sets into a single file.
-->

## Past Editions Development Data

* [IWST.OfflineTask](https://huggingface.co/datasets/IWSLT/IWSLT.OfflineTask)

The development data is not segmented using the reference transcript. The archives contain segmentation into sentence-like segmentation using automatic tools. However, the participants might also use a different segmentation. The data is provided as an archive with the following files ($set e.g. IWSLT.TED.dev2010):
  * $set.en-de.en.xml: Reference transcript (will not be provided for evaluation data)
  * $set.en-de.en.xml: Reference translation (will not be provided for evaluation data)
  * CTM_LIST: Ordered file list containing the ASR Output CTM Files (will not be provided for evaluation data) (Generated by ASR systems that use more data)
  * FILE_ORDER: Ordered file list containing the wav files
  * $set.yaml: This file contains the time steps for sentence-like segments. It is generated by the LIUM Speaker Diarization tool.
  * $set.h5: This file contains the 40-dimensional Filterbank features for each sentence-like segment of the test data created by XNMT.
  * The last two files are created by the following command:
python -m xnmt.xnmt_run_experiments /opt/SLT.KIT/scripts/xnmt/config.las-pyramidal-preproc.yaml
  

## Training Data and Data Conditions

Coming Soon

<!--
A "**constrained**" setup is proposed as the official training data condition, in which the allowed training data is limited to a medium-sized framework in order to keep the training time and resource requirements manageable. In order to allow participants to leverage large language models and medium-sized resources, we propose a "**constrained with large language models**" condition, where a specific set of language models is allowed. In order to allow the participation of teams equipped with high computational power and effective in-house solutions built on additional resources, an "**unconstrained**" setup without data restrictions is also proposed.

* **Constrained** training: Under this condition, the allowed training resources are the following ones (note that the list does not include any pre-trained language model):


| Data type | src lang | tgt lang | Training corpus (URL) | Version | Comment
| --- | :---: | :---: | --- | --- | --- |
| speech | en | -- | [LibriSpeech ASR corpus](http://www.openslr.org/12/) | v12 | includes translations into *pt*, not to be used
| speech | en | -- | [How2](https://github.com/srvk/how2-dataset) | na | |
| speech | en | -- | [Mozilla Common Voice](https://commonvoice.mozilla.org/en/datasets) | v11.0  | |
| speech | en | -- | [TED LIUM](https://lium.univ-lemans.fr/en/ted-lium3/) | v2/v3 | |
| speech | en | -- | [Vox Populi](https://github.com/facebookresearch/voxpopuli) | na | |
| speech-to-text-parallel | en | de | [MUST-C](https://mt.fbk.eu/must-c/) | v1.2/v2.0/v3.0 |  |
| speech-to-text-parallel | en | ja, zh | [MUST-C](https://mt.fbk.eu/must-c/) | v2.0 | |
| speech-to-text-parallel | en | de | [MUST-Cinema](https://mt.fbk.eu/must-cinema/) | v1.0 | with subtitle and line breaks |
| speech-to-text-parallel | en | de | [Speech Translation TED corpus](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/corpus/iwslt-corpus.zip) | na | |
| speech-to-text-parallel | en | de, ja, zh | [CoVoST](https://github.com/facebookresearch/covost) | v2 | |
| speech-to-text-parallel | en | de | [Europarl-ST](https://www.mllp.upv.es/europarl-st/) | v1.1 | |
| text-parallel | en | de | [Europarl](https://www.statmt.org/europarl/v10/training/europarl-v10.de-en.tsv.gz) | v10 | |
| text-parallel | en | es | [Europarl](https://object.pouta.csc.fi/OPUS-Europarl/v8/tmx/en-es.tmx.gz) | v8 | |
| text-parallel | en | es, zh, de, ja | [NewsCommentary](https://data.statmt.org/news-commentary/v16/training) | v16 | |
| text-parallel | en | es, zh, de, ja | [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles/corpus/version/OpenSubtitles) | v2018 | |
| text-parallel | en | de | [OpenSubtitles](https://apptek930-my.sharepoint.com/:u:/g/personal/ematusov_apptek_com/ESYWN8_BzeJAmBv4GcRapbsBeLpmLOd699qBc9_WG7Gifw?e=Bk6UWh) | v2018 apptek | partially re-aligned, filtered, with document meta-information on genre |
| text-parallel | en | es | [OpenSubtitles](https://apptek930-my.sharepoint.com/:u:/g/personal/ematusov_apptek_com/EafNtfaI0yNKgsoDIDTsEK8BelStVZVsZIrQcwjgTx5diA?e=BT97yx) | v2018 apptek | partially re-aligned, filtered, with document meta-information on genre |
| text-parallel | en | ja | [JParaCrawl](https://www.kecl.ntt.co.jp/icl/lirg/jparacrawl/) | | |
| text-parallel | en | de | [TED2020](https://object.pouta.csc.fi/OPUS-TED2020/v1/tmx/de-en.tmx.gz) | v1 | |
| text-parallel | en | es | [TED2020](https://object.pouta.csc.fi/OPUS-TED2020/v1/tmx/en-es.tmx.gz) | v1 | |
| text-parallel | en | es, zh, de, ja | [Tatoeba](https://opus.nlpl.eu/Tatoeba.php) | v2022-03-03 | |
| text-parallel | en | es | [ELRC-CORDIS_News](https://object.pouta.csc.fi/OPUS-ELRC-CORDIS_News/v1/tmx/en-es.tmx.gz) | v1 | |
| text-parallel | en | de | [ELRC-CORDIS_News](https://object.pouta.csc.fi/OPUS-ELRC-CORDIS_News/v1/tmx/de-en.tmx.gz) | v1 | |
| text-monolingual | -- | de | [OpenSubtitles with subtitle breaks](https://fbk.sharepoint.com/:u:/s/MTUnit/Efm0lF0ITTJeBM0ZmjlAKeEBu9CE33SCvb05S1tAq2AkSA?e=FHbZci) | v2018-apptek | superset of parallel data, with subtitle breaks and document meta-info on genre, automatically predicted line breaks |
| text-monolingual | -- | es | [OpenSubtitles with subtitle breaks](https://fbk.sharepoint.com/:u:/s/MTUnit/EXSih5zOAUZciBlO9HiXrJYBVYjjyRuEM7EK9c9BzpKD7w?e=MllfhK) | v2018-apptek | superset of parallel data, with subtitle breaks and document meta-info on genre, automatically predicted line breaks |

Note: this list is identical to the one available in the subtitle task. Some training data are specific for the subtitling task including subtitle boundaries (`<eob>` and `<eol>`).

* **Constrained with Large Language Models** training: Under this condition, all the constrained resources plus a restricted selection of large language models are allowed. The following pre-trained language models are considered parts of the training data and freely usable to build the SLT systems:

  * [Wav2vec 2.0](https://github.com/pytorch/fairseq/blob/main/examples/wav2vec/README.md)
  * [Hubert](https://github.com/pytorch/fairseq/tree/main/examples/hubert)
  * [WavLM](https://github.com/microsoft/unilm/tree/master/wavlm)
  * [SpeechLM](https://github.com/microsoft/unilm/tree/master/speechlm)
  * [data2vec](https://github.com/facebookresearch/fairseq/tree/main/examples/data2vec)
  * [MBART](https://github.com/pytorch/fairseq/blob/main/examples/mbart/README.md)
  * [MBART50](https://github.com/pytorch/fairseq/tree/main/examples/multilingual#mbart50-models)
  * [M2M100](https://github.com/pytorch/fairseq/tree/main/examples/m2m_100)
  * [Delta LM](https://github.com/microsoft/unilm/tree/master/deltalm)
  * [T5](https://github.com/google-research/text-to-text-transfer-transformer)
  * [BLOOM (Note: only the small 560M parameter version)](https://huggingface.co/bigscience/bloom-560m#model-details)
  * [Mistral 7B Instruction Fine-tuned](https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.1)
  * [Mistral 7B Base Model](https://huggingface.co/mistralai/Mistral-7B-v0.1)
  * [Mistral 7B Base Model](https://huggingface.co/meta-llama/Llama-2-7b-chat-hf)
  * [Llama2 7B base model](https://huggingface.co/meta-llama/Llama-2-7b-hf)
  * [NLLB 3.3B](https://huggingface.co/facebook/nllb-200-distilled-1.3B)
  * [NLLB 1.3B](https://huggingface.co/facebook/nllb-200-3.3B)
  * [NLLB 600M](https://huggingface.co/facebook/nllb-200-distilled-600M)
  * [Seamless Models (SeamlessM4T/Streaming/Expressive)](https://github.com/facebookresearch/seamless_communication)
    

* **Unconstrained** training: any resource, pre-trained language models included, can be used with the exception of evaluation sets 
--> 
## Submission Guidelines

  * Multiple run submissions are allowed, but participants must explicitly indicate one PRIMARY run for each track. All other run submissions are treated as CONTRASTIVE runs. In the case that none of the runs is marked as PRIMARY, the latest submission (according to the file time-stamp) for the respective track will be used as the PRIMARY run.
  * Submissions must be packaged as a gzipped TAR archive (see format below) and sent as an email attachment to <iwslt_offline_task_submission@fbk.eu>.
  * The TAR archive should include in the file name the type of system (cascade/end-to-end) used to generate the submission
  * Each run has to be stored as a plain text file with one sentence per line
  * Scoring will be case-sensitive and will include punctuation. Submissions have to be in UTF-8. Tags such as applause, laughing, etc are not considered during the evaluation.

TAR archive file structure:
```
< UserID >/< Set >.< LangDir >.< Task >.< UserID >.primary.txt  
  /< Set >.< LangDir >.< Task >.< UserID >.contrastive1.txt  
  /< Set >.< LangDir >.< Task >.< UserID >.contrastive2.txt  
  /...  
```
where:  
`< UserID >` = user ID of the participant used the short name chosen in the registration form (e.g. the name of your institution)  
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
<!-- Decision to take: Add more contact here -->

Chairs: Matteo Negri (FBK, Italy), Marco Turchi (Zoom, Germany)

Discussion: <iwslt-evaluation-campaign@googlegroups.com>


## Organizers

<!-- Decision to take: Add more organizers here -->
Sebastian Stüker (Zoom, Germany)  
Jan Niehues (KIT, Germany)  
Tsz Kin Lam (The University of Edinburgh, the United Kingdom)\
Barry Haddow (The University of Edinburgh, the United Kingdom)\

