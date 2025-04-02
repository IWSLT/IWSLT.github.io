---
permalink: /2025/low-resource
title: "Low-resource track"
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

The low-resource shared task will, for the first time, involve two tracks:
<ul>
	<li> Track 1: A "traditional" speech-to-text translation track focusing on XX typologically diverse language-pairs.</li>
	<li> Track 2: A data track, inviting participants to provide open-sourced speech translation datasets for under-resourced languages.</li>
</ul>

Participants are free to participate in any number of language-pairs in any of the tracks, but we <emph>highly encourage participation in as many as possible.</emph> 
We welcome both dedicated systems that are designed to a single language-pair, as well as general recipes aimed at improving speech translation broadly for a wide typology of languages. 


## Track 1: Speech-Text Speech Translation

### General Information for All Language-Pairs

The submission format will be standardized across all language-pairs.
Participants can submit systems under two conditions:
- **Constrained condition:** systems are trained only on the datasets provided by the organizers (listed below)
- **Unconstrained condition:** systems can be trained with any resource, including pre-trained models. Multilingual models are allowed. 

Information about data and baselines are provided in the sections specific to each language pair. 

### Data for each Language Pair

Please see below for data pointers for each language pair.

### (North) Levantine Dialectal Arabic to English (pca-eng)

This language pair will focus on evaluating performance on one Arabic vernacular:
<ul>
	<!--<li> Tunisian (ISO-3 code: aeb)</li>-->
	<li> North Levantine (ISO-3 code: apc) </li>
</ul>

We point the participants to training data across different Arabic varieties:

 <!--- The **aeb-eng** training data are the same as the one used in the previous IWSLT tasks: <a href="https://iwslt.org/2022/dialect">https://iwslt.org/2022/dialect</a>.  We suggest you follow the train/dev/test1 split instructions according to the linked webpage.-->
 - The **apc-eng** validation/testing data (with transcriptions) can be found [here](https://github.com/ufal/IWSLT2024_Levantine_Arabic_data). Participants are provided with about 120k lines of multi-parallel North Levantine-MSA-English textual data, that can be downloaded from the [LINDAT/CLARIAH-CZ Repository](https://lindat.mff.cuni.cz/repository/xmlui/handle/11234/1-5033). For the speech data, we recommend two LDC resources: BBN/AUB DARPA Babylon Levantine corpus ([Speech + Transcript]((https://catalog.ldc.upenn.edu/LDC2005S08))) and the Levantine Arabic QT Training Data Set 5 corpus ([Speech](https://catalog.ldc.upenn.edu/LDC2006S29) + [Transcript](https://catalog.ldc.upenn.edu/LDC2006T07)).
 For validation, please use the [validation](http://hdl.handle.net/11234/1-5518) and [test](http://hdl.handle.net/11234/1-5519) splits of [IWSLT 2024](https://iwslt.org/2024/low-resource). We will provide a new test set for the evaluation period.

We also provide links to speech recognition datasets that include Arabic data:
- OpenSLR Resource [SLR46](https://www.openslr.org/46/)
- OpenSLR Resource [SLR48](https://www.openslr.org/48/)
- OpenSLR Resource [SLR108](https://www.openslr.org/108/)
- OpenSLR Resource [SLR132](https://www.openslr.org/132/)

### Tunisian Arabic Dialect to English (aeb-eng) 
<!--In spite of the recent progress in artificial intelligence and particularly in speech processing, the majority of world languages and dialects remain uncovered.
That is the case of the Arabic-speaking world where informal communication is carried out using a mixture of local dialects, Standard Arabic and foreign languages such as English and French. This complex linguistic situation coupled with the absence of dedicated data sets represents a significant barrier to the development of performant speech processing systems for a number of Arabic dialects.
-->
This shared task is intended to advance the state of the art of speech transcription and translation for the Tunisian dialect.

Participants will be provided with the following datasets:
-   (1) 323.73 hours of Tunisian Conversational Telephone Speech (CTS), with manual transcripts;
-   (2) 167.48 hours of the above data manually translated into English for end-to-end speech translation models;
-  (3) 08 hours of Tunisian dialect Conversations in train stations with manual transcripts.

Datasets (1) and (2) are made available to the IWSLT participants at no cost by LDC.
The development and test sets (~3 hours each) are also three-way Tunisian Conversational Telephone Speech from LDC. 
Participants will be evaluated using CTS (similar to LDC datasets) test sets for:
- <b>(1) Speech Transcription</b> that takes Tunisian speech as input and generates Tunisian text as output;
- <b>(2) Speech Translation</b> that takes Tunisian speech as input and generates English text as output.

Participants can build systems for evaluation in any of these conditions:
- <b>Constrained</b>: train using only Tunisian-English resources from LDC;
- <b>Unconstrained condition</b>: participants may use any additional public or private resources.

**Obtaining Data**

IWSLT participants may obtain the Tunisian-English speech translation data for no cost from LDC. Please sign [this](https://github.com/fbougares/iwslt25_aeb-eng/blob/main/IWSLT_2025_LDC_Evaluation_Agreement.pdf) and email it to ldc@ldc.upenn.edu. This 3-way parallel data corresponds to datasets (1) and (2) mentioned in the above Description section.
TARIC data set is available by fill out the form available at <https://demo-lia.univ-avignon.fr/taric-dataset/> of TARIC

After you obtain the data sets please use the files ids available here <https://github.com/fbougares/iwslt25_aeb-eng> to generate your dev and internal test sets. The official test set files will be released later for official evaluation.

**Baseline Models**

Stay tuned, we will be releasing baseline models.

**Submission**

Participants will receive email from LDC with instructions for downloading the evaluation set.
The evaluation set will include a ```segments.txt``` (one utterance per line, with file-ids and start/end times) and the submission of translation outputs should be ordered in the same way.
Submissions should be compressed in a single .tar.gz file and emailed to fethi DOT bougares AT elyadata.com, with "IWSLT 2025 Dialect Shared Task Submission" in the title; you will receive a confirmation of receipt within a day. If multiple outputs are submitted for one test set, one system must be explicitly marked as primary, or the submission with the latest timestamp will be treated as primary.

File names pattern for translation outputs should follow the following structure:  <br>

(1) File names for speech recognition outputs should follow the following structure:  <br>
```<participant>.asr.<condition>.<primary/contrastive1/contrastive2>.<src>.txt``` <br>
e.g.,
```lia.asr.constrained.primary.aeb.txt```

(1) File names for speech translation outputs should follow the following structure:  <br>
```<participant>.st.<condition>.<primary/contrastive1/contrastive2>.<src>-<tgt>.txt``` <br>
e.g.,
```lia.st.unconstrained.primary.aeb-eng.txt```


Submissions should consist of plaintext files with one sentence per line, following the order of the test set segment file, pre-formatted for scoring (detokenized). We will be using BLEU and CHRF scores for official evaluation. Submissions are supposed to be lower-cased and without punctuation.

Participants are requested to include a short system description in the submission email.

**Organizers**

- Fethi Bougares (Head of Research @ Elyadata / Associate member @LIA)
- Yannick Estève (Full Professor @LIA)
- Salima Mdhaffar (Researcher @LIA)
- Haroun Elleuch (Phd student Elyadata/LIA)

For questions and clarifications about this task, please write to 
- fethi DOT bougares @ elyadata.com
- yannick DOT esteve @ univ-avignon.fr




### Bemba to English (bem-eng)
Bemba is a Bantu language, spoken by over 10 million people in Zambia and other parts of Africa.

Data are based on the corpus described in [this paper](https://aclanthology.org/2023.acl-long.115/), providing 180 hours of Bemba speech, along with transcriptions and translations in English.
They are available for download in this <a href="#">Github link</a>.

Additional Bemba speech data (with transcriptions) are available here:

- BembaSpeech [data](https://github.com/csikasote/BembaSpeech) [paper](https://arxiv.org/pdf/2102.04889.pdf)
- ZambeziVoice [data](https://github.com/unza-speech-lab/zambezi-voice) [paper](https://arxiv.org/pdf/2306.04428.pdf)

### Fongbe to French (fon-fra)
Fongbe, a tonal African language, is the most spoken dialect of Benin, by more than 50% of Benin’s population, including 8 million speakers. Fongbe is also spoken in Nigeria and Togo.

This task involves translating spoken Fongbe into written French. The organizers provides nearly 57 hours of spoken Fongbe with corresponding French translations. The data used for this shared task is an extension of the [FFTSC corpus](https://aclanthology.org/2024.lrec-main.638.pdf)
The use of this data is restricted to participation in this shared task.
To get it, please sign [this form](https://drive.google.com/file/d/1xMG8riQEjnK1NHrkDLF86ZgosXlzbPxf/view?usp=sharing) and email it to fortune.kponou@imsp-uac.org

**Evaluation data are now accessible to the registered participants on the [private HF repo](https://huggingface.co/GbeBenin) dedicated to this fon-fra task**

 
### Irish to English (gle-eng)
Irish (also known as Gaeilge) has around 170,000 L1 speakers and "1.85 million (37%) people across the island (of Ireland) claim to be at least somewhat proficient with the language". In the Republic of Ireland, it is the national and first official language. It is also one of the official languages of the European Union and a recognized minority language in Northern Ireland.

IWSLT participants may obtain the Irish-English speech translation data  from <a href="https://github.com/shashwatup9k/iwslt2025_ga-eng"> here</a>.

### Bhojpuri to Hindi (bho-hin)

Bhojpuri belongs to the Indo-Aryan language group. It is dominantly spoken in India’s western part of Bihar, the north-western part of Jharkhand, and the Purvanchal region of Uttar Pradesh. As per the 2011 Census of India, it has around 50.58 million speakers. Bhojpuri is spoken not just in India but also in other countries such as Nepal, Trinidad, Mauritius, Guyana, Suriname, and Fiji. Since Bhojpuri was considered a dialect of Hindi for a long time, it did not attract much attention from linguists and hence remains among the many lesser-known and less-resourced languages of India.

IWSLT participants may obtain the <a href="https://github.com/panlingua/iwslt2025_bho-hi">Bhojpuri-Hindi speech translation data</a> without any cost. This corpus consists of 25 hours of audio speech data from the news domain and translations into Hindi text.

We point participants to additional Bhojpuri audio data (with transcriptions), parallel and monolingual corpora from here: 

- [ULCA-asr-dataset-corpus](https://github.com/Open-Speech-EkStep/ULCA-asr-dataset-corpus)
- [Bhojpuri-wav2vec2 based model](https://github.com/Open-Speech-EkStep/vakyansh-models#wav2vec2-based-models)
- [Bhojpuri Language Technological Resources (BHLTR)](https://github.com/shashwatup9k/bho-resources)

### Estonian to English (est-eng)

<!---Details on  Estonian.

Data pointers.--->

Training and dev data for [IWSLT 2025](https://iwslt.org/2025/) Estonian-English speech translation task are available [here](https://github.com/taltechnlp/iwslt2025_est2eng_data) 

Training data contains 581647 utterances (1258 hours), and the development set 1601 utterances (3.6 hours). Training data originates from the TalTech Estonian Speech Dataset 1.0 which is a manually transcribed dataset of mostly broadcast data created for training ASR models. All the speech data consists of long-form speech and has been manually transcribed and time-aligned with speech at an utterance level. In the dataset provided here, the long-form recordings have been split up into utterances. The transcripts have been automatically translated to English using Google Translate. Development data contains data from government and municipal press conferences, TV news and TV talk shows and has been manually translated to English. Both original Estonian transcriptions as well as English translations are provided for all utterances.


### Maltese to English (mlt-eng)

**\[Update Feb 1\]: The data and form are available!**
Maltese is a Semitic language, with a heavy influence from Italian and English. It is spoken mostly in Malta, but also in migrant communities abroad, most notably in Australia and parts of America and Canada. The data release for this shared task consists of over 14 hours (split into dev and train) of audio data, together with their transcription in Maltese and translation into English. 

To obtain the data, please fill out <a href="https://forms.gle/SqLLneEp33i7isEG6">this form</a>. 

We also point participants to additional Maltese data here:

- [text corpus](https://github.com/MLRS/BERTu) used to train BERTu, a Maltese BERT model
- [MASRI Data](https://www.um.edu.mt/projects/masri/) speech recognition data
- [Maltese Language Resource Server](https://mlrs.research.um.edu.mt/)

### Marathi to Hindi (mar-hin)

Marathi is an Indo-Aryan language dominantly spoken in India’s Maharashtra state. It is one of the 22 scheduled languages of India and the official language of Maharashtra and Goa. As per the 2011 Census of India, it has around 83 million speakers which covers 6.86% of the country's total population. Marathi speakers rank third amongst the languages that are spoken in India.

IWSLT participants may obtain the <a href="https://github.com/panlingua/iwslt2025_mr-hi">Marathi-Hindi speech translation data</a> without any cost. This corpus consists of 30 hours of audio speech data from the news domain and translations into Hindi text.

We point participants to additional Marathi audio data (with transcriptions) from here: 

- [Common Voice](https://commonvoice.mozilla.org/en/datasets)
- [OpenSLR](https://www.openslr.org/64/)
- [Indian Language Corpora](https://www.cse.iitb.ac.in/~pjyothi/indiccorpora/)


### Quechua to Spanish (que-spa)

Quechua is an indigenous language spoken by more than 8 million people in South America. It is mainly spoken in Peru, Ecuador, and Bolivia where the official high-resource language is Spanish. It is a highly inflective language based on its suffixes which agglutinate and found to be similar to other languages like Finnish. The average number of morphemes per word (synthesis) is about two times larger than English. English typically has around 1.5 morphemes per word and Quechua has about 3 morphemes per word. 

There are two main region divisions of Quechua known as Quechua I and Quechua II. This data set consists of two main types of Quechua spoken in Ayacucho, Peru (Quechua Chanka ISO:quy) and Cusco, Peru (Quechua Collao ISO:quz) which are both part of Quechua II and, thus, considered “southern” languages. We label the data set with **que** - the ISO code for Quechua II mixtures.

IWSLT participants may obtain the public Quechua-Spanish speech translation dataset along with the additonal parallel (text-only) data for the *unconstrained* task at no cost here: <a href="https://github.com/Llamacha/IWSLT2025_Quechua_data">IWSLT 2025 QUE-SPA Data set</a>. IWSLT particpants should feel free to use any publicly available data for the *unconstrained* task. This includes a data set of nearly 50 hours of fully transcribed Quechua audio from previous shared tasks along with the introduction of a new data set this year which is about 8 hours of synthetic (post-edited) translations. For assistance with the data sets, please email j.ortega@northeastern.edu and rodolfojoel.zevallos@upf.edu.


### Baselines

<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->
Coming soon!

### Submission

<!-- Description of expected submission format and submission instructions -->
Coming soon!

### Evaluation

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->
The official scoring will be based on automatic metrics (COMET, BLEU, chrF++) over lower-cased outputs after removing punctuation. 
Please follow the “norm” files in the <a href="https://github.com/kevinduh/iwslt22-dialect">setup instructions</a>.

We will also aim for a human evaluation of the translation outputs for the more competitive systems.


## Track 2: Training and Evaluation Data Track

This track aims to empower language communities to contribute to key datasets. These datasets are essential for expanding the reach of spoken language technology to more languages and varieties.

Progress made in translation quality has largely been directed at high-resource languages. Recently, focus has started to shift to under-served languages, and foundational datasets such as FLORES and NTREX have made it easier to develop and evaluate MT models for an increasing amount of languages. The high impact of these components left some in the research community wondering: how do we add more languages to these existing open-source datasets?

The goal of this shared task track is to expand open datasets to more languages. In particular, we are soliciting contributions to Speech Translation Training and Evaluation Datasets, either on text-to-speech or speech-to-speech formats.

To describe and publicise their contributions, tracj participants will be asked to submit a 2-4 page paper to be presented at IWSLT 2025, similar to other Shared Task papers.

### Data Submission Requirements

We highly encourage participants to get creative, however we also want to ensure data quality. Please see notes below:

* Translations should be performed, wherever possible, by qualified, native speakers of the target language. We strongly encourage verification of the data by at least one additional native speaker.
* Dataset card: <a href="https://oldi.org/guidelines#dataset-card">dataset cards</a> should be attached to new data submissions, detailing precise language information and the translation workflow that was employed. In particular, we ask participants to identify the language with both an <a href="https://iso639-3.sil.org/code_tables/639/data">ISO 639-3</a> individual language tag and a <a href="https://glottolog.org/glottolog/glottologinformation">Glottocode</a>. The script should be identified with an <a href="https://unicode.org/iso15924/iso15924-codes.html">ISO 15924</a> script code.
* License: We highly encourage new contributions to be released under CC BY-SA 4.0 or other similarly permissive licenses. By contributing data to this shared task, participants agree to have this data released under these terms. At a minimum, data should be made available for research use.
* Use of automatic translation or LLMs for data generation: while post-editing of automatic output is allowed, we require that any data submitted for the shared task are 100% verified by humans, if not directly created by humans. Raw, unverified machine translated outputs are not allowed. If using MT, you must ensure that the terms of service of the model you use allow re-using its outputs to train other machine translation models (as an example, popular commercial systems such as DeepL, Google Translate and ChatGPT disallow this).

### Paper Submission Requirements

Coming soon!

## Organizers

<!-- List of organizers' names and affiliations -->


## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair(s):  

<ul>
	<li> General Overview:
		<ul>
			<li> Antonios Anastasopoulos, George Mason University</li>
			<li> Kenton Murray, Johns Hopkins University</li>
		</ul>
	</li>
	<li> Bemba:
		<ul>
			<li>Claytone Sikasote, University of Zambia</li>
		</ul>
	</li>
	<li> Arabic:
		<ul>
			<!-- <li>Mateusz Krubiński, Institute of Formal and Applied Linguistics, Charles University (krubinski [email symbol] ufal.mff.cuni.cz)</li> -->
			<li>Pavel Pecina, Institute of Formal and Applied Linguistics, Charles University (pecina [email symbol] ufal.mff.cuni.cz)</li>
			<li>Fethi bougares, University of Le Mans</li>
		</ul>
	</li>
	<li> Fongbe:
		<ul>
			<li>Yannick Estève, Avignon University (yannick.esteve [email symbol] univ-avignon.fr)</li>
			<li>Fethi Bougares, University of Le Mans</li>
			<li>Salima Mdhaffar, Avignon University</li>
		</ul>
	</li>
	<li> Irish, Bhojpuri, Marathi:
		<ul>
			<li>Atul Kr. Ojha, University of Galway (atulkumar.ojha [email symbol] insight-centre.org)</li>
			<li>John P. McCae, University of Galway</li>
			<li> Yasmin Moslem, Bering Lab (only for Irish language pair) </li>
		</ul>
	</li>
	<li> Estonian:
		<ul>
			<li>Tanel Alumäe, Tallinn University of Technology</li>
			<li>Mark Fishel, University of Tartu</li>
		</ul>
	</li>
	<li> Maltese:
		<ul>
			<li>Claudia Borg, University of Malta (claudia.borg [email symbol] um.edu.mt)</li>
		</ul>
	</li>
	<li> Quechua:
		<ul>
			<li>John E. Ortega, Northeastern University (j.ortega [email symbol] northeastern.edu)</li>
			<li>Rodolfo Zevallos, Universitat Pompeu Fabra (rodolfojoel.zevallos [email symbol] upf.edu)</li>
		</ul>
	</li>
</ul>

Discussion: <iwslt-evaluation-campaign@googlegroups.com>
