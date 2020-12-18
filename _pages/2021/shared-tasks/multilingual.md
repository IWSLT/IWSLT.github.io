---
permalink: /2021/multilingual
title: "Multilingual Speech Translation"
---

## Description

While multilingual translation is an established task, until recently few parallel resources existed for speech translation and most remain only for translation from English. 
Multilingual models enable transfer from related tasks, important for low-resource language pairs, and further, extend the possibility of zero-shot translation between languages which may have been observed in other pairs. 

In addition to parallel speech and translations, many sources of data may be useful for speech translation: monolingual speech and transcripts, parallel text, and data from other languages or language pairs. 
While cascades of separately trained automatic speech recognition (ASR) and machine translation (MT) models can leverage all of these data sources, how to most effectively do so with end-to-end models remains an open and exciting research question.

Motivated by the above, the multilingual speech translation task will provide data for two conditions: **supervised**, and **zero-shot**.
We will provide speech and transcripts for four languages (Spanish, French, Portuguese, Italian) and translations in a subset of five languages (English, Spanish, French, Portuguese, Italian) as [shown below](#data).  
Zero-shot language pairs will have ASR data released for training but not translations; the target languages may be observed in other language pairs in training. 
Participants may use the provided resources in any way.

Both **constrained** submissions (using the provided data only, e.g., no models pretrained on external data) and **unconstrained** submissions are encouraged and will be evaluated separately. 
At evaluation time, we will provide speech in the four source languages and ask participants to generate translations in both English and Spanish. 
Submitting generated transcripts (ASR) for evaluation is not mandatory but strongly encouraged as a useful diagnostic. 

We look forward to your creative submissions!  


## Data

The data and baselines will be released Feb. 1, 2020.
{: .notice--warning}

The data is derived from TEDx talks and translations.
All provided data will be segmented and aligned.
Raw speech with segments files as well as npz and h5 files with pre-extracted features will be provided for participants' flexibility. 
![[multilingual speech translation task data image]](https://iwslt.github.io/assets/images/mst2021-data.png)


#### Suggested Additional Data for Unconstrained Submissions

- [CoVoST](https://github.com/facebookresearch/covost)
- [Europarl-ST](https://www.mllp.upv.es/europarl-st)
- [MuST-C v1](https://ict.fbk.eu/must-c/)

These are only suggestions; any publicly available additional data or pretrained models are permitted. 
We remind participants that use of any of resources beyond the provided TEDx will make a submission **unconstrained.**


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

We will evaluate translation output using BLEU as computed by [sacreBLEU](https://github.com/mjpost/sacrebleu) and WER for ASR output. 


## Organizers

Elizabeth Salesky (JHU, USA)  
Jake Bremerman (UMD, USA)  
Jan Niehues (Maastricht University, Netherlands)  
Matt Post (JHU, USA)  
Matthew Wiesner (JHU, USA)


## Contact

Organizers: [Email](mailto:elizabeth.salesky+iwslt2021@gmail.com)  
Discussion: [IWSLT google group](https://groups.google.com/g/iwslt-evaluation-campaign)  