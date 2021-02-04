---
permalink: /2021/multilingual
title: "Multilingual Speech Translation"
toc: true
toc_sticky: true
---

## Description

While multilingual translation is an established task, until recently, few parallel resources existed for speech translation and most remain only for translation from English speech. 
Multilingual models enable transfer from related tasks, which is particularly important for low-resource languages; however, parallel data between two otherwise high-resource languages can often be rare, making multilingual translation and zero-shot translation important for many resource settings. 

In addition to parallel speech and translations, many sources of data may be useful for speech translation: monolingual speech and transcripts, parallel text, and data from other languages or language pairs. 
While cascades of separately trained automatic speech recognition (ASR) and machine translation (MT) models can leverage all of these data sources, how to most effectively do so with end-to-end models remains an open and exciting research question.

Motivated by the above, the **multilingual speech translation task** will provide data for two conditions: **supervised**, and **zero-shot**.
We will provide speech and transcripts for four languages (Spanish, French, Portuguese, Italian) and translations in a subset of five languages (English, Spanish, French, Portuguese, Italian) as [shown below](#data). 
Zero-shot language pairs will have ASR data released for training but not translations; the target languages may be observed in other language pairs in training. 
Participants may use the provided resources in any way.

Both **constrained** submissions (using the provided data only, e.g., no models pretrained on external data) and **unconstrained** submissions are encouraged and will be evaluated separately. 
At evaluation time, we will provide speech in the four source languages and ask participants to generate translations in both English and Spanish. 
Submitting generated transcripts (ASR) for evaluation is not mandatory but strongly encouraged as a useful point of analysis. 

We look forward to your creative submissions!  


## Data

The [Multilingual TEDx](https://arxiv.org/abs/2102.01757){:target="_blank"} data is hosted on [OpenSLR](http://openslr.org/100/){:target="_blank"}. 
The data is derived from TEDx talks and translations. 
All provided data is segmented and aligned at the sentence-level. 
The released data contains train, validation, and progress test sets.  
Blind evaluation sets for IWSLT2021 will be released Apr 5.
![[multilingual speech translation task data image]](https://iwslt.github.io/assets/images/mst2021-data.png)


### Suggested Additional Data for Unconstrained Submissions

- [CoVoST](https://github.com/facebookresearch/covost){:target="_blank"}
- [Europarl-ST](https://www.mllp.upv.es/europarl-st){:target="_blank"}
- [MuST-C v1](https://ict.fbk.eu/must-c/){:target="_blank"}

These are only suggestions; any publicly available additional data or pretrained models are permitted. 
We remind participants that use of any of resources beyond Multilingual TEDx will make a submission **unconstrained.**


## Baselines

We provide [fairseq baselines](https://github.com/esalesky/fairseq/blob/master/examples/speech_to_text/docs/mtedx_example.md) for all tasks, and [kaldi baselines](https://github.com/m-wiesner/tedx){:target="_blank"} for ASR. 


## Submission

Submissions should be compressed in a single .tar.gz file and emailed [here](mailto:elizabeth.salesky+iwslt2021@gmail.com).  
We would like to see outputs for all test sets. 
If multiple outputs are submitted for one test set, one system must be explicitly marked as **primary**, or the submission with the latest timestamp will be treated as primary.

File names should follow the following structure:  <br>
```<participant>.<constrained/unconstrained>.<primary/contrastive>.<src>-<tgt>``` <br>
e.g.,
```jhu.constrained.primary.es-en.txt```

Submissions should consist of plaintext files with one sentence per line, pre-formatted for scoring (detokenized). 
Participants must specify if their submission is unconstrained (use additional data beyond what is provided) or constrained (use only the TEDx data provided); constrained and unconstrained systems will be scored separately.
For unconstrained systems, additional data or pretrained models should be specified in the submission email. 


## Evaluation

We will evaluate translation output using BLEU as computed by [SacreBLEU](https://github.com/mjpost/sacrebleu) and WER for ASR output.
Validation and progress test sets have been added to SacreBLEU. 


## Organizers

Elizabeth Salesky (JHU, USA)  
Jake Bremerman (UMD, USA)  
Jan Niehues (Maastricht University, Netherlands)  
Matt Post (JHU, USA)  
Matthew Wiesner (JHU, USA)


## Contact

Organizers: [Email](mailto:elizabeth.salesky+iwslt2021@gmail.com)  
Discussion: [IWSLT google group](https://groups.google.com/g/iwslt-evaluation-campaign)  