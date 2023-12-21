---
permalink: /2024/offline
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

The goal of the **Offline Speech Translation Task**, the one with the longest tradition at IWSLT, is to examine automatic methods for translating audio speech in one language into text in the target language. This has to be done either by exploiting cascaded solutions or end-to-end approaches. Although the results of the last few editions have confirmed that the performance of end-to-end models is approaching that of cascade solutions, it is currently not clear which of the two technologies is more effective.  Moreover, all the recent evaluations have been based on test sets extracted from TED talks, which are representative of a relatively simpler application scenario compared to the variety of potential on-field deployments of SLT technology. In this controlled scenario, a single speaker acts out a prepared speech without background noise and interaction with other speakers. 

Finally, last year's edition showed that introducing complexity to the scenario (e.g., including spontaneous speech, terminology, and dialogues) resulted in a clear degradation of the performance of both technologies compared to the use of the classic TED talk test set.

<!-- This imposes an interesting research question of how robust our current SLT system is in a more realistic scenario. Accent, a specific pronunciation by people in a particular area, country, or social group, is a unique characteristic in the speech modality. In spite of speaking in the same language, such specific pronunciation could hinder communication between people in different groups. However, accent is rarely examined in our SLT systems. This year, in addition to the traditional test sets, we would provide an extra test set to challenge the participant’s systems on accented conversations in the English-to-German language direction.-->

<!-- DThe submitted system, whether it is under “constrained” data condition or not, would be evaluated on this extra test set. The participants are also welcome to adapt their systems for this robustness challenge on the accent-related data, e.g., VCTK corpus, LibriTTS corpus, and ACL 60/60 evaluation sets. -->

<!-- Decision to take: what scientific questions? Here we need to highlight the robust scenario -->
<!--In addition to answering the question **if the cascade solution is still the dominant technology**, this year we will address an additional research question in the evaluation:
* **Is the current spoken language translation technology able to deal with more complex scenarios (e.g. spontaneous speech, terminology, and dialogues)?** In addition to the classic TED talk test set from English into German, the task introduces two more test sets that face more challenging scenarios:
 replace this with Amazon data * ACL presentations: a single speaker is presenting on a stage. Although this is similar to the TED talk scenario, the speech translation system needs to deal with non-native speakers, different accents, various recording quality, terminology, and controlled interaction with a second speaker.
 replace this bullet with subtitling test sets * Press conferences and interviews: in this scenario, two persons interact on different topics. The speech translation system needs to deal with non-native speakers, different accents, controlled interaction with a second speaker, and spontaneous speeches.
-->

In addition to answering the question **if the cascade solution is still the dominant technology**, this year we will address an additional research question in the evaluation:
* **Is the current spoken language translation technology able to deal with more complex scenarios (e.g. spontaneous speech, terminology, different accents, background noise, and dialogues)?** In addition to the classic TED talk test set from English into German, the task introduces two more test sets that face more challenging scenarios:
<!-- replace this with Amazon data * ACL presentations: a single speaker is presenting on a stage. Although this is similar to the TED talk scenario, the speech translation system needs to deal with non-native speakers, different accents, various recording quality, terminology, and controlled interaction with a second speaker.-->
 * TV series from ITV studios: in this scenario, multiple persons interact in different scenarios. The speech translation system needs to deal with overlapping speakers, different accents, and background noise.
 * Physical training sessions: in this scenario, persons are speaking while practicing in the gym. The speech translation system needs to deal with background noise and an informal speaking style.
 * Accent challenge data: accent, a specific pronunciation by people in a particular area, country, or social group, is a unique characteristic in the speech modality. In spite of speaking in the same language, such specific pronunciation could hinder communication between people in different groups. However, accent is rarely examined in our SLT systems. The submitted system, whether it is under “constrained” data conditions or not, would be evaluated on this extra test set. The participants are also welcome to adapt their systems for this robustness challenge on the accent-related data, e.g., VCTK corpus, LibriTTS corpus, and ACL 60/60 evaluation sets. 

<!--Move here the part on accent
Add the part on the additional test sets. Deadline 1st of March -> only the audio. Evaluation performed by the persons who submitted the data. About the format, Marco contacts Jan. We force them to translate everything by merging the additional test sets into a single file.
-->

<!-- Decision to take: What language directions -->
<!--Similarly to last year, three language directions are proposed in the offline task. Each language direction will be tested in different evaluation scenarios:
* English -> German: TED talks, ACL presentations and press conference and interviews.
* English -> Japanese: TED talks. 
* English -> Chinese: TED talks. 
-->

Similarly to last year, three language directions are proposed in the offline task. Each language direction will be tested in different evaluation scenarios:
* English -> German: TED talks, TV series, physical training sessions, and accent challenge data.
* English -> Japanese: TED talks. 
* English -> Chinese: TED talks. 


The system's performance will be evaluated with respect to its capability to produce translations similar to the target-language references. Such similarity will be measured in terms of multiple automatic metrics: COMET, BLEURT, BLEU, TER, and characTER. The submitted runs will be ranked based on the COMET calculated on the test set by using automatic resegmentation of the hypothesis based on the reference translation by [mwerSegmenter](https://www-i6.informatik.rwth-aachen.de/web/Software/mwerSegmenter.tar.gz). The detailed evaluation script can be found in the [SLT.KIT](https://github.com/isl-mt/SLT.KIT/blob/master/scripts/evaluate/Eval.sh). Moreover, to meet the requests of last year's participants, a human evaluation will be performed on the best-performing submission of each participant.





## Evaluation Conditions

Both cascade and end-to-end models will be evaluated. We kindly ask each participant to specify at submission time if a cascade or an end-to-end model has been used.

In this task, we use the following definition of end-to-end model:
  * No intermediate discrete representations (e.g., source language transcripts like in cascade or target languages like in rover)
  * All parameters/parts that are used during decoding need to be trained on the end2end task (may also be trained on other tasks -> multitasking ok, LM rescoring is not ok)

All the systems will be evaluated on the combination of the different test tests (depending on the language directions) and each specific test set. It is important to note that all the test sets will be released together, but specific information to identify the different test sets will be associated with the data. Each audio file will have a clear identifier of the type of data: e.g. TEDtalk_1.wav, ACL_1.wav, Press_1.wav. More detailed information will be released with the test sets.


## Test Data
<!-- Decision to take: to uncomment when releasing the data -->
<!-- * English-German
   * [tst2023](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/IWSLT-SLT.tst2023.en-de.tgz)
 * English-Japanese
   * [tst2023](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-ja/IWSLT-SLT.tst2023.en-ja.tgz)
 * English-Chinese
   * [tst2023](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-zh/IWSLT-SLT.tst2023.en-zh.tgz)
-->

## Past Editions Development Data

The development data is not segmented using the reference transcript. The archives contain segmentation into sentence-like segmentation using automatic tools. However the participants might also use a different segmentation. The data is provided as an archive with the following files ($set e.g. IWSLT.TED.dev2010):
  * $set.en-de.en.xml: Reference transcript (will not be provided for evaluation data)
  * $set.en-de.en.xml: Reference translation (will not be provided for evaluation data)
  * CTM_LIST: Ordered file list containing the ASR Output CTM Files (will not be provided for evaluation data) (Generated by ASR systems that use more data)
  * FILE_ORDER: Ordered file list containing the wav files
  * $set.yaml: This file contains the time steps for sentence-like segments. It is generated by the LIUM Speaker Diarization tool.
  * $set.h5: This file contains the 40-dimensional Filterbank features for each sentence-like segment of the test data created by XNMT.
  * The last two files are created by the following command:
python -m xnmt.xnmt_run_experiments /opt/SLT.KIT/scripts/xnmt/config.las-pyramidal-preproc.yaml

**Development data:**

  * [dev2010](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/preprocessed/IWSLT-SLT.dev2010.en-de.tgz)
  * [tst2010](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/preprocessed/IWSLT-SLT.tst2010.en-de.tgz)
  * [tst2013](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/preprocessed/IWSLT-SLT.tst2013.en-de.tgz)
  * [tst2014](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/preprocessed/IWSLT-SLT.tst2014.en-de.tgz)
  * [tst2015](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/preprocessed/IWSLT-SLT.tst2015.en-de.tgz)
  * [tst2018](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/IWSLT-SLT.tst2018.en-de.tgz)
  * [tst2019](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/IWSLT-SLT.tst2019.en-de.tgz)
  * [tst2020](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/IWSLT-SLT.tst2020.en-de.tgz)



## Training Data and Data Conditions

A "**constrained**" setup is proposed as the official training data condition, in which the allowed training data is limited to a medium-sized framework in order to keep the training time and resource requirements manageable. In order to allow participants to leverage large language models and medium-sized resources, we propose a "**constrained with large language models**" condition, where a specific set of language models is allowed. In order to allow the participation of teams equipped with high computational power and effective in-house solutions built on additional resources, an "**unconstrained**" setup without data restrictions is also proposed.

* **Constrained** training: Under this condition, the allowed training resources are the following ones (note that the list does not include any pre-trained language model):


| Data type | src lang | tgt lang | Training corpus (URL) | Version | Comment
| --- | :---: | :---: | --- | --- | --- |
| speech | en | -- | [LibriSpeech ASR corpus](http://www.openslr.org/12/) | v12 | includes translations into *pt*, not to be used
| speech | en | -- | [How2](https://github.com/srvk/how2-dataset) | na | |
| speech | en | -- | [Mozilla Common Voice](https://commonvoice.mozilla.org/en/datasets) | v11.0  | |
| speech | en | -- | [TED LIUM](https://lium.univ-lemans.fr/en/ted-lium3/) | v2/v3 | |
| speech | en | -- | [Vox Populi](https://github.com/facebookresearch/voxpopuli) | na | |
| speech-to-text-parallel | en | de | [MUST-C](https://ict.fbk.eu/must-c/) | v1.2/v2.0/v3.0 | A new version of MuST-C en-de has been released!! please check it out! |
| speech-to-text-parallel | en | ja, zh | [MUST-C](https://ict.fbk.eu/must-c/) | v2.0 | |
| speech-to-text-parallel | en | de, es | [MUST-Cinema](https://ict.fbk.eu/must-cinema/) | v1.0 | with subtitle and line breaks |
| speech-to-text-parallel | en | es | [MUST-C](https://ict.fbk.eu/must-c/) | v1.2 | same as MUST-Cinema below but without subtitle breaks |
| speech-to-text-parallel | en | de | [Speech Translation TED corpus](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/corpus/iwslt-corpus.zip) | na | |
| speech-to-text-parallel | en | de, ja, zh | [CoVoST](https://github.com/facebookresearch/covost) | v2 | |
| speech-to-text-parallel | en | de, es | [Europarl-ST](https://www.mllp.upv.es/europarl-st/) | v1.1 | |
| text-parallel | en | de | [Europarl](https://www.statmt.org/europarl/v10/training/europarl-v10.de-en.tsv.gz) | v10 | |
| text-parallel | en | es | [Europarl](https://object.pouta.csc.fi/OPUS-Europarl/v8/tmx/en-es.tmx.gz) | v8 | |
| text-parallel | en | es, zh, de, ja | [NewsCommentary](https://data.statmt.org/news-commentary/v16/training) | v16 | |
| text-parallel | en | es, zh, de, ja | [OpenSubtitles](https://opus.nlpl.eu/OpenSubtitles-v2018.php) | v2018 | |
| text-parallel | en | de | [OpenSubtitles](IWSLT23_OPUS_OpenSubtitles_parallel_filtered.de-en.tgz) | v2018 apptek | partially re-aligned, filtered, with document meta-information on genre |
| text-parallel | en | es | [OpenSubtitles](IWSLT23_OPUS_OpenSubtitles_parallel_filtered.en-es.tgz) | v2018 apptek | partially re-aligned, filtered, with document meta-information on genre |
| text-parallel | en | ja | [JParaCrawl](https://www.kecl.ntt.co.jp/icl/lirg/jparacrawl/) | | |
| text-parallel | en | de | [TED2020](https://object.pouta.csc.fi/OPUS-TED2020/v1/tmx/de-en.tmx.gz) | v1 | |
| text-parallel | en | es | [TED2020](https://object.pouta.csc.fi/OPUS-TED2020/v1/tmx/en-es.tmx.gz) | v1 | |
| text-parallel | en | es, zh, de, ja | [Tatoeba](https://opus.nlpl.eu/Tatoeba.php) | v2022-03-03 | |
| text-parallel | en | es | [ELRC-CORDIS_News](https://object.pouta.csc.fi/OPUS-ELRC-CORDIS_News/v1/tmx/en-es.tmx.gz) | v1 | |
| text-parallel | en | de | [ELRC-CORDIS_News](https://object.pouta.csc.fi/OPUS-ELRC-CORDIS_News/v1/tmx/de-en.tmx.gz) | v1 | |
| text-monolingual | -- | de | [OpenSubtitles with subtitle breaks](https://drive.google.com/file/d/1LCU_3dff7l88k20BfoPFLydhOil3dtRl/view?usp=sharing_) | v2018-apptek | superset of parallel data, with subtitle breaks and document meta-info on genre, automatically predicted line breaks |
| text-monolingual | -- | es | [OpenSubtitles with subtitle breaks](https://drive.google.com/file/d/1xxZnlvF8ds8KBnMnHnRoPzcMP0mRTkuH/view?usp=sharing) | v2018-apptek | superset of parallel data, with subtitle breaks and document meta-info on genre, automatically predicted line breaks |

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

* **Unconstrained** training: any resource, pre-trained language models included, can be used with the exception of evaluation sets 
 
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

Chairs: Marco Turchi (Zoom, Germany), Matteo Negri (FBK, Italy) 

Discussion: <iwslt-evaluation-campaign@googlegroups.com>


## Organizers

<!-- Decision to take: Add more organizers here -->
Sebastian Stüker (Zoom, Germany)  
Jan Niehues (KIT, Germany)  
Roldano Cattoni (FBK, Italy)\
Tsz Kin Lam (The University of Edinburgh, the United Kingdom)\
Barry Haddow (The University of Edinburgh, the United Kingdom)\
Marcely Zanon Boito (NAVER LABS Europe, France)


## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair:   
Discussion: <iwslt-evaluation-campaign@googlegroups.com>
