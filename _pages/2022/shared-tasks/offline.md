---
permalink: /2022/offline
title: "Offline Speech Translation"
toc: true
toc_sticky: true
---

## Description


<!-- the task, the languages, and the type of data -->

Recent advances in deep learning are giving the possibility to address traditional NLP tasks in a new and completely different manner. One of these tasks is spoken language translation (SLT). For years, SLT has been addressed by cascading an automatic speech recognition (ASR) and a machine translation (MT) system. Recent trends rely on using a single neural network to directly translate the input audio signal in one language into a text in a different language without intermediate symbolic representations, e.g., transcriptions.  

The goal of the **Offline Speech Translation Task** is to examine automatic methods for translating audio speech in one language into text in the target language. This has to be done either by exploiting cascaded solutions or end-to-end approaches. Last year's results of IWSLT 2021 have confirmed that the performance of end-to-end models is approaching the results of cascade solutions. Hence, the questions we want to answer this year are: **is the cascaded solution still the dominant technology in spoken language translation?** 

In addition to this research question, this year will will address additional research question in the evaluation:

  * **Are the results obtained using the English-German data also valid for other language directions?** Differently from last year, the task addresses the translation of TED talks from English into German (similar to previosu editions) and from English to Chinese and English to Japanese. **One test set will be released for each language direction, respectively with and without audio segmentation.**
  * **Can we improve the translation quality by using pre-trained models?** In addition to the allowed list of training data for the constrained condition, we also provided a list of pre-trained models that participants are allowed to use in their system. We hope to answer the question how helpful these resources are to improve the performance of state-of-the-art speech translation systems.
  
  
  
The system's performance will be evaluated with respect to their capability to produce translations similar to the target-language references. Such similarity will be measured in terms of multiple automatic metrics: BLEU, TER, BEER and characTER. The submitted runs will be ranked based on the BLEU calculated on the test set by using automatic resegmentation of the hypothesis based on the reference translation by [mwerSegmenter](https://www-i6.informatik.rwth-aachen.de/web/Software/mwerSegmenter.tar.gz). The detailed evaluation script can be found in the [SLT.KIT](https://github.com/isl-mt/SLT.KIT/blob/master/scripts/evaluate/Eval.sh). Moreover, to meet the requests of last year's participants, a human evaluation will be performed on the best performing submission of each participant.
The guidelines for generating the human translation for TED talks were modified recently, in order to produce shorter translations that better fit for subtitling. Since this task focuses on speech translation without additional constraints, we will produce an additional reference that is generated without additional constraints for the human translators as we did last year.

## Evaluation Conditions

Both cascade and end-to-end models will be evaluated. We kindly ask each participant to specify at submission time if a cascade or an end-to-end model has been used.

In this task, we use the following definition of end-to-end model:
  * No intermediated discrete representations (source language like in cascade or target languages like in rover)
  * All parameters/parts that are used during decoding need to be trained on the end2end task (may also be trained on other tasks -> multitasking ok, LM rescoring is not ok)

### Multilingual Models

We are also interested in when and how multilingual models may be beneficial.
With three target languages this year, participants may choose to create one model to translate to all three targets.
Many allowed [pretrained models](#pretrained-models) are also multilingual.
We ask that anyone who uses one multilingual model to submit to the three target languages specify this at submission time; we will analyze submissions to see if there are any consistent differences between individual and multilingual models.


## Test Data

This year one versions of the same TED talks is released. It contains the audio files and the information to convert them into sentence-like segmentation using automatic tools. Systems using the given or another segmentation will be evaluated in a single ranking without distinction between given or own segmentation.

### English - German Test sets

To measure the progress in the ST field, each participant is required to translate also the 2021 test set that is still blind. Similar to last year test set, the 2022 test set will be made available with and without automatic segmentation.

2021:
  -   [Segmented/Unsegmented](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-de/IWSLT-SLT.tst2021.en-de.tgz)

2022:
  -   To be released


### English - Chinese Test sets

2022:
  -   To be released

### English - Japanese Test sets

2022:
  -   To be released

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

**IMPORTANT**: English - Chinese/Japanese training data are now available soon! Enjoy the data!
{: .notice--info}


### English - German Training data

The same training data of the last year's edition are allowed. 
  
The dataset is available [here](https://ict.fbk.eu/must-c/). Press the bottom "click here to download the corpus", and select version V2. 

Please read the note [here](https://iwslt.org/2021/offline#allowed-training-data) to better understand the differences between the MuST-C V1 and V2.


### English - Chinese Training data 
  
The dataset is available [here](https://ict.fbk.eu/must-c/). Press the bottom "click here to download the corpus", and select version V2. 


### English - Japanese Training data 
  
The dataset is available [here](https://ict.fbk.eu/must-c/). Press the bottom "click here to download the corpus", and select version V2. 


### Additional Training data 

These datasets can be used to train your model:
  * [MuST-C corpus v1](https://ict.fbk.eu/must-c/) The MuST-C V1 is still available to favor the reuse of past trained models.
  * [CoVoST](https://github.com/facebookresearch/covost)
  * [TED corpus](https://wit3.fbk.eu/2017-01-c)
  * [Speech-Translation TED corpus](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/corpus/iwslt-corpus.zip) (for this corpus, we provided 40-dimension Filterbank features from the audio, extracted by XNMT)
  * [How2 Corpus](https://github.com/srvk/how2-dataset) (only English - Portuguese) 
  * [LibriVoxDeEn](https://heidata.uni-heidelberg.de/dataset.xhtml?persistentId=doi:10.11588/data/TMEDTX) (only German - English)
  * [Europarl-ST](https://www.mllp.upv.es/europarl-st/)
  * TED LIUM corpus [v2](https://lium.univ-lemans.fr/en/ted-lium2/), [v3](https://lium.univ-lemans.fr/en/ted-lium3/) 
      * The official test set is not part of this corpus, but if you want to use the development data you need to make sure that it is not part of the data
  * Data provided by WMT [2019](http://www.statmt.org/wmt19/), [2020](http://www.statmt.org/wmt20/) and [2021](http://www.statmt.org/wmt21/) 
  * [OpenSubtitles2018](http://opus.nlpl.eu/OpenSubtitles2018.php)
  * [Augmented LibriSpeech](https://github.com/alicank/Translation-Augmented-LibriSpeech-Corpus) (only English - French)
  * [Mozilla Common Voice](https://voice.mozilla.org/en/datasets) for English use version en_2179h_2020-12-11
  * [LibriSpeech ASR corpus](http://www.openslr.org/12/)
  * [VoxPopuli](https://github.com/facebookresearch/voxpopuli)

### Pretrained models

Moreover, the follow pre-trained language models are considered parts of the training data and freely usable to build the SLT systems:

  * [Wav2vec 2.0](https://github.com/pytorch/fairseq/blob/main/examples/wav2vec/README.md)
  * [Hubert](https://github.com/pytorch/fairseq/tree/main/examples/hubert)
  * [MBART](https://github.com/pytorch/fairseq/blob/main/examples/mbart/README.md)
  * [MBART50](https://github.com/pytorch/fairseq/tree/main/examples/multilingual#mbart50-models)
  * [M2M100](https://github.com/pytorch/fairseq/tree/main/examples/m2m_100)
  * [Delta LM](https://github.com/microsoft/unilm/tree/master/deltalm)
  * [T5](https://github.com/google-research/text-to-text-transfer-transformer)


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

Chair: Marco Turchi (FBK, Italy). 

Discussion: <iwslt-evaluation-campaign@googlegroups.com>


## Organizers

Sebastian Stüker (KIT, Germany)  
Jan Niehues (Maastricht University, Netherlands)  
Matteo Negri (FBK, Italy)  
Roldano Cattoni (FBK, Italy) 







<!-- list of names and affiliations -->


<!-- Markdown notes: comments can be formed as above; bulleted lines start with a - ; if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line -->
