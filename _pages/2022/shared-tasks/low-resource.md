---
permalink: /2022/low-resource
title: "Low-Resource Speech Translation"
---

## Description

This shared task will focus on the problem of developing speech transcription and translation tools for under-resourced languages.
For the vast majority of the world's languages there exist little speech-translation parallel data at the scale needed to train speech translation models. Instead, in a real-world situation we will have access to limited, disparate resources (e.g. word-level translations, speech recognition, small parallel text data, monolingual text, raw audio, etc).

This shared task invites participants to build the best speech transcription/translation system they can for transcribing and/or translating between the following language pairs:

- Tamasheq (taq) to French (fra)
- Tunisian Arabic (aeb) to English (eng)
- <del>Marathi (mar) to Hindi (hin)</del>
- <del>Bhojpuri (bho) to Hindi (hin)</del>


We will provide a list of available:
- parallel translation text corpora
- speech recognition datasets for source languages
- small speech translation datasets for the two language pairs
- monolingual textual corpora 
Note: (not all of the above will be available for all languages)

We allow the use of any pre-trained machine translation, speech recognition, speech synthesis, or speech translation model. We will allow both constrained and unconstrained submissions (a constrained submission will be one using only the data we provide/list). The only data that will not be allowed will be the ones that will be part of the test set.

We invite participants to explore all possible research directions: from pipeline approaches, to end-to-end models, offline or online methods, using other languages through cross-lingual transfer, which provides several datasets), data augmentation, and anything else you come up with.

We look forward to your creative submissions!  

## Allowed Training Data

You may use any of the resources listed below or any other resource you deem appropriate.

### Tamasheq-French
 * Speech-to-translation parallel data: [here](https://github.com/mzboito/IWSLT2022_Tamasheq_data)
 * Additional audio data (see description in the above Github page): [here](https://demo-lia.univ-avignon.fr/studios-tamani-kalangou/)

### Tunisian Arabic - English
* You can use the same data used for the [dialect task](https://iwslt.org/2022/dialect) (unconstrained condition).


### Pretrained Models
The use of pre-trained models such as [wav2vec 2.0](https://arxiv.org/abs/2006.11477), [mBART](https://arxiv.org/abs/2001.08210), or similar is also allowed and is considered a constrained submission.

## Evaluation

The primary task is translation, and hence the submissions will be evaluated using standard automatic translation metrics (e.g. COMET, BLEU and chrF++ as computed by [SacreBLEU](https://github.com/mjpost/sacrebleu)). 

In addition, if the participants' systems also produce transcriptions for the source utterances (which would be the case for pipeline/cascade or multitask systems), we will invite their submission and also evaluate on ASR quality using standard ASR metrics (WER).

### Evaluation Dates

April 14 to 27. Test data are available!

For Tamasheq-French, the test set is available at: [https://github.com/mzboito/IWSLT2022_Tamasheq_data/tree/main/taq_fra_clean/test](https://github.com/mzboito/IWSLT2022_Tamasheq_data/tree/main/taq_fra_clean/test)

For participants who signed up to receive the Tunisian-English data, you should have received an email from LDC and should be able to download the eval pack LDC2022E02 from your LDC account. If you have any problems receiving this data, please contact kevinduh@cs.jhu.edu

## Submission

Submissions should be compressed in a single .tar.gz file and emailed to marcely.zanon-boito at univ-avignon.fr for Tamasheq and to kevinduh [at] cs.jhu.edu for Tunisian Arabic, with "IWSLT 2022 Low-Resource Shared Task Submission" in the title.

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
- Sabrina Syeda Akter (George Mason University, USA)
- Marcely Zanon Boito (Avignon University, France)
- Antonios Anastasopoulos (George Mason University, USA)
- Kevin Duh (Johns Hopkins University, USA)
- Yannick Estève (Avignon University, France)
- Souhir Gahbiche (Airbus, France)
- Marcello Federico (Amazon, USA)
- Alex Waibel (CMU, USA)

The Tamasheq-French task is organized by the ON-TRAC consortium made up of LIA (Avignon University), LIUM (Le Mans University), LIG (University Grenoble Alpes) and Airbus. ON-TRAC is a project co-financed by the French national research agency.

## Contact

Organizers: We can be reached by email through the IWSLT google group listed below
Discussion: [IWSLT google group](https://groups.google.com/g/iwslt-evaluation-campaign)  

