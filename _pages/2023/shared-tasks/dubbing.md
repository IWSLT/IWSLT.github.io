---
permalink: /2023/dubbing
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

Participants will be given German videos like this, along with their transcripts (e.g. "Sein Hauptgebiet waren es, romantische und gotische Poesie aus dem Englischen ins Japanische zu übersetzen."):

<video src="https://user-images.githubusercontent.com/3534106/217985339-fb31a3a5-7845-4d52-b651-0ab93e426c70.mp4" controls="controls" style="max-width: 600px;">
</video>

And will produce videos like this, dubbed into English:

<video src="https://user-images.githubusercontent.com/3534106/217978682-d74d35b8-3a5f-4e46-82c2-94269e56b3b4.mp4" controls="controls" style="max-width: 600px;">
</video>

Automatic dubbing is a very [difficult/complex task](https://arxiv.org/abs/2212.12137), and for this shared task we will focus on the characteristic which is most unique to dubbing: **isochrony**. Isochrony refers to the property that the speech translation is time aligned with the original speaker’s video. When the speaker’s mouth is moving, a listener should hear speech; likewise, when their mouth isn’t moving, a listener should not hear speech. 

To make this task accessible for small academic teams with limited training resources, we make some simplifications: First, we assume the input speech has already been converted to text using an ASR system and the desired speech/pause times have been extracted from the input speech. Second, to alleviate the challenges of training a TTS model, the output is defined to be [phonemes](https://en.wikipedia.org/wiki/Phoneme) and their durations. These phonemes and durations will be played through [this open-source text-to-speech model](https://github.com/mtresearcher/FastSpeech2) to produce the final speech.

To illustrate, here’s an example in which “hallo! wei gehts?” is translated to “hi! how are you?” such that the output will fit in the desired target speech durations of 0.4s and 1.3s, with a pause in between:
<div class='fill-screen'><img class='make-it-fit' 
         src='https://user-images.githubusercontent.com/3534106/218159375-443e8168-147f-4963-b88a-5adb0b789d83.png'>
</div>

<img src='https://user-images.githubusercontent.com/3534106/218159375-443e8168-147f-4963-b88a-5adb0b789d83.png' width="200">

<img src='https://user-images.githubusercontent.com/3534106/218159375-443e8168-147f-4963-b88a-5adb0b789d83.png' width="2000">

<img src='https://user-images.githubusercontent.com/3534106/218159375-443e8168-147f-4963-b88a-5adb0b789d83.png' width="20000">

<img src="https://user-images.githubusercontent.com/3534106/218159375-443e8168-147f-4963-b88a-5adb0b789d83.png" width=80% height=80%>

<img width="720" alt="dubbing10" src="https://user-images.githubusercontent.com/3534106/218168605-08fc7943-137a-4b61-b2cd-619ef27ce96b.png">

## Data

Official training and test data can be found [here](https://github.com/amazon-science/iwslt-autodub-task/tree/main/data).

The training data is derived from [CoVoST2](https://arxiv.org/abs/2007.10310) and consists of:

* Source (German) text
* Desired target speech durations (e.g. 2.1s of speech, followed by a pause, followed by 1.3s of speech)
* Target (English) phonemes and durations corresponding to a translation which adheres to the desired timing


The test data consist of videos of native speakers reading individual German sentences from the CoVoST-2 test set. 

In order to make the shared task approachable for small academic teams, we will have a constrained setting in which participants may use only the official data listed above and may not use any pretrained models.

Additionally, we will have an unconstrained setting more inline with real world conditions where additional speech and parallel data is likely available.  In the unconstrained setting, participants may use any publicly available datasets or pre-trained models, as long as they are licensed for research purposes. 


## Baseline

We provide a complete [baseline](https://github.com/amazon-science/iwslt-autodub-task) (used to create the videos in the description above) as a starting point for participants. The baseline uses target factors to keep track of remaining durations and pauses while generating phonemes and durations in the target language. Those phones and durations are then passed through a publically available [text-to-speech](https://github.com/ming024/FastSpeech2) system. 

## Submission

Details TBA.


## Evaluation

Participant teams will submit English speech for a set of German videos, each containing one sentence from the CoVoST-2 test set. The new audio will be overlayed on the original video and the resulting video will be judged for it’s overall quality (both isochrony and translation quality). Exact details TBA. 

We will also report automatic metrics for each submission, for both machine translation quality and isochrony adherence. However, human judgements will be the primary evaluation method. 


## Organizers

* Brian Thompson (AWS AI Labs)
* Prashant Mathur (AWS AI Labs)
* Alexandra Chronopoulou (Center for Information and Language Processing, LMU)
* Proyag Pal (University of Edinburgh)


## Contact

brianjt at amazon dot com
  
Discussion: <iwslt-evaluation-campaign@googlegroups.com>
