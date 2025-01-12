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

The low-resource shared task will, for the first time, involve three tracks:
<ul>
	<li> Track 1: A "traditional" speech-to-text translation track focusing on XX typologically diverse language-pairs.</li>
	<li> Track 2: A speech-to-speech translation track, focusing on XX Indic languages. </li>
	<li> Track 3: A data track, inviting participants to provide open-sourced speech translation datasets for under-resourced languages.</li>
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

### Dialectal Arabic to English (ara-eng)

This language pair will focus on evaluating performance on one Arabic vernacular:
<ul>
	<!--<li> Tunisian (ISO-3 code: aeb)</li>-->
	<li> North Levantine (ISO-3 code: apc) </li>
</ul>

We point the participants to training data across different Arabic varieties:

 <!--- The **aeb-eng** training data are the same as the one used in the previous IWSLT tasks: <a href="https://iwslt.org/2022/dialect">https://iwslt.org/2022/dialect</a>.  We suggest you follow the train/dev/test1 split instructions according to the linked webpage.-->
 - The **apc-eng** validation/testing data (with transcriptions) can be found [here](https://github.com/ufal/IWSLT2024_Levantine_Arabic_data). Participants are provided with about 120k lines of multi-parallel North Levantine-MSA-English textual data, that can be downloaded from the [LINDAT/CLARIAH-CZ Repository](https://lindat.mff.cuni.cz/repository/xmlui/handle/11234/1-5033). For the speech data, we recommend two LDC resources: BBN/AUB DARPA Babylon Levantine corpus ([Speech + Transcript]((https://catalog.ldc.upenn.edu/LDC2005S08))) and the Levantine Arabic QT Training Data Set 5 corpus ([Speech](https://catalog.ldc.upenn.edu/LDC2006S29) + [Transcript](https://catalog.ldc.upenn.edu/LDC2006T07)).

We also provide links to speech recognition datasets that include Arabic data:
- OpenSLR Resource [SLR46](https://www.openslr.org/46/)
- OpenSLR Resource [SLR48](https://www.openslr.org/48/)
- OpenSLR Resource [SLR108](https://www.openslr.org/108/)
- OpenSLR Resource [SLR132](https://www.openslr.org/132/)

### Bemba to English (bem-eng)
Bemba is a Bantu language, spoken by over 10 million people in Zambia and other parts of Africa.

Data are based on the corpus described in [this paper](https://aclanthology.org/2023.acl-long.115/), providing 180 hours of Bemba speech, along with transcriptions and translations in English.
They are available for download in this <a href="#">Github link</a>.

Additional Bemba speech data (with transcriptions) are available here:

- BembaSpeech [data](https://github.com/csikasote/BembaSpeech) [paper](https://arxiv.org/pdf/2102.04889.pdf)
- ZambeziVoice [data](https://github.com/unza-speech-lab/zambezi-voice) [paper](https://arxiv.org/pdf/2306.04428.pdf)

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

Details on  Estonian.

Data pointers.

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

IWSLT participants may obtain the public Quechua-Spanish speech translation dataset along with the additonal parallel (text-only) data for the *constrained* task at no cost here: <a href="https://github.com/Llamacha/IWSLT2024_Quechua_data">IWSLT 2024 QUE-SPA Data set</a>. IWSLT particpants should also feel free to use any publicly available data for the *unconstrained* task. This includes a data set of nearly 50 hours of fully transcribed Quechua audio from previous shared tasks. For assistance with the data sets, please email j.ortega@northeastern.edu and rodolfojoel.zevallos@upf.edu.


### Baselines

<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->
Coming soon!

### Submission

<!-- Description of expected submission format and submission instructions -->
Coming soon!

### Evaluation

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->
Coming soon!

## Track 2: Speech-to-Speech Translation

The second track of this year's Shared Task focuses on speech-to-speech translation for four languages spoken in the Indian subcontinent: Hindi, English, Bengali, and XXX.

More details below (coming soon!).

### Data

Data will be released in January.

<!-- Details description of the data and links to download -->


### Baselines

Coming soon!
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->


### Submission

Coming soon!
<!-- Description of expected submission format and submission instructions -->


### Evaluation

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->
Coming soon!


## Track 3: Training and Evaluation Data Track

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
Discussion: <iwslt-evaluation-campaign@googlegroups.com>
