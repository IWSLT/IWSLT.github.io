---
permalink: /2022/dialect
title: "Dialectal Speech Translation"
---

## Description

In some communities, two dialects of the same language are used by speakers under different settings. For example, in the Arabic-speaking world, Modern Standard Arabic (MSA) is used as spoken and written language for formal communications (e.g., news broadcasts, official speeches, religion), whereas informal communication is carried out in local dialects such as Egyptian, Moroccan, and Tunisian. This diglossia phenomenon poses unique challenges to speech translation. Often only the “high” dialect for formal communication has sufficient training data for building strong ASR and MT systems; the “low” dialect for informal communication may not even be commonly written.

The goal of this shared task is to advance dialectal speech translation in diglossic communities. Specifically, we focus on Tunisian-to-English speech translation, with additional ASR and MT resources in Modern Standard Arabic. Participants will be provided with the following datasets: 

-  (a) 160 hours of Tunisian conversational speech, with manual transcripts (written in Arabic and Buckwalter script)
-  (b) 200k lines of manual translations of the above Tunisian transcripts into English, making a three-way parallel data that supports end-to-end speech translation models
-  (c) 1200 hours of Modern Standard Arabic (MSA) broadcast news with transcripts for ASR, available from MGB-2
-  (d) ~13,000k lines of bitext in MSA-English for MT, available from OPUS (Opensubtitles, Multi-UN, QED, TED, GlobalVoices, News-Commentary)

Datasets (a) and (b) are new resources developed by the LDC, which will be released for free to the IWSLT participants. The development and test sets (~3 hours each) are also three-way parallel and have the same characteristics. These datasets have been manually segmented at the utterance level. Participants will build end-to-end or cascaded systems that take Tunisian speech as input and generate English text as final output. 

Participants can build systems for evaluation in any of these conditions:
- Basic condition: train on datasets (a) and (b) only. This uses only Tunisian-English resources; the smaller dataset and simpler setup makes this ideal for participants starting out in speech translation research. 
- Dialect adaptation condition: train on datasets (a), (b), (c), (d). The challenge is to exploit the large MSA datasets for transfer learning while accounting for lexical, morphological, and syntactic differences between dialects. This condition may be an interesting way to explore how multilingual models work in multi-dialectal conditions. 
- Unconstrained condition: participants may use public or private resources for English and more Arabic dialects besides Tunisian (e.g., CommonVoice, TEDx, NIST OpenMT, MADAR). This condition is cross-listed with the [low-resource shared task](low-resource.md).

We will provide ASR, MT, and ST baselines as reference for the participants. The main evaluation metric will be BLEU on the final English translation; we will also compute WER on Tunisian transcripts for participants who submit cascade systems. This new dataset from LDC is conversational in nature (similar in style to Spanish Fisher/CALLHOME), and should be interesting for both ASR and MT researchers.

The ultimate goal of this shared task is to explore how transfer learning between “high” and “low” dialects can enable speech translation in diglossic communities. Diglossia is a common phenomenon in the world. Besides Arabic vs. its dialects, other examples include Mandarin Chinese vs. Cantonese/Shanghainese/Taiwanese/etc., Bahasa Indonesia vs. Javanese/Sundanese/Balinese/etc., Standard German vs. Swiss German, and Katharevousa vs. Demotic Greek. We imagine that techniques from multilingual speech translation and low-resource speech translation shared tasks will be relevant; we also hope that new techniques that specifically exploit the characteristics of diglossia will be explored. 



## Organizers

- Kevin Duh (Johns Hopkins University) 
- Matthew Wiesner (Johns Hopkins University) 
- Paul McNamee (Johns Hopkins University) 
- Kenton Murray (Johns Hopkins University)

Please contact iwslt-evaluation-campaign@googlegroups.com for questions and clarifications about this task. 

<!-- Markdown notes: comments can be formed as above; bulleted lines start with a - ; if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line -->

