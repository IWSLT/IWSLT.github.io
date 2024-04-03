---
permalink: /2024/low-resource
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

The goal of this shared task is to benchmark and promote speech translation technology for a diverse range of dialects and low-resource languages.
While significant research progress has been demonstrated recently on popular datasets, many of the world's dialects and low-resource languages lack the parallel data at scale needed for standard supervised learning.
We will likely require creative approaches in leveraging disparate resources.

For example, to translate dialectal speech such as Tunisian Arabic, one may leverage existing speech and text resources in Modern Standard Arabic. 
Or, to translate a low-resource language such as Tamasheq, one may need to leverage word-level translation resources and raw audio. 

We will provide training and evaluation data for 8 typologically diverse language-pairs. 
Participants are free to participate in any number of language-pairs in this track, but we highly encourage participation in as many as possible. 
We welcome both dedicated systems that are designed to a single language-pair, as well as general recipes aimed at improving speech translation broadly for a wide typology of languages. 

## General Information for All Language-Pairs

The submission format will be standardized across all language-pairs.
Participants can submit systems under two conditions:
- **Constrained condition:** systems are trained only on the datasets provided by the organizers (listed below)
- **Unconstrained condition:** systems can be trained with any resource, including pre-trained models. Multilingual models are allowed. 

Information about data and baselines are provided in the sections specific to each language pair. 

## Data and Baselines

### Dialectal Arabic to English (ara-eng)

This language pair will focus on evaluating performance on two Arabic vernaculars:
<ul>
	<li> Tunisian (ISO-3 code: aeb)</li>
	<li> North Levantine (ISO-3 code: apc) </li>
</ul>

We point the participants to training data across different Arabic varieties:

 - The **aeb-eng** training data are the same as the one used in the IWSLT 2022 and 2023 tracks: <a href="https://iwslt.org/2022/dialect">https://iwslt.org/2022/dialect</a>.  We suggest you follow the train/dev/test1 split instructions according to the linked webpage.
 - The **apc-eng** validation/testing data (with transcriptions) can be found [here](https://github.com/ufal/IWSLT2024_Levantine_Arabic_data). Participants are provided with about 120k lines of multi-parallel North Levantine-MSA-English textual data, that can be downloaded from the [LINDAT/CLARIAH-CZ Repository](https://lindat.mff.cuni.cz/repository/xmlui/handle/11234/1-5033). For the speech data, we recommend two LDC resources: BBN/AUB DARPA Babylon Levantine corpus ([Speech + Transcript]((https://catalog.ldc.upenn.edu/LDC2005S08))) and the Levantine Arabic QT Training Data Set 5 corpus ([Speech](https://catalog.ldc.upenn.edu/LDC2006S29) + [Transcript](https://catalog.ldc.upenn.edu/LDC2006T07)).

**\[Feb 8 Update:\] We have worked with LDC to make sure participants can access the below-mentioned Tunisian-English data! See below.**
IWSLT participants may obtain the Tunisian-English speech translation data for no cost from LDC. Please sign this [form](https://drive.google.com/file/d/1vlR01ai3G-E95Byiv6kiMLdbu_7AD94w/view?usp=sharing) and email it to ldc@ldc.upenn.edu (see instructions in the form itself). This 3-way parallel data corresponds to 160 hours and 200k lines worth of aligned audio in Tunisian speech, Tunisian transcripts, and English translations.
All datasets have been manually segmented at the utterance level.

We also provide links to speech recognition datasets that include Arabic data:
- OpenSLR Resource [SLR46](https://www.openslr.org/46/)
- OpenSLR Resource [SLR48](https://www.openslr.org/48/)
- OpenSLR Resource [SLR108](https://www.openslr.org/108/)
- OpenSLR Resource [SLR132](https://www.openslr.org/132/)

**\[April 2 Update:\] THE TEST DATA FOR 2024 IS NOW AVAILABLE [HERE](https://github.com/ufal/IWSLT2024_Levantine_Arabic_data)**


### Bemba to English (bem-eng)
Bemba is a Bantu language, spoken by over 10 million people in Zambia and other parts of Africa.

Data are based on the corpus described in [this paper](https://aclanthology.org/2023.acl-long.115/), providing 180 hours of Bemba speech, along with transcriptions and translations in English.
They are available for download in this <a href="#">Github link</a>.

Additional Bemba speech data (with transcriptions) are available here:

- BembaSpeech [data](https://github.com/csikasote/BembaSpeech) [paper](https://arxiv.org/pdf/2102.04889.pdf)
- ZambeziVoice [data](https://github.com/unza-speech-lab/zambezi-voice) [paper](https://arxiv.org/pdf/2306.04428.pdf)

**\[April 2 Update:\] THE TEST DATA FOR 2024 IS NOW AVAILABLE [HERE](https://github.com/csikasote/iwslt_2024_bemba_test )**

### Bhojpuri to Hindi (bho-hin)

Bhojpuri belongs to the Indo-Aryan language group. It is dominantly spoken in India’s western part of Bihar, the north-western part of Jharkhand, and the Purvanchal region of Uttar Pradesh. As per the 2011 Census of India, it has around 50.58 million speakers. Bhojpuri is spoken not just in India but also in other countries such as Nepal, Trinidad, Mauritius, Guyana, Suriname, and Fiji. Since Bhojpuri was considered a dialect of Hindi for a long time, it did not attract much attention from linguists and hence remains among the many lesser-known and less-resourced languages of India.

IWSLT participants may obtain the <a href="https://github.com/panlingua/iwslt2023_bho-hi">Bhojpuri-Hindi speech translation data</a> without any cost. Please sign <a href="http://panlingua.co.in/iwslt-2023/IWSLT2024_bho-hi_Panlingua_Agreement.pdf"> this form</a> and email it to info@panlingua.co.in. This corpus consists of 25 hours of audio speech data from the news domain and translations into Hindi text.

We point participants to additional Bhojpuri audio data (with transcriptions), parallel and monolingual corpora from here: 

- [ULCA-asr-dataset-corpus](https://github.com/Open-Speech-EkStep/ULCA-asr-dataset-corpus)
- [Bhojpuri-wav2vec2 based model](https://github.com/Open-Speech-EkStep/vakyansh-models#wav2vec2-based-models)
- [Bhojpuri Language Technological Resources (BHLTR)](https://github.com/shashwatup9k/bho-resources)

**\[April 2 Update:\] THE TEST DATA FOR 2024 WILL BE SENT TO REGISTERED PARTICIPANTS ONLY. IF YOU HAVE NOT REGISTERED, PLEASE SEND AN EMAIL TO info@panlingua.co.in**

### Irish to English (gle-eng)
Irish (also known as Gaeilge) has around 170,000 L1 speakers and "1.85 million (37%) people across the island (of Ireland) claim to be at least somewhat proficient with the language". In the Republic of Ireland, it is the national and first official language. It is also one of the official languages of the European Union and a recognized minority language in Northern Ireland.

IWSLT participants may obtain the Irish-English speech translation data  from <a href="https://github.com/shashwatup9k/iwslt2023_ga-eng"> here</a>. Please sign <a href="https://forms.gle/7UPquNT9PT6SSTgk6"> this form</a> to get access credentials. This corpus consists of 11 hours of audio speech data and translations into English text.

**\[April 2 Update:\] THE TEST DATA FOR 2024 IS NOW AVAILABLE [HERE](https://github.com/shashwatup9k/iwslt2023_ga-eng/tree/main/test-2024)**


### Maltese to English (mlt-eng)

**\[Update Feb 1\]: The data and form are available!**
Maltese is a Semitic language, with a heavy influence from Italian and English. It is spoken mostly in Malta, but also in migrant communities abroad, most notably in Australia and parts of America and Canada. The data release for this shared task consists of over 14 hours (split into dev and train) of audio data, together with their transcription in Maltese and translation into English. 

To obtain the data, please fill out <a href="https://forms.gle/SqLLneEp33i7isEG6">this form</a>. 

We also point participants to additional Maltese data here:

- [text corpus](https://github.com/MLRS/BERTu) used to train BERTu, a Maltese BERT model
- [MASRI Data](https://www.um.edu.mt/projects/masri/) speech recognition data
- [Maltese Language Resource Server](https://mlrs.research.um.edu.mt/)

**\[April 2 Update:\] THE TEST DATA FOR 2024 CAN BE DOWNLOADED [HERE](https://drive.google.com/drive/folders/1ldOnKHZHD9YXfcPZ-DNwV-fS9J4jsSwI?usp=sharing)**

### Marathi to Hindi (mar-hin)

Marathi is an Indo-Aryan language dominantly spoken in India’s Maharashtra state. It is one of the 22 scheduled languages of India and the official language of Maharashtra and Goa. As per the 2011 Census of India, it has around 83 million speakers which covers 6.86% of the country's total population. Marathi speakers rank third amongst the languages that are spoken in India.

IWSLT participants may obtain the <a href="https://github.com/panlingua/iwslt2023_mr-hi">Marathi-Hindi speech translation data</a> without any cost. Please sign <a href="http://panlingua.co.in/iwslt-2023/IWSLT2024_mr-hi_Panlingua_Agreement.pdf"> this form</a> and email it to info@panlingua.co.in. This corpus consists of 30 hours of audio speech data from the news domain and translations into Hindi text.

We point participants to additional Marathi audio data (with transcriptions) from here: 

- [Common Voice](https://commonvoice.mozilla.org/en/datasets)
- [OpenSLR](https://www.openslr.org/64/)
- [Indian Language Corpora](https://www.cse.iitb.ac.in/~pjyothi/indiccorpora/)

**\[April 2 Update:\] THE TEST DATA FOR 2024 IS NOW AVAILABLE [HERE](https://github.com/panlingua/iwslt2023_mr-hi/tree/main/test-2024)**

### Quechua to Spanish (que-spa)

Quechua is an indigenous language spoken by more than 8 million people in South America. It is mainly spoken in Peru, Ecuador, and Bolivia where the official high-resource language is Spanish. It is a highly inflective language based on its suffixes which agglutinate and found to be similar to other languages like Finnish. The average number of morphemes per word (synthesis) is about two times larger than English. English typically has around 1.5 morphemes per word and Quechua has about 3 morphemes per word. 

There are two main region divisions of Quechua known as Quechua I and Quechua II. This data set consists of two main types of Quechua spoken in Ayacucho, Peru (Quechua Chanka ISO:quy) and Cusco, Peru (Quechua Collao ISO:quz) which are both part of Quechua II and, thus, considered “southern” languages. We label the data set with **que** - the ISO code for Quechua II mixtures.

IWSLT participants may obtain the public Quechua-Spanish speech translation dataset along with the additonal parallel (text-only) data for the *constrained* task at no cost here: <a href="https://github.com/Llamacha/IWSLT2024_Quechua_data">IWSLT 2024 QUE-SPA Data set</a>. IWSLT particpants should also feel free to use any publicly available data for the *unconstrained* task. This includes a data set of nearly 50 hours of fully transcribed Quechua audio from previous shared tasks. For assistance with the data sets, please email j.ortega@northeastern.edu and rodolfojoel.zevallos@upf.edu.

**\[April 2 Update:\] THE TEST DATA FOR 2024 IS NOW AVAILABLE [HERE](https://github.com/Llamacha/IWSLT2024_Quechua_data/tree/main/que_spa_constrained)**


### Tamasheq to French (tmh-fra)

Tamasheq is a variety of Tuareg, a Berber macro-language spoken by nomadic tribes across North Africa in Algeria, Mali, Niger and Burkina Faso. It accounts for approximately 500,000 native speakers, being mostly spoken in Mali and Niger. 
This task is about translating spoken Tamasheq into written French. Almost 20 hours of spoken Tamasheq with French translation are **freely** provided by the organizers. 
A major challenge is that no Tamasheq transcription is provided.


 - Speech-to-translation parallel data: [here](https://github.com/gruly/IWSLT2022_Tamasheq_data)
 - Additional audio data (see description in the above Github page): [here](https://demo-lia.univ-avignon.fr/studios-tamani-kalangou/)
 - The corpus is described in <a href="https://arxiv.org/abs/2201.05051">this paper</a>
  * Baseline systems are available as a <a href="https://speechbrain.github.io">SpeechBrain</a> recipe<a href="https://github.com/speechbrain/speechbrain/tree/develop/recipes/IWSLT22_lowresource"> here</a>. The best baseline system gets  a BLEU score of 13.89 on the validation data
 
 **\[April 2 Update:\] THE TEST DATA FOR 2024 IS NOW AVAILABLE [HERE](https://github.com/gruly/IWSLT2022_Tamasheq_data/tree/main/taq_fra_clean/test2024/wav)**
 
 
## Baselines

<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->

We provide various baselines:

* For Arabic, feel free to build upon the baseline models in ESPnet provided by <a href="https://shinjiwlab.github.io">CMU WAVLab</a>. Here are the recipes for the basic condition: <a href="https://github.com/espnet/espnet/blob/master/egs2/iwslt22_dialect/asr1/RESULTS.md">ASR model</a> and
<a href="https://github.com/espnet/espnet/blob/master/egs2/iwslt22_dialect/st1/RESULTS.md">ST model</a>. You may also find it helpful to refer to the system description papers in 2022 from <a href="https://aclanthology.org/2022.iwslt-1.27/">CMU</a>, <a href="https://aclanthology.org/2022.iwslt-1.29/">JHU</a>, and <a href="https://aclanthology.org/2022.iwslt-1.28/">ON-TRAC</a>, or the <a href="https://aclanthology.org/2022.iwslt-1.10v2.pdf">2022 findings paper</a>.

* A baseline system for Tamasheq is available as a <a href="https://speechbrain.github.io">SpeechBrain</a> recipe<a href="https://github.com/speechbrain/speechbrain/tree/develop/recipes/IWSLT22_lowresource"> here</a>. This system is the one which got the best result during the IWSLT22 edition with a BLEU score of 5.7.

* We also direct the participants to [the IWSLT 2023 findings paper](https://aclanthology.org/2023.iwslt-1.1v2.pdf) for best practices based on last year's shared task. Papers describing last year's submitted systems are listed [here](https://aclanthology.org/events/iwslt-2023/). 


## Submission

<!-- Description of expected submission format and submission instructions -->

Participants will submit their final predictions in the following format for all language pairs.

We will primarily focus on speech translation results ("st"), but participants are welcome to share intermediate speech recognition outputs as well ("asr").

We ask participants to identify their _primary_ submission (which will be used for the final ranking). We will also allow up to two contrastive submissions ("contrastive1", "contrastive2").

Please name all files as follows:
- [team_name].[task].[type].[label].[language-pair].txt

where:
- "team_name" is the name of the team
- "task" is one of "st" and "asr"
- "type" is one of "constrained" and "unconstrained"
- "label" is one of "primary", "contrastive1", or "contrastive2"
- "language-pair" uses the three-letter ISO codes defined above (e.g. que-spa for Quechua to Spanish)

If participants do not have a constrained/unconstrained system or primary, constrastive1, constrastive2 they should submit only the files that they have, please do NOT repeat submissions.

Submission files should contain translations (or transcriptions) in the format of one per line following the format of the segments file (in sequence) corresponding to the test data splits.

Submission details will be provided with the release of the test data.

## Evaluation

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->
The official BLEU score will use lower-case and no punctuation, following the "norm" files in the setup [instructions](https://github.com/kevinduh/iwslt22-dialect). 

We will also aim for a human evaluation of the translation outputs.


## Organizers

<!-- List of organizers' names and affiliations -->
Arabic:
<ul>
	<li>Kenton Murray, Johns Hopkins University </li>
	<li>Mateusz Krubiński, Institute of Formal and Applied Linguistics, Charles University (krubinski [email symbol] ufal.mff.cuni.cz)</li>
	<li>Pavel Pecina, Institute of Formal and Applied Linguistics, Charles University (pecina [email symbol] ufal.mff.cuni.cz)</li>
</ul>

Bemba:
<ul>
	<li>Antonios Anastasopoulos, George Mason University (antonis [email symbol] gmu.edu)</li>
	<li>Claytone Sikasote, University of Zambia (claytone.sikasote [email symbol] cs.unza.zm)</li>
</ul>

Bhojpuri, Irish, Marathi:
<ul>
	<li>Atul Kr. Ojha - University of Galway (atulkumar.ojha [email symbol] insight-centre.org)</li>
	<li> John P. McCae - University of Galway </li>
</ul>


Maltese:
<ul>
	<li>Claudia Borg, University of Malta (claudia.borg [email symbol] um.edu.mt)</li>
	<li>Rishu Kumar, Charles University (kumarri [email symbol] student.cuni.cz></li>
</ul>


Quechua:
<ul>
	<li>John Ortega - Northeastern University (j.ortega [email symbol] northeastern.edu)</li>
	<li>Rodolfo Zevallos - Universitat Pompeu Fabra (rodolfojoel.zevallos [email symbol] upf.edu)</li>
	<li>William Chen - Carnegie Mellon Univerisy (wc4 [email symbol] andrew.cmu.edu)</li>
	<li>Ibrahim Ahmed - Northeastern University (i.ahmad [email symbol] northeastern.edu)</li>
</ul>

Tamasheq:
<ul>
 	<li>Yannick Estève - Avignon University (yannick.esteve [email symbol] univ-avignon.fr)</li>
</ul>


## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair: Antonios Anastasopoulos, George Mason University

Discussion: <iwslt-evaluation-campaign@googlegroups.com>

Please use the tag [LowRes] in your email title when emailing the above googlegroup.
