---
permalink: /2022/dialect
title: "Dialectal Speech Translation"
---

## Description

In some communities, two dialects of the same language are used by speakers under different settings. For example, in the Arabic-speaking world, Modern Standard Arabic (MSA) is used as spoken and written language for formal communications (e.g., news broadcasts, official speeches, religion), whereas informal communication is carried out in local dialects such as Egyptian, Moroccan, and Tunisian. This diglossia phenomenon poses unique challenges to speech translation. Often only the “high” dialect for formal communication has sufficient training data for building strong ASR and MT systems; the “low” dialect for informal communication may not even be commonly written.

The goal of this shared task is to advance dialectal speech translation in diglossic communities. Specifically, we focus on Tunisian-to-English speech translation, with additional ASR and MT resources in Modern Standard Arabic. Participants will be provided with the following datasets: 

-  (a) 160 hours of Tunisian conversational speech, with manual transcripts
-  (b) 200k lines of manual translations of the above Tunisian transcripts into English, making a three-way parallel data (i.e. aligned audio, transcript, translation) that supports end-to-end speech translation models
-  (c) 1200 hours of Modern Standard Arabic (MSA) broadcast news with transcripts for ASR, available from [MGB-2](https://arabicspeech.org/mgb2/) (Specifically, MGB-2 contains an estimated 70% MSA, with the rest being a mix of Egyptian, Gulf, Levantine, and North African dialectal Arabic. All of the MGB-2 train data is allowed.)
-  (d) ~42,000k lines of bitext in MSA-English for MT, available for download from [OPUS](https://opus.nlpl.eu) ([Opensubtitles](https://opus.nlpl.eu/OpenSubtitles-v2018.php), [UN](https://conferences.unite.un.org/UNCorpus), [QED](https://opus.nlpl.eu/QED-v2.0a.php), [TED](https://opus.nlpl.eu/TED2020-v1.php), [GlobalVoices](https://opus.nlpl.eu/GlobalVoices-v2017q3.php), [News-Commentary](https://opus.nlpl.eu/News-Commentary-v16.php)). For convenience, these six corpora is packaged in a single 2GB tar file [here](https://www.cs.jhu.edu/~kevinduh/j/iwslt22/iwslt22-dialect-bitext.tgz). 

Datasets (a) and (b) are new resources developed by the LDC, which will be provided to the IWSLT participants at no cost. The development and test sets (~3 hours each) are also three-way parallel and have the same characteristics. These datasets have been manually segmented at the utterance level. Participants will build end-to-end or cascaded systems that take Tunisian speech as input and generate English text as final output. 

Participants can build systems for evaluation in any of these conditions:
- <b>Basic condition</b>: train on datasets (a) and (b) only. This uses only Tunisian-English resources; the smaller dataset and simpler setup makes this ideal for participants starting out in speech translation research. 
- <b>Dialect adaptation condition</b>: train on datasets (a), (b), (c), (d). The challenge is to exploit the large MSA datasets for transfer learning while accounting for lexical, morphological, and syntactic differences between dialects. This condition may be an interesting way to explore how multilingual models work in multi-dialectal conditions. 
- <b>Unconstrained condition</b>: participants may use public or private resources for English and more Arabic dialects besides Tunisian (e.g., CommonVoice, TEDx, NIST OpenMT, MADAR, GALE). Multilingual models beyond Arabic and English are allowed. This condition is cross-listed with the [low-resource shared task](low-resource.md).

The main evaluation metric will be BLEU on the final English translation; we will also compute WER on Tunisian transcripts for participants who submit cascade systems. This new dataset from LDC is conversational in nature (similar in style to Spanish Fisher/CALLHOME), and should be interesting for both ASR and MT researchers.

The ultimate goal of this shared task is to explore how transfer learning between “high” and “low” dialects can enable speech translation in diglossic communities. Diglossia is a common phenomenon in the world. Besides Arabic vs. its dialects, other examples include Mandarin Chinese vs. Cantonese/Shanghainese/Taiwanese/etc., Bahasa Indonesia vs. Javanese/Sundanese/Balinese/etc., Standard German vs. Swiss German, and Katharevousa vs. Demotic Greek. We imagine that techniques from multilingual speech translation and low-resource speech translation shared tasks will be relevant; we also hope that new techniques that specifically exploit the characteristics of diglossia will be explored. 

## Obtaining Data

IWSLT participants may obtain the Tunisian-English speech translation data for no cost from LDC. Please sign this [form](https://www.cs.jhu.edu/~kevinduh/j/iwslt22/IWSLT_2022_LDC_Evaluation_Agreement) and email it to ldc@ldc.upenn.edu. This 3-way parallel data corresponds to datasets (a) and (b) mentioned in the above Description section, and includes 160 hours and 200k lines worth of aligned Audio, Tunisian transcripts, and English translations. 

After you obtain the Tunisian-English speech translation data from LDC, please follow these [instructions](https://github.com/kevinduh/iwslt22-dialect) to generate data splits. For the <b>Basic condition</b>, please see the resulting <i>train</i> files for training, <i>dev</i> files for development, and <i>test1</i> files for internal unofficial evaluation. A new blind <i>test2</i> file will be released for official evaluation. 

For the <b>Dialect adaptation condition</b>, please add any of the MGB-2 and OPUS bitext referenced above. For the <b>Unconstrained condition</b>, feel free to use any resource. 

## Baseline Models

Feel free to build upon the baseline models in ESPnet provided by <a href="https://shinjiwlab.github.io">CMU WAVLab</a>. Here are the recipes for the basic condition: <a href="https://github.com/espnet/espnet/blob/master/egs2/iwslt22_dialect/asr1/RESULTS.md">ASR model</a> and 
<a href="https://github.com/espnet/espnet/blob/master/egs2/iwslt22_dialect/st1/RESULTS.md">ST model</a>. The models are also downloadable from Huggingface. 

If you would like to share your baseline models here for other colleagues to use during the evaluation campaign, please contact Kevin Duh. 

## Submission

Participants will receive email from LDC with instructions for downloading the evaluation set. The evaluation set will include a `segments.txt` (one utterance per line, with file-ids and start/end times) and the submission of translation outputs should be ordered in the same way. Submissions should be compressed in a single .tar.gz file and emailed to x@cs.jhu.edu (where x=kevinduh), with "IWSLT 2022 Dialect Shared Task Submission" in the title; you will receive a confirmation of receipt within a day. If multiple outputs are submitted for one test set, one system must be explicitly marked as primary, or the submission with the latest timestamp will be treated as primary. 

File names for translation outputs should follow the following structure:  <br>
```<participant>.st.<condition>.<primary/contrastive1/contrastive2>.<src>-<tgt>.txt``` <br>
e.g.,
```gmu.st.basic.primary.aeb-eng.txt``` for translation outputs.

File names for speech recognition outputs should follow the following structure:  <br>
```<participant>.asr.<condition>.<primary/contrastive1/contrastive2>.<src>.txt``` <br>
e.g.,
```gmu.asr.basic.primary.aeb.txt``` for ASR outputs.

The ```<condition>``` tag should be one of the following: "basic" for <b>basic condition</b>, "adaptation" for <b>dialect adaptation condition</b>, and "unconstrained" for <b>unconstrained condition</b>. Submissions should consist of plaintext files with one sentence per line, following the order of the test set segment file, pre-formatted for scoring (detokenized). The official BLEU score will use lower-case and no punctuation, following the "norm" files in the setup [instructions](https://github.com/kevinduh/iwslt22-dialect). We ask that the participants include a (very) short system desciption in the submission email.


## Organizers

- Kevin Duh (Johns Hopkins University) 
- Paul McNamee (Johns Hopkins University) 
- Kenton Murray (Johns Hopkins University)

Please contact iwslt-evaluation-campaign@googlegroups.com for questions and clarifications about this task. 

<!-- Markdown notes: comments can be formed as above; bulleted lines start with a - ; if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line -->

