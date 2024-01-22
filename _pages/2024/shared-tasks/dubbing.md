---
permalink: /2024/dubbing
title: "Dubbing track"
toc: true
toc_sticky: true
---

<!--
Markdown notes: comments can be formed as in this example;
bulleted lines start with a - ;
if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line
-->

## Description

This task focuses on **automatic dubbing**: translating the speech in a video into a new language such that the new speech is natural when overlayed on the original video. 

Participants will be given original videos (like this), along with their transcripts (e.g. "Sein Hauptgebiet waren es, romantische und gotische Poesie aus dem Englischen ins Japanische zu übersetzen."):

<video src="https://user-images.githubusercontent.com/3534106/217985339-fb31a3a5-7845-4d52-b651-0ab93e426c70.mp4" controls="controls" style="max-width: 600px;">
</video>

And will be asked to generate videos like this, dubbed into target language, in this case, English:

<video src="https://user-images.githubusercontent.com/3534106/217978682-d74d35b8-3a5f-4e46-82c2-94269e56b3b4.mp4" controls="controls" style="max-width: 600px;">
</video>

Automatic dubbing is a very [difficult/complex task](https://arxiv.org/abs/2212.12137). A unique aspect of dubbing is **isochrony** which refers to the property that the speech translation is time aligned with the original speaker’s video. When the speaker’s mouth is moving, a listener should hear speech; likewise, when their mouth isn’t moving, a listener should not hear speech. 

## Data

We will just operate in an unconstrained setting more inline with real world conditions where additional speech and parallel data is likely available.  Participants may use any public or private datasets or pre-trained models. 

#### German - English

We follow last year (2023) release of training and test data that can be found [here](https://github.com/amazon-science/iwslt-autodub-task/tree/main/data).

The training data for German-English direction is derived from [CoVoST2](https://arxiv.org/abs/2007.10310) and consists of:

* Source (German) text
* Desired target speech durations (e.g. 2.1s of speech, followed by a pause, followed by 1.3s of speech)
* Target (English) phonemes and durations corresponding to a translation which adheres to the desired timing

The test data consist of videos of native speakers reading individual German sentences from the CoVoST-2 test set. 

#### English - Chinese

In this task, we are adding a new language direction for dubbing, English-Chinese. In collaboration with subtitle task, we will use English videos as described [here](https://iwslt.org/2023/subtitling#development-and-evaluation-data) as dev and test sets. 


## Baseline

In German-English direction, we provide a complete [baseline](https://github.com/amazon-science/iwslt-autodub-task) (used to create the videos in the description above) as a starting point for participants. The baseline uses target factors to keep track of remaining durations and pauses while generating phonemes and durations in the target language. Those phones and durations are then passed through a publically available [text-to-speech](https://github.com/ming024/FastSpeech2) system. 

In English-Chinese, baseline systems are TBD. 

## Submission

TBD.

## Evaluation

Participant teams will submit English speech for a set of German videos, each containing one sentence from the CoVoST-2 test set. The new audio will be overlayed on the original video and the resulting video will be judged for it’s overall quality (both isochrony and translation quality). Exact details TBD. 

For English-Chinese direction, participants will be asked to generate target speech audio on subtitle test sets.

We will report automatic metrics for each submission, for both machine translation quality and isochrony adherence. 
Human evaluations are TBD.


## Organizers

* Brian Thompson (Amazon)
* Prashant Mathur (AWS AI Labs) 
* Xing Niu (AWS AI Labs)

## Contact

{pramathu,brianjt} AT amazon DOT com

