---
permalink: /2026/voice-cloning
title: "Cross-lingual Voice Cloning track"
toc: true
toc_sticky: true
---

## Motivation

Voice cloning is a type of speech synthesis task that aims to mimic the characteristics of an original voice for a new input text. Current systems have limited capabilities in diverse areas including as they support of a limited number of languages, struggle with scientific and domain-specific terminology, and show difficulty with code-switching scenarios. The task of voice cloning is used for diverse purposes including:

* **Speaker standardization:** In speech systems, voice cloning can be employed as a speaker standardization step, especially in commercial systems that require the final output to match certain voice characteristics. For example, during training data creation, a few samples from a voiceover artist can be licensed to be used for standardizing a huge amount of training data. Alternatively, speaker standardization can be applied as a post-processing step in speech synthesis. This can be more efficient and cost-effective than creating data from scratch.

* **Multilingual content creation:** Content creators can convert their audio into other languages in their voices.

* **Augmentative and alternative communication:** In general, speech synthesis can be used in assistive tools. Voice cloning can make the experience more personalized by mimicking the voice of people with special needs, or creating age-appropriate voices for teaching children.

## Description

The cross-lingual voice cloning task requires systems to synthesize speech in a target language while preserving the voice characteristics of a speaker from source language audio. Unlike traditional speech translation tasks, the cross-lingual voice cloning task focuses on transferring voice identity across languages while maintaining naturalness and intelligibility. Given a small set of enrollment (reference) utterances from a source speaker in language $L_s$ and text input in a target language $L_t$, systems must generate speech that:

1. Maintains the speaker identity and voice characteristics (timbre, prosody, speaking style) of the source speaker
2. Produces natural and intelligible speech in the target language $L_t$, with accurate translation
3. Handles appropriate phonetic adaptations across languages while preserving speaker identity

### Input

Participants will receive:

- **Reference audio**: Raw audio file(s) from target speaker
- **Target text**: Written text in target language $L_t$ to be synthesized

### Output

* Systems must produce synthesized audio in the target language that preserves the source speaker's voice characteristics.


## Data

Data will be released in January.

<!-- Details description of the data and links to download -->


## Baselines

Participants are allowed to use any **open-source** model(s).


## Submission

Systems will be submitted through a form that will be available by the time the evaluation period starts.

System description papers should follow the same instructions as those for the main conference, available [here](https://iwslt.org/2026/#submission-requirements).

### Important Dates

The preliminary timeline is below and may be subject to minor changes.
{: .notice--info}

| Date           | Event                                        |
| -------------- | -------------------------------------------- |
| Jan 25, 2026   | Release of shared task training and dev data |
| Apr 1-15, 2026 | Evaluation period                            |
| Apr 24, 2026   | System paper submission deadline             |
| May 15, 2026   | Notification of acceptance                   |
| June 1, 2026   | Camera ready deadline                        |
| July 3-4, 2026 | IWSLT conference                             |

**Note:** All deadlines are Anywhere on Earth (11:59PM UTC-12:00).


## Evaluation

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->


## Organizers

* Yasmin Moslem (ADAPT Centre, Trinity College Dublin)
* Ali Hatami (Insight Centre, Galway University)
* Atul Ojha (Insight Centre, Galway University)


## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair(s): Yasmin Moslem: <u>yasmin.moslem [email symbol] adaptcentre.ie</u>

#### Discussion: <iwslt-evaluation-campaign@googlegroups.com>
