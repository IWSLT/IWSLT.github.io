---
permalink: /2026/voice-cloning
title: "Cross-Lingual Voice Cloning Track"
toc: true
toc_sticky: true
---

## Motivation

Voice cloning is a type of speech synthesis task that aims to mimic the characteristics of an original voice for a new input text. Current systems have limited capabilities in diverse areas as they support a limited number of languages, struggle with scientific and domain-specific terminology, and show difficulty with code-switching scenarios. The task of voice cloning is used for diverse purposes including:

* **Speaker standardization:** In speech systems, voice cloning can be employed as a speaker standardization step, especially in commercial systems that require the final output to match certain voice characteristics. For example, during training data creation, a few samples from a voiceover artist can be licensed to be used for standardizing a huge amount of training data. Alternatively, speaker standardization can be applied as a post-processing step in speech synthesis. This can be more efficient and cost-effective than creating data from scratch.

* **Multilingual content creation:** Content creators can convert their audio into other languages in their voices.

* **Augmentative and alternative communication:** In general, speech synthesis can be used in assistive tools. Voice cloning can make the experience more personalized by mimicking the voice of people with special needs, or creating age-appropriate voices for teaching children.

## Description

The cross-lingual voice cloning task requires systems to synthesize speech in a target language while preserving the voice characteristics of a speaker from source language audio. Unlike traditional speech translation tasks, the cross-lingual voice cloning task focuses on transferring voice identity across languages while maintaining naturalness and intelligibility. Given a small set of enrollment (reference) utterances from a source speaker in language L<sub>s</sub> and text input in a target language L<sub>t</sub>, systems must generate speech that:

1. Maintains the speaker identity and voice characteristics (timbre, prosody, speaking style) of the source speaker
2. Produces natural and intelligible speech in the target language L<sub>t</sub>
3. Handles appropriate phonetic adaptations across languages while preserving speaker identity

### Input

Participants will receive:

- **Reference audio:** Raw audio file(s) from the source speaker. This audio is used to mimic the speaker characteristics.
- **Target text:** Written text in the target language L<sub>t</sub> to be synthesized. This text can have different content from what is spoken in the reference audio.

### Output

* Systems must produce synthesized audio in the target language that preserves the source speaker's voice characteristics.

### Languages

* **Source language:** English
* **Target languages:** Arabic, Chinese, and French

Participants may submit to one or all of the target languages for official evaluation. Building a model for each language is possible, but building one multilingual model is encouraged.

## Baselines

* Participants are allowed to use any **open-source** model(s). This includes but not limited to Qwen3-TTS, Qwen3-Omin, IndexTTS2, CosyVoice3, OpenVoice2, or VoxCPM. Only open-source models can be used.

## Data

### Training and Dev Data

* Participants may use any suitable training and dev data
* It is recommended to integrate the [ACL 60/60 dataset](https://huggingface.co/datasets/ymoslem/acl-6060) since the blind dataset will include utterances in the same domain.

### Blind Data

<!-- The blind test data that is required for submission is going to be released before the evaluation period starts. -->

The blind test data that is required for submission is as follows:
- **Reference audio:** [link](https://machinetranslation.io/files/iwslt26cloning/audio.zip)
- **Target text:** [link](https://machinetranslation.io/files/iwslt26cloning/text.zip)


## Submission

<!-- Systems will be submitted through a form that will be available before the evaluation period starts. -->

* Submit one zip file per language.
* Required zip filename format: `{team}_{language}.zip` (example: `tcd_ar.zip`)
* Language codes: Arabic (ar), Chinese (zh), French (fr)
  
**Inside each zip archive:**

* Include generated wav files only.
* Required generated wav filename format: `{language}_{lineNumber}_{originalName}.wav` (example: `ar_023_2023.acl-long.3.wav`)
* `lineNumber` must be the source-text line ID (zero-padded 1-based).
* `originalName` must exactly match the reference audio stem (without .wav).

Before submission, please run the [verify_submission_naming.py](http://machinetranslation.io/files/iwslt26cloning/verify_submission_naming.py) script. Here is a Python usage example:
```
python3 verify_submission_naming.py /path/to/submission --language ar --source-file /path/to/arabic.txt --reference-dir /path/to/ref_audio
```

**Submission form:** Please submit your systems by 18th April 2026 at: [https://forms.office.com/e/cDcxEuJ4bA](https://forms.office.com/e/cDcxEuJ4bA)


## System Description Paper

System description papers should follow the same instructions as those for the main conference, available [here](https://iwslt.org/2026/#submission-requirements).

All participants are encouraged to submit a paper describing their submitted system(s). Aspects that must be covered by the system description paper include but not limited to:

* Technical details of the system including, data, models, and approaches.
* Evaluation should be clearly documented.
* Ethical considerations regarding data licensing and potential misuse should be addressed.

### Important Dates

| Date                | Milestone                                      |
|---------------------|------------------------------------------------|
| Jan 1, 2026         | Release of shared task training and dev data   |
| Apr 1, 2026         | Release of shared task blind test data         |
| Apr 1-18, 2026      | Evaluation period (shared task)               |
| Apr 18, 2026        | System submission deadline (shared task)      |
| Apr 24, 2026        | System paper submission deadline (shared task)|
| May 15, 2026        | Notification of acceptance                     |
| June 1, 2026        | Camera ready deadline (all papers)             |
| July 3-4, 2026      | IWSLT conference                               |

**Note:** All deadlines are 11:59PM Anywhere on Earth (UTC-12:00).


## Evaluation

Systems will be evaluated on the following aspects:

* **Content Consistency:** To evaluate content consistency, the generated audio is converted to text using a speech recognition model, and then the generated transcript is compared to the actual text.
* **Speaker Similarity:** This measures how well the output matches the source speaker’s voice characteristics. This is computed as the cosine similarity between speaker embeddings.
* **Speech Quality:** Naturalness, intelligibility, and absence of artifacts are assessed using objective quality metrics.

## Expression of Interest

Although it is not required, it is highly recommended to fill out the [expression of interest form](https://forms.office.com/e/PYgKd2gFTr) once you decide to participate in the Cross-Lingual Voice Cloning Track to help the organizers anticipate the effort and resources required for evaluation. Looking forward to your participation! :)

## Organizers

* Yasmin Moslem (ADAPT Centre, Trinity College Dublin)
* Ali Hatami (Insight Centre, Galway University)
* Atul Ojha (Insight Centre, Galway University)


## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair(s): Yasmin Moslem: <u>yasmin.moslem [email symbol] adaptcentre.ie</u>

#### Discussion: <iwslt-evaluation-campaign@googlegroups.com>
