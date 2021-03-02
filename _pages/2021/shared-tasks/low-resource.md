---
permalink: /2021/low-resource
title: "Low-Resource Speech Translation"
---

## Description
<!-- the task, the languages, and the type of data -->

This shared task will focus on the problem of developing speech transcription and translation tools for under-resourced languages, to match the real-world needs of humanitarian organizations.
For the vast majority of the world's languages there exist little speech-translation parallel data at the scale needed to train speech translation models. Instead, in a real-world situation we will have access to limited, disparate resources (e.g. word-level translations, speech recognition, small parallel text data, monolingual text, raw audio, etc).

This shared task, in collaboration with the Translators without Borders, invites participants to build the best speech transcription/translation system they can for transcribing and/or translating between the following language pairs:

- Coastal Swahili (swa) to English (eng)
- Congolese Swahili (swc) to French (fra)

We will provide a list of available:
- parallel translation text corpora for any combination between {swa,swc}x{eng,fra}
- speech recognition datasets for the Swahili varieties (which will be the source side)
- small speech translation datasets for the two language pairs
- word-level terminologies and lexicons
- monolingual textual corpora on all four languages

We allow the use of any pre-trained machine translation, speech recognition, speech synthesis, or speech translation model. We will allow both constrained and unconstrained submissions (a constrained submission will be one using only the data we provide/list). The only data that will not be allowed will be the ones that will be part of the test set.

We invite participants to explore all possible research directions: from pipeline approaches, to end-to-end models, offline or online methods, using other languages through cross-lingual transfer (checkout the [shared task on multilingual speech translation](/2021/multilingual), which provides several datasets), data augmentation, and anything else you come up with.

We look forward to your creative submissions!  

## Allowed Training Data

You may use any of the resources listed below or any other resource you deem appropriate. There is exactly one resource you are not allowed to use: the TICO-19 dataset (which will be part of the evaluation set).

### Speech-Transcription-Translation data

* We are releasing small datasets (5k instances) for Swahili speech to English as well as Congolese Swahili to French. These are available for download through [this link](https://drive.google.com/file/d/1lhifoEY0Kzj6s11W_taKoVW_mAvzzZ04/view?usp=sharing). The .zip file also includes the validation data in both language pairs. The format of the files follows the format of the [multilingual task](/2021/multilingual).
* You may also use any of the allowed data for the [Offline Translation task](/2021/offline) or the [Multilingual Translation task](/2021/multilingual), i.e. the [Multilingual TEDx](http://openslr.org/100/) [CoVost](https://github.com/facebookresearch/covost) dataset, [Europarl-ST](https://www.mllp.upv.es/europarl-st), [MuST-C](https://ict.fbk.eu/must-c/).

## ASR data
Any speech recognition data can be used. We point to some relevant resources:
* [ALFFA dataset](http://193.48.145.249/fulltext/Gelas/Gelas_2012_SLTU.pdf), hosted in [OpenSLR](https://www.openslr.org/25/)
* [Mozilla Common Voice](https://voice.mozilla.org/en/datasets)
* [Gamayun Swahili speech samples](https://gamayun.translatorswb.org/data/) (requires registration but it is free)
* IARPA Babel Swahili Language Pack, available through [LDC](https://catalog.ldc.upenn.edu/LDC2017S05) (fee of $25)

## Translation data
Any parallel data can be used, except for the TICO-19 dataset. We point to some relevant resources:
* English-Swahili (swa) parallel data on [OPUS](https://opus.nlpl.eu/) (select 'en' and 'swa'): [MultiCCAligned](https://opus.nlpl.eu/MultiCCAligned-v1.php), [CCAligned](https://opus.nlpl.eu/CCAligned-v1.php), [JW300](https://opus.nlpl.eu/JW300-v1.php), etc
* French-Congolese Swahili (swc) parallel data on [OPUS](https://opus.nlpl.eu/) (select 'fr' and 'swc'): [JW300](https://opus.nlpl.eu/JW300-v1.php)
* [Gamayun kit](https://gamayun.translatorswb.org/data/) translated by the Translators without Botders (requires registration but is free).

### Pretrained Models
The use of pre-trained models such as [wav2vec 2.0](https://arxiv.org/abs/2006.11477), [mBART](https://arxiv.org/abs/2001.08210), or similar is also allowed.

## Evaluation

The primary task is translation, and hence the submissions will be evaluated using standard automatic translation metrics (e.g. BLEU and chrF++ as computed by [SacreBLEU](https://github.com/mjpost/sacrebleu)). 
In addition, if the participants' systems also produce transcriptions for the source utterances (which would be the case for pipeline/cascade or multitask systems), we will invite their submission and also evaluate on ASR quality using standard ASR metrics (WER).

## Submission

Submissions should be compressed in a single .tar.gz file and emailed [here](mailto:anastasopoulos.ant@gmail.com), with "IWSLT 2021 Low-Resource Shared Task Submission" in the title.

We would like to see outputs for both test sets. If multiple outputs are submitted for one test set, one system must be explicitly marked as primary, or the submission with the latest timestamp will be treated as primary. 

File names for translation outputs should follow the following structure:  <br>
```<participant>.st.<primary/contrastive>.<src>-<tgt>``` <br>
e.g.,
```gmu.st.primary.swa-eng.txt``` for translation outputs.

File names for speech recognition outputs should follow the following structure:  <br>
```<participant>.asr.<primary/contrastive>.<src>``` <br>
e.g.,
```gmu.asr.primary.swc.txt``` for ASR outputs.

Submissions should consist of plaintext files with one sentence per line, following the order of the test set, pre-formatted for scoring (detokenized). We ask that the participants include a (very) short system desciption in the submission email.



## Organizers
<!-- list of names and affiliations -->

- Antonios Anastasopoulos (George Mason University, USA)
- Grace Tang (Translators without Borders)
- Will Lewis (University of Washington, USA)
- Sylwia Tur (Appen, USA)
- Rosie Lazar (Appen, USA)
- Marcello Federico (Amazon, USA)
- Alex Waibel (CMU, USA)

## Contact

Organizers: We can be reached by email through the IWSLT google group listed below
Discussion: [IWSLT google group](https://groups.google.com/g/iwslt-evaluation-campaign)  


<!-- Markdown notes: comments can be formed as above; bulleted lines start with a - ; if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line -->
