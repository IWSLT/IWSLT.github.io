---
permalink: /2026/low-resource
title: "Low-resource ST track"
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
While significant research progress has been demonstrated recently on popular datasets, many of the world's languages lack the parallel data at scale needed for standard supervised learning.
The community will likely require creative approaches in leveraging disparate resources in order to make progress.

The low-resource shared task will, as last year, involve two tracks:
<ul>
	<li> Track 1: A "traditional" speech-to-text translation track focusing on 10 typologically diverse language-pairs.</li>
	<li> Track 2: A data track, inviting participants to provide open-sourced speech translation datasets for under-resourced languages.</li>
</ul>

This year's focus will be on </emph>explicitly multilingual systems that can handle speech from as many diverse languages as possible.</emph> We welcome general recipes aimed at improving speech translation broadly for a wide typology of languages. 
Thus, while participants are free to participate in any number of language pairs that are our focus, we <emph>highly encourage participation in as many as possible.</emph> 
Of course, we still welcome dedicated systems that are designed to cater to a single language-pair.


## Track 1: Speech-Text Speech Translation

### General Information for All Language-Pairs

The submission format will be standardized across all language-pairs.
Participants can submit systems under two conditions:
- **Constrained condition:** systems are trained only on the datasets provided by the organizers (listed below)
- **Unconstrained condition:** systems can be trained with any resource, including pre-trained models. Multilingual models are allowed. 

Information about data and baselines are provided in the sections specific to each language pair. 

### Data for each Language Pair

Please see below for data pointers for each language pair.

### Mapuzugun to Spanish (arn-spa)
Mapudungun is a language isolate and the indigenous language of the Mapuche people, spoken by about 100,000-200,000 people in Chile and Argentina.

Data are based on the corpus described in [this paper](https://aclanthology.org/2020.lrec-1.350.pdf), providing more than 130 hours of Mapuzugun speech, along with transcriptions and translations in Spanish.

<strong>Data will be made available by February 5.</strong>

### Bemba to English (bem-eng)
Bemba is a Bantu language, spoken by over 10 million people in Zambia and other parts of Africa.

Data are based on the corpus described in [this paper](https://aclanthology.org/2023.acl-long.115/), providing 180 hours of Bemba speech, along with transcriptions and translations in English.
They will be available for download in a <a href="#">Github link</a> by <strong>Feb 5</strong>.

Additional Bemba speech data (with transcriptions) are available here:

- BembaSpeech [data](https://github.com/csikasote/BembaSpeech) [paper](https://arxiv.org/pdf/2102.04889.pdf)
- ZambeziVoice [data](https://github.com/unza-speech-lab/zambezi-voice) [paper](https://arxiv.org/pdf/2306.04428.pdf)



### Bhojpuri to Hindi (bho-hin)

Bhojpuri belongs to the Indo-Aryan language group. It is dominantly spoken in India’s western part of Bihar, the north-western part of Jharkhand, and the Purvanchal region of Uttar Pradesh. As per the 2011 Census of India, it has around 50.58 million speakers. Bhojpuri is spoken not just in India but also in other countries such as Nepal, Trinidad, Mauritius, Guyana, Suriname, and Fiji. Since Bhojpuri was considered a dialect of Hindi for a long time, it did not attract much attention from linguists and hence remains among the many lesser-known and less-resourced languages of India.

IWSLT participants may obtain the <a href="https://github.com/shashwatup9k/iwslt2026_bho-hi">Bhojpuri-Hindi speech translation data</a> without any cost. This corpus consists of 26 hours of audio speech data from the news domain and translations into Hindi text.

We point participants to additional Bhojpuri audio data (with transcriptions), parallel and monolingual corpora from here: 

- [ULCA-asr-dataset-corpus](https://github.com/Open-Speech-EkStep/ULCA-asr-dataset-corpus)
- [Bhojpuri-wav2vec2 based model](https://github.com/Open-Speech-EkStep/vakyansh-models#wav2vec2-based-models)
- [Bhojpuri Language Technological Resources (BHLTR)](https://github.com/shashwatup9k/bho-resources)

### Catalan to English (cat-eng)

Catalan is a Western Romance language spoken by over 10 million people.

<strong>Data will be made available by February 5.</strong>

### Central Kurdish to English (ckb-eng)

This task focuses on speech-to-text translation from Central Kurdish to English. Central Kurdish (ISO 639-3) with an estimated 8 million speakers, is the second most widely spoken dialect of the Kurdish language. It is spoken mainly in the Kurdistan regions of Iran and Iraq and uses a modified version of the Arabic script.

The task is based on the COMMUTE-Kurdish corpus, which contains 30 hours of spontaneous Central Kurdish speech collected from Kurdish media. The data are manually segmented, transcribed, and translated into English. The corpus covers multiple domains, including politics, culture, economy, sports, art, and science.

The COMMUTE-Kurdish dataset, complementary datasets, baseline models, evaluation instructions, and contact information are available on the task website:

<strong> Data: [here](https://lium.univ-lemans.fr/en/corpus-commute-kurdish/)</strong>

### Irish to English (gle-eng)
Irish (also known as Gaeilge) has around 170,000 L1 speakers and "1.85 million (37%) people across the island (of Ireland) claim to be at least somewhat proficient with the language". In the Republic of Ireland, it is the national and first official language. It is also one of the official languages of the European Union and a recognized minority language in Northern Ireland.

IWSLT participants may obtain the Irish-English speech translation data  from <a href="https://github.com/shashwatup9k/iwslt2026_ga-eng"> here</a>.

### Igbo to English (ibo-eng)

The Igbo language is a Niger-Congo language spoken by approximately 30–45 million people in Nigeria, Cameroon, and Equatorial Guinea.

Newly collected data is available [here](huggingface.co/datasets/McGill-NLP/african_celtic_dataset), and they are the same as the ones used for [the African and Celtic Speech-to-Speech Shared Task](https://iwslt.org/2026/african-celtic). We encourage interested participants to also consider participating in that task as well.

<strong>Pointers to additional data will be provided by February 5.</strong>

### Hausa to English (hau-eng)

Hausa is a Chadic language spoken by more than 100 million people in Nigeria and Niger.

Newly collected data is available [here](huggingface.co/datasets/McGill-NLP/african_celtic_dataset), and they are the same as the ones used for [the African and Celtic Speech-to-Speech Shared Task](https://iwslt.org/2026/african-celtic). We encourage interested participants to also consider participating in that task as well.

<strong>Pointers to additional data will be provided by February 5.</strong>

### Quechua to Spanish (que-spa)

Quechua is an indigenous language spoken by more than 8 million people in South America. It is mainly spoken in Peru, Ecuador, and Bolivia where the official high-resource language is Spanish. It is a highly inflective language based on its suffixes which agglutinate and found to be similar to other languages like Finnish. The average number of morphemes per word (synthesis) is about two times larger than English. English typically has around 1.5 morphemes per word and Quechua has about 3 morphemes per word. 

There are two main region divisions of Quechua known as Quechua I and Quechua II. This data set consists of two main types of Quechua spoken in Ayacucho, Peru (Quechua Chanka ISO:quy) and Cusco, Peru (Quechua Collao ISO:quz) which are both part of Quechua II and, thus, considered “southern” languages. We label the data set with **que** - the ISO code for Quechua II mixtures.

IWSLT participants may obtain the public Quechua-Spanish speech translation dataset along with the additonal parallel (text-only) data for the *unconstrained* task at no cost here: <a href="https://github.com/johneortega/IWSLT2026_Quechua_data">IWSLT 2026 QUE-SPA Data set</a>. IWSLT particpants should feel free to use any publicly available data for the *unconstrained* task. This includes a data set of nearly 50 hours of fully transcribed Quechua audio from previous shared tasks along with the introduction of a new data set this year which is about 8 hours of synthetic (post-edited) translations. A new addition this year is a *Quechua Collao* dataset which contains 15 hours of ASR data with Spanish translation. For assistance with the data sets, please email j.ortega@northeastern.edu.

### Catalan to English (ca-en)
Catalan (català) is a Western Romance language which has approximately 4.1 million L1 speakers and more than 10 million people who can speak the language across its territories. It is spoken primarily in Catalonia, the Valencian Community, the Balearic Islands, and parts of Aragon in Spain, as well as in Andorra, where it is the sole official language. Catalan is also spoken in parts of southern France (Northern Catalonia) and in the city of Alghero in Sardinia, Italy.

In Catalonia, the Valencian Community, and the Balearic Islands, Catalan is co-official with Spanish and is widely used in education, media, and public administration. It is recognized as a regional or minority language in several European regions and has the ISO 639-1 code ca.

IWSLT participants may obtain the public Catalan-English speech translation dataset at no cost here: <a href="https://github.com/rjzevallos/IWSLT_2026_Catalan_Dataset">IWSLT 2026 CA-EN Data set</a>. IWSLT particpants should feel free to use any publicly available data for the *unconstrained* task. For assistance with the data sets, please email rodolfo.zevallos@bsc.es.

### Yoruba to English (yor-eng)

The Igbo language is a Niger-Congo language spoken by approximately 50 million people in Nigeria, Benin, and Togo.

Newly collected data is available [here](huggingface.co/datasets/McGill-NLP/african_celtic_dataset), and they are the same as the ones used for [the African and Celtic Speech-to-Speech Shared Task](https://iwslt.org/2026/african-celtic). We encourage interested participants to also consider participating in that task as well.

<strong>Pointers to additional data will be provided by February 5.</strong>




## Submission

<!-- Description of expected submission format and submission instructions -->

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

<strong>Submission files should contain translations (or transcriptions) in the format of one per line following the format of the segments file (in sequence) corresponding to the test data splits.</strong>

We ask participants to email their submissions for all language pairs to the organizers in the following email address:
- iwslt.2026.lowres.submissions@gmail.com

Ideally, your email body should include a brief description of your system (which the organizers can use/modify for describing your submission in the Findings paper), and a brief explanation if you include multiple files per language. 


## Evaluation

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

Please follow the [general submission requirements](https://iwslt.org/2025/#submission-requirements), ensuring that your paper includes all necessary details for reproducing your system.


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
	<li> Mapuzugun:
		<ul>
			<li>Antonios Anastasopoulos, George Mason University</li>
			<li>Chutong Meng, George Mason University</li>
		</ul>
	</li>
	<li> Central Kurdish:
		<ul>
			<li>Mohammadamini Mohammad, University of Le Mans</li>
			<li>Antoine Laurent, University of Le Mans</li>
			<li>Marie Tahon, University of Le Mans</li>
		</ul>
	</li>
	<li> Irish, Bhojpuri:
		<ul>
			<li>Atul Kr. Ojha, University of Galway (atulkumar.ojha [email symbol] insight-centre.org)</li>
			<li>John P. McCae, University of Galway</li>
			<li> Yasmin Moslem, Bering Lab (only for Irish language pair) </li>
		</ul>
	</li>
	<li> Quechua, Catalan:
		<ul>
			<li>John E. Ortega, Northeastern University (j.ortega [email symbol] northeastern.edu)</li>
			<li>Rodolfo Zevallos, Universitat Pompeu Fabra (rodolfojoel.zevallos [email symbol] upf.edu)</li>
		</ul>
	</li>
</ul>


## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair(s): Antonios Anastasopoulos <antonis@gmu.edu>;  
Discussion: <iwslt-evaluation-campaign@googlegroups.com>
