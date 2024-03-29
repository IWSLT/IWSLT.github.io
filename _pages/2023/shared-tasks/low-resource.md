---
permalink: /2023/low-resource
title: "Dialectal and Low-resource track"
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

The goal of this shared task is to benchmark and promote speech translation technology for a diverse range of dialects and low-resource languages.
While significant research progress has been demonstrated recently on popular datasets, many of the world's dialects and low-resource languages lack the parallel data at scale needed for standard supervised learning.
We will likely require creative approaches in leveraging disparate resources.

For example, to translate dialectal speech such as Tunisian Arabic, one may leverage existing speech and text resources in Modern Standard Arabic. 
Or, to translate a low-resource language such as Tamasheq, one may need to leverage word-level translation resources and raw audio. 

We will provide training and evaluation data for a range of language-pairs. 
Participants are free to participate in any number of language-pairs in this track. 
We encourage both dedicated systems that are designed to a single language-pair, as well as general recipes aimed at improving speech translation broadly for a wide typology of languages. 



## General Information for All Language-Pairs

The submission format will be standardized across all language-pairs.
Participants can submit systems under two conditions:
- **Constrained condition:** systems are trained only on the dataset provided by the organizers
- **Unconstrained condition:** systems can be trained with any resource, including pre-trained models. Multilingual models are allowed. 

Information about data and baselines are provided in the sections specific to each language pair. 

## Data and Baselines

### aeb-eng: Tunisian Arabic to English 
<!-- Details description of the data and links to download -->

The aeb-eng training data is the same as the one used in the IWSLT 2022 Dialectal Speech Translation track in the previous year: <a href="https://iwslt.org/2022/dialect">https://iwslt.org/2022/dialect</a>. 
Please follow the train/dev/test1 split instructions according to the aforementioned IWSLT 2022 webpage.

In 2022 we had three conditions: basic, dialect adaptation, and unconstrained. 
The basic condition in 2022 corresponds to the "constrained" condition in 2023; the dialect adaptation and unconstrained conditions in 2022 will be referred to as the "unconstrained" condition in 2023.
A new test set (<it>test3</it>) will be provided as part of this 2023 evaluation. 

IWSLT participants may obtain the Tunisian-English speech translation data for no cost from LDC. Please sign this [form](https://www.cs.jhu.edu/~kevinduh/j/iwslt23/IWSLT_2023_LDC_Evaluation_Agreement) and email it to ldc@ldc.upenn.edu. This 3-way parallel data corresponds to 160 hours and 200k lines worth of aligned audio in Tunisian speech, Tunisian transcripts, and English translations.
All datasets have been manually segmented at the utterance level.

The official BLEU score will use lower-case and no punctuation, following the "norm" files in the setup [instructions](https://github.com/kevinduh/iwslt22-dialect). 

For baselines, feel free to build upon the models in ESPnet provided by <a href="https://shinjiwlab.github.io">CMU WAVLab</a>. Here are the recipes for the basic condition: <a href="https://github.com/espnet/espnet/blob/master/egs2/iwslt22_dialect/asr1/RESULTS.md">ASR model</a> and
<a href="https://github.com/espnet/espnet/blob/master/egs2/iwslt22_dialect/st1/RESULTS.md">ST model</a>. You may also find it helpful to refer to the system description papers in 2022 from <a href="https://aclanthology.org/2022.iwslt-1.27/">CMU</a>, <a href="https://aclanthology.org/2022.iwslt-1.29/">JHU</a>, and <a href="https://aclanthology.org/2022.iwslt-1.28/">ON-TRAC</a>, or the <a href="https://aclanthology.org/2022.iwslt-1.10v2.pdf">2022 findings paper</a>.

### ga-eng: Irish to English
Irish (also known as Gaeilge) has around 170,000 L1 speakers and “1.85 million (37%) people across the island (of Ireland) claim to be at least somewhat proficient with the language”. In the Republic of Ireland, it is the national and first official language. It is also one of the official languages of the European Union and a recognized minority language in Northern Ireland with the ISO *ga* code.

IWSLT participants may obtain the Irish-English speech translation data  from <a href="https://github.com/shashwatup9k/iwslt2023_ga-en"> here</a>. Please sign <a href="https://forms.gle/N6KvepNo6gs8BpF56"> this form</a> to get acess and/or password.This corpus consists of 11 hours of audio speech data and translations into English text.

### mr-hi: Marathi to Hindi 
Marathi is an Indo-Aryan language which has the ISO code *mr*, and is dominantly spoken in India’s Maharashtra state. It is one of the 22 scheduled languages of India and the official language of Maharashtra and Goa. As per the 2011 Census of India, it has around 83 million speakers which covers 6.86% of the country's total population. Marathi speakers rank third amongst the languages that are spoken in India.

IWSLT participants may obtain the <a href="https://github.com/panlingua/iwslt2023_mr-hi">Marathi-Hindi speech translation data</a> without any cost. Please sign <a href="http://panlingua.co.in/iwslt-2023/IWSLT2023_mr-hi_Panlingua_Agreement.pdf"> this form</a> and email it to info@panlingua.co.in. This corpus consists of 30 hours of audio speech data from the news domain and translations into Hindi text.

* Participants can get the additional Marathi audio data (with transcription) from here: [Common Voice](https://commonvoice.mozilla.org/en/datasets), [OpenSLR](https://www.openslr.org/64/) and [Indian Language Corpora](https://www.cse.iitb.ac.in/~pjyothi/indiccorpora/)

### mlt-eng: Maltese to English
Please fill out <a href="https://forms.office.com/pages/responsepage.aspx?id=vfGpYaB-aECyMbtKa_y3ADtSBzjpn85Mvz9VNgwI-utUQVBGMlBGVzhUVFNKRUQ3RkdVM0ZJMVVJUy4u">this form</a> to request the Maltese-English data for the LowResSLT task. The data is divided into three parts, and we are releasing around 2.5 hours of audio with Maltese transcription and English translation. We are also releasing about 7.5 hours of audio with only Maltese transcription. We will also point to some parallel text corpora for Maltese-English translation.

After filling out this form, you will get the link to download the data as well as an email from us with the link for the dataset, if we update something for the same.

For submission, please follow the standard instructions provided below. Please also submit the split you used for training and validation, along with your translation output. For evaluation, we will be lowercasing everything with punctuation removed. We will also include an additional evaluation with casing and punctuation if your submission contains them. We also encourage you to submit your ASR files as well if you have a cascade/pipeline approach. Please send your submissions to Rishu.Kumar [at] dfki.de


### pus-fra: Pashto to French 
Pashto is spoken by approximately forty to sixty million people in the world. It is particularly spoken by the Pashtun people in the south, east and southwest of the country, as well as in the north and northwest Pakistan but also in Iran, Tajikistan and India (Uttar Pradesh and Cashmere) and one of the two official languages of Afghanistan.

<!-- Details description of the data and links to download -->
This corpus is a collection of about 100 hours of Broadcast News with transcriptions in Pashto and translations in French text.

<strong>Obtaining data</strong>
IWSLT participants may obtain the Pashto-French speech translation data for no cost from ELDA. Please sign <a href="https://drive.google.com/file/d/1YZxBJNDrMVLQx9yTPdqkanySGc-R8BkN/view?usp=sharing">this form</a> and email it to mapelli@elda.org.

<strong>Notice</strong>
for Pashto to French language-pair, we discourage the use of non-public datasets. If you do want to use a private dataset, please contact the organizers, to make sure that your dataset does not overlap with the test set.

For baselines, here are the recipes for the basic condition: <a href="https://github.com/SouhirG/iwslt2023/blob/main/asr/readme.md">ASR model</a> and
<a href="https://github.com/SouhirG/iwslt2023/blob/main/mt/readme.md">MT model</a>. They are also downloadable with the dataset.

### tmh-fra: Tamasheq to French
Tamasheq is a variety of Tuareg, a Berber macro-language spoken by nomadic tribes across North Africa in Algeria, Mali, Niger and Burkina Faso. It accounts for approximately 500,000 native speakers, being mostly spoken in Mali and Niger. 
This task is about translating spoken Tamasheq into written French. Almost 20 hours of spoken Tamasheq with French translation are **freely** provided by the organizers. 
A major challenge is that no Tamasheq transcription is provided.

 * Speech-to-translation parallel data: [here](https://github.com/gruly/IWSLT2022_Tamasheq_data)
 * Additional audio data (see description in the above Github page): [here](https://demo-lia.univ-avignon.fr/studios-tamani-kalangou/)
 * The corpus is described in <a href="https://arxiv.org/abs/2201.05051">this paper</a>
 * A baseline system is available as a <a href="https://speechbrain.github.io">SpeechBrain</a> recipe<a href="https://github.com/speechbrain/speechbrain/tree/develop/recipes/IWSLT22_lowresource"> here</a>. This system is the one which got the best result during the IWSLT22 edition with a BLEU score of 5.7
 * **THE TEST DATA FOR 2023 IS NOW AVAILABLE [HERE](https://github.com/gruly/IWSLT2022_Tamasheq_data/tree/main/taq_fra_clean/test2023/wav)**
 * **Submission file is a text document, with one translation by line, in the same order as the one given in the segments file** [here](https://github.com/gruly/IWSLT2022_Tamasheq_data/tree/main/taq_fra_clean/test2023/txt)


Two kinds of submission are possible: **Constrained condition** and/or **Unconstrained condition**, following the common rules mentioned above in the *General Information for All Language-Pairs* section.

Contact: Yannick Estève (Avignon University)

### que-spa: Quechua to Spanish 
Quechua is an indigenous language spoken by more than 8 million people in South America. It is mainly spoken in Peru, Ecuador, and Bolivia where the official high-resource language is Spanish. It is a highly inflective language based on its suffixes which agglutinate and found to be similar to other languages like Finnish. The average number of morphemes per word (synthesis) is about two times larger than English. English typically has around 1.5 morphemes per word and Quechua has about 3 morphemes per word. 

There are two main region divisions of Quechua known as Quechua I and Quechua II. This data set consists of two main types of Quechua spoken in Ayacucho, Peru (Quechua Chanka ISO:quy) and Cusco, Peru (Quechua Collao ISO:quz) which are both part of Quechua II and, thus, considered a “southern” languages. We label the data set with **que** - the ISO norm for Quechua II mixtures.

IWSLT participants may obtain the public Quechua-Spanish speech translation dataset along with the additonal parallel (text-only) data for the *constrained* task at no cost here: <a href="https://github.com/Llamacha/IWSLT2023_Quechua_data">IWSLT 2023 QUE-SPA Data set</a>. IWSLT particpants should also feel free to use any public websites for the *unconstrained* task. This includes the data set of 60 hours of fully transcribed Quechua audio which can be obtained by emailing j.ortega@northeastern.edu and rodolfojoel.zevallos@upf.edu.

Test Data now available: <a href="https://github.com/Llamacha/IWSLT2023_Quechua_data/tree/main/que_spa_clean/test">Quechua Test Data </a>
 
Participants will submit their final predictions in the following format where "team_name" is the
name of their team:

- team_name.st.constrained.primary.que-spa.txt
- team_name.st.constrained.contrastive1.que-spa.txt
- team_name.st.constrained.contrastive2.que-spa.txt
- team_name.st.unconstrained.primary.que-spa.txt
- team_name.st.unconstrained.contrastive1.que-spa.txt
- team_name.st.unconstrained.contrastive2.que-spa.txt

If participants do not have a constrained/unconstrained system or primary, constrastive1, constrastive2 they should submit only the files that the have, please do NOT repeat submissions.

Submission files should contain translations in the format of 1 per line following the format of the segments file (in sequence) found here: <a href="https://github.com/Llamacha/IWSLT2023_Quechua_data/blob/main/que_spa_clean/test/txt/segments">Quechua Test Segments File Order</a>

The scripts to score submissions are based on BLEU and CHRF and can be found on the main site: <a href="https://github.com/Llamacha/iwslt23_que_esp">Scripts for scoring using BLEU/CHRF</a>. When BLEU scores are found to be below 5, CHRF will be considered.

Submissions should be sent to all: j.ortega@northeastern.edu, rodolfojoel.zevallos@upf.edu, and williamchen@cmu.edu (please send to all) 

Good Luck!


## Submission/Evaluation
<!-- Description of expected submission format and submission instructions -->
<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

Please submit your files as ```<participant>.st.<condition>.<primary/contrastive1/contrastive2>.<source>-<target>.txt```.
The evaluation set will include a `segments.txt` (one utterance per line, with file-ids and start/end times) and the submission of translation outputs should be ordered in the same way. 

Specifically, file names for translation outputs should follow the following structure:  <br>
```<participant>.st.<condition>.<primary/contrastive1/contrastive2>.<src>-<tgt>.txt``` <br>
e.g.,
```gmu.st.basic.primary.aeb-eng.txt``` for translation outputs. The language pair is indicated by ```<src>-<tgt>```. 

File names for speech recognition outputs (if applicable) should follow the following structure:  <br>
```<participant>.asr.<condition>.<primary/contrastive1/contrastive2>.<src>.txt``` <br>
e.g.,
```gmu.asr.basic.primary.aeb.txt``` for ASR outputs.

Submissions should consist of plaintext files with one sentence per line, following the order of the test set segment file, pre-formatted for scoring (detokenized and cased appropriately). 
The ```<condition>``` tag should be one of the following: 
“constrained“ or “unconstrained”. 
If multiple outputs are submitted for one test set, one system must be explicitly marked as primary.
We ask that the participants include a (very) short system desciption in the submission email.

All submissions of the same language-pair should be compressed in a single .tar.gz file with "IWSLT 2023 Dialectal and Low-Resource Task Submission" in the title, and submitted to corresponding organizer for evaluation:
- <strong> aeb-eng: </strong> x@cs.jhu.edu (where x=kevinduh). <strong>March 31, 2013 update: The test sets are released. Please login to your LDC account and click on "Downloads". Please submit results for LDC2022E02 (previous year's test) and LDC2023E09 (new test), with filenames e.g. ```<participant>.LDC2022E02.st.<condition>.primary.aeb-eng.txt```, ```<participant>.LDC2023E09.st.<condition>.primary.aeb-eng.txt```  </strong>
- <strong> pus-fra: </strong> souhir.gahbiche@airbus.com and antoine.thiol@airbus.com
- <strong> tmh-fra: </strong> manh-ha.nguyen@univ-avignon.fr and yannick.esteve@univ-avignon.fr
- <strong> mlt-eng: </strong> Rishu.Kumar@dfki.de
- <strong> que-spa: </strong> j.ortega@northeastern.edu, rodolfojoel.zevallos@upf.edu, and williamchen@cmu.edu (please send to all)
- <strong> mr-hi: </strong> The test data are now availabile. As earlier mentioned, submission file should consist of plaintext file(s) with one translation by line, in the same order as the one given in the segments file [here](https://github.com/panlingua/iwslt2023_mr-hi/test/stamped.tsv). Submissions must be sent as an email to atulkumar.ojha@insight-centre.org
- <strong> ga-eng: </strong> Submissions must be sent as an email to atulkumar.ojha@insight-centre.org

## Organizers
<!-- List of organizers' names and affiliations -->

<strong> aeb-eng: </strong>
- Kevin Duh, Johns Hopkins University
- Paul McNamee, Johns Hopkins University
- Kenton Murray, Johns Hopkins University

<strong> pus-fra, tmh-fra:</strong>
- Souhir Gahbiche (Airbus, France)
- Khalid Choukri (ELDA, France)
- Yannick Estève, Avignon University

<strong>mlt-eng:</strong>
- Claudia Borg, University of Malta
- Thierry Declerck, DFKI
- Rishu Kumar, CUNI
- Lonneke van der Plas, IDIAP

<strong>que-spa:</strong>
- John E. Ortega, Northeastern University 
- Rodolfo Zevallos, Universitat Pompeu Fabra
- William Chen, Carnegie Mellon University

<strong>mr-hi, ga-eng:</strong>
- Atul Kr. Ojha, University of Galway and Panlingua Language Processing LLP
- John McCrae, University of Galway
- John Judge, Dublin City University

<strong> overview</strong>
- Antonios Anastasopoulos, George Mason University
- Milind Agarwal, George Mason University


## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Although each language-pair is managed by different organizers, please use this common forum for all questions and comments: <iwslt-evaluation-campaign@googlegroups.com> <br>

Please use "Dialectal/Low-Resource" in your email subject to make it easy for the organizers to monitor the forum.
