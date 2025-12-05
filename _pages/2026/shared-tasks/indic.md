---
permalink: /2026/indic
title: "Indic S2S track"
toc: true
toc_sticky: true
---

<!--
Markdown notes: comments can be formed as in this example;
bulleted lines start with a - ;
if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line
-->

## Description

The objective of this shared task is to establish a benchmark dataset and develop speech-to-speech translation models for three language pairs belonging to the Devanagari family of Indian languages. Most of these languages are severely low-resource and remain largely unexplored in the context of speech translation. This poses a unique challenge, as existing pre-trained models often struggle to generalize effectively to such underrepresented languages. An additional difficulty arises from the fact that many of the target languages are linguistically distant from English, further complicating translation tasks.
The dataset we propose will serve as the first benchmark and gold-standard resource for speech-to-speech translation across these languages, covering three major Indian languages. By providing this resource, we aim to catalyze the development of robust systems that not only advance research but can also be deployed in real-world applications to improve accessibility and multilingual communication.



<!-- Description the task, the languages, and the type of data -->


## Data
We are offering training and evaluation data for 3 language pairs. Participants have the flexibility to engage in multiple language pairs and directions within this category. We welcome both specialized systems designed for individual language pairs and general approaches aimed at enhancing cascaded as well as direct (End-to-End) speech-to-speech translation across Indic languages.  
For this shared track, we welcome English to Indic {Hindi, Marathi, Punjabi}, and Indic {Hindi, Marathi, Punjabi} to English speech-to-speech translation models for constrained and unconstrained settings. Thus, there will be a total of 6 cases for this task. 
Languages: We plan to release a dataset for the following language pairs: English (en) to Hindi (hi), Marathi (mr), and Punjabi (pa). The speech data is approximately 40 hours for each of the languages. We also intend to provide parallel texts for all the languages. 

Data will be released in January.

<!-- Details description of the data and links to download -->


## Baselines

<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->
Baseline S2S Results on the provided and FLEURS dataset. The results are taken form a paper whic is yet to publish.

Below are the baseline results for the Speech-to-Speech Translation (S2ST) task for Hindi (Hi), Punjabi (Pa), and Marathi (Mr).
Here Indic-S2UT is a model traine on the provided dataset
All results are normalized BLEU, evaluated on the same test set.
<table> 
<thead> 
<tr> <th>Language Pair</th> <th>Indic-S2UT (Provided Dataset) </th> <th>Indic-S2UT (FLEURS)</th></tr> 
</thead> 
<tbody> <tr> <td><strong>Hi → En</strong></td> <td><strong>26.08</strong></td> <td>24.87</td> </tr> 
<tr> <td><strong>Pa → En</strong></td> <td>19.35</td> <td><strong>29.18</strong></td> </tr> 
<tr> <td><strong>Mr → En</strong></td><td><strong>15.29</strong></td> <td>13.98</td> </tr> 
</tbody> 
</table>

## Submission

<!-- Description of expected submission format and submission instructions -->
The submissions must be mailed to this email: <iwsltindictracksubmissions@gmail.com>

Only one submission is allowed per team. The submissions must be submitted zipped in tar.gz format and then emailed. The email should include the following information:

- Institute:

- Contact Person (mail ID):

- Team Members with Details:

- Brief abstract about the system (Mention details about all the models if a different model is used for different language pair): 

**Language specific** (must mention for each language pair)
- Data condition: Constrained/Unconstrained

- End-to-End (Direct) or Cascaded S2S Model:

- Multilingual: Yes/No

- Do you want to make your submissions freely available for research purposes? (yes/no)

**TAR archive file structure**: 

```
For language specific submission:
< TeamID >_< S2SModel >_<DataCon>_< IndicYear >.tar.gz  
  /< LangPair >_< S2SModel >_< IndicYear >.<Tgt>
  /...

For multilingual submission:
< TeamID >_< S2SModel >_<DataCon>_< IndicYear >.tar.gz  
  /< LangPair >_< S2SModel >_< IndicYear >.hi
  /< LangPair >_< S2SModel >_< IndicYear >.mr
  /< LangPair >_< S2SModel >_< IndicYear >.pa
```
where:

`<TeamID>` is the Team ID used at the time of filling google form for downloading datasets.

`<LangPair>` denotes language pair, example: **'hi-en', 'mr-en', 'pa-en', en-hi', 'en-mr', 'en-pa' **.

`<S2SModel>` denotes whether the S2S model is cascaded or end-to-end (direct), example: '**Casc**' or '**E2E**'.

`<DataCon>` denotes whether the data used for model training is constrained or unconstrained, example: '**Cons**' or '**UnCons**'. 

`<IndicYear>` is the year of submission for Indic track, example: '**Indic2026**'.

`<Tgt>` denotes the file extension of target language, example: '**hi**' for Hindi, '**mr**' for Marathi and '**pa**' for Punjabi.

For Example: `IITI_en-hi_E2E_Indic2026.hi`

## Submission Criterion
<!-- Description of constraints for contestants to follow -->
The submissions for the all the language-pairs can for the below 2 conditions:

1. Constrained Conditions: Only the data provided for the language pair can be used for pre-training the models. No data from any other sources can be used for pre-training of the models. 

2. Unconstrained Conditions: Any pre-trained models and any other data can be used for pre-training the models.


## Evaluation
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->
Submissions must be evaluated on the provided dataset, and it is recommended to additionally evaluate performance on the FLEURS dataset (optional). The translation quality will be measured using sacreBLEU, TER (Translation Edit Rate), and BLASER scores (both with and without references).

- Only one test set will be provided for each language pair, consisting of speech in the source language only. The test set will include the .wav files and a .tsv file containing the list of .wav filenames.

- For every speech utterance in the test set, the predicted speech and its transcribed text must be submitted. You must also specify which ASR model was used to transcribe the predicted speech.

- The reference-free BLASER score must be submitted, as it does not require ground-truth references.

- All evaluation results—such as BLEU, TER, and BLASER scores—on the FLEURS dataset must be included in the manuscript.
  
## Timeline
We follow the same schedule as all the other tasks. [(Important Dates)](https://iwslt.org/2026/#important-dates)

## Organizers

<!-- List of organizers' names and affiliations -->
1. Mahendra Gupta (Lecturer, Computer Science and Engineering, Govt. Polytechnic College Anuppur,M.P., India)- <mahendragupta2211@gmail.com>
2. Dr. Chandresh Kumar Maurya (Assistant Professor, AI Lab, Computer Science and Engineering, Indian Institute of Technology Indore, India)- <chandresh@iiti.ac.in>



## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair(s): Chandresh Kumar Maurya <chandresh@iiti.ac.in>;  
Discussion: <iwslt-evaluation-campaign@googlegroups.com>