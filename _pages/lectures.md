---
permalink: /lectures/
title: "Lectures"
classes: wide
---

<br/>
The ISCA SIGSLT lecture series is held periodically on Zoom, with recordings posted on [YouTube](https://www.youtube.com/playlist?list=PLMS8PIkS6c4jU-4KZdhFErTYMP7KmFRw-){:target="_blank"} for those who cannot join live.  
Zoom links are distributed through the [SIGSLT google group](https://groups.google.com/g/sigslt){:target="_blank"}.


## Speech Translation: Effectiveness, Efficiency, and Data
Jinming Zhao, PhD student at Monash University in Australia [(Contact)](mailto:jinming.zhao@monash.edu){:target="_blank"}.  

**Date:**  
<i class="fas fa-calendar-day"></i> Thurs 20 Oct 2022, 00:00 UTC [(9am JST / 2am CEST / 8pm EST / 5pm PST)](https://www.timeanddate.com/worldclock/converter.html?iso=20221020T000000&p1=1440&p2=248&p3=5805&p4=224&p5=179)

**Recording:**  
<i class="fas fa-video"></i> Watch on [YouTube](https://youtu.be/LodPoXYsAtQ){:target="_blank"}  

**Abstract:**  
Speech translation (ST) is a task of translating speech in one language into text in a foreign language. In this talk, I will discuss three avenues for advancing ST, from the perspectives of effectiveness, efficiency and data. First, it is a common practice in ST to jointly fine-tune a pretrained speech encoder and a text decoder. Yet, this exposes a modality gap, as the two modules are pretrained on different modalities. I will describe a novel Transformer-based adapter that we designed to bridge the gap and show that this leads to better translation quality. Secondly, we propose an adapter that can be seamlessly integrated with pretrained speech encoders, which are otherwise expensive to use. The integration leads to significantly reduced computation complexity for wav2vec2, while bringing better model performance. Lastly, we introduce a simple, scalable and effective data augmentation technique to convert text to speech on-the-fly. We demonstrate that synthetic speech generated via our approach works equally well as text-to-speech-generated speech.


**Bio:**  
Jinming Zhao is a PhD student at Monash University in Australia, under supervision of Professor Gholamreza Haffari and Dr Ehsan Shareghi. Her research focuses on improving representation for spoken language translation, and her works have been published at top-tier Speech/NLP conferences.


## State of the art and current challenges of MT for sign to spoken languages
Dr. Dimitar Shterionov, assistant professor in the Department of Cognitive Science and Artificial Intelligence at Tilburg University  
Dr. Mirella De Sisto, postdoctoral researcher in the Department of Cognitive Science and Artificial Intelligence at Tilburg University  

**Date:**  
<i class="fas fa-calendar-day"></i> Wed 14 Sept 2022, 15:00 UTC [(12am JST / 5pm CEST / 11am EST / 8am PST)](https://www.timeanddate.com/worldclock/converter.html?iso=20220914T150000&p1=1440&p2=248&p3=5805&p4=224&p5=179)

**Recording:**  
<i class="fas fa-video"></i> Watch on [YouTube](https://www.youtube.com/watch?v=W20MfKWGMiY){:target="_blank"}  

**Abstract:**  
Machine translation (MT) is a core technique for reducing language barriers that has advanced and seen many breakthroughs since it began in the 1950s, to reach quality levels comparable to humans. Despite the significant advances of MT for spoken languages in the recent couple of decades, MT is in its infancy when it comes to SLs. The complexity of the problem, automatically translating between SLs or SL and spoken languages, requires multi-disciplinary research. SLMT is lagging behind, in comparison to MT for spoken languages, for a number of reasons linked to challenges of technical as well as linguistic nature.
  
In this presentation, we discuss current approaches to SLMT and will dive into some of the challenges that the field is facing. We focus on those challenges which are related to linguistic properties of sign languages and to the format of the data available. We discuss possible approaches to some of them and, by doing that, we introduce our work in progress.

**Bio:**  
Dr. Dimitar Shterionov is an assistant professor in the Department of Cognitive Science and Artificial Intelligence at Tilburg University. He is the scientific coordinator of the [SignON project](https://signon-project.eu/). His current research focuses on low-resource MT, and, in particular, on MT for Sign Languages. He is an experienced researcher in MT and NLP, and an expert in a plethora of subtopics of MT such as quality estimation, automatic post-editing, evaluation of MT quality and usability, and speech-to-text and text-to-speech translation.

Dr. Mirella De Sisto is a postdoctoral researcher in the Department of Cognitive Science and Artificial Intelligence at Tilburg University. As a member of the SignON project, her current research focus is Sign Language MT and how to support its development with a linguistically-informed approach. Her expertise lies in the interface between linguistics and NLP and MT.


## Towards Streaming Speech Translation
Javier Iranzo-Sánchez, PhD student at the Universitat Politècnica de València.

**Date:**  
<i class="fas fa-calendar-day"></i> Tues 14 June 2022, 08:00 UTC [(5pm JST / 10am CET / 4am EST / 1am PST)](https://www.timeanddate.com/worldclock/converter.html?iso=20220614T080000&p1=1440&p2=248&p3=5805&p4=224&p5=179)

**Recording:**  
<i class="fas fa-video"></i> Watch on [YouTube](https://youtu.be/91btxw8ewcI){:target="_blank"}  

**Abstract:**  
This seminar introduces the task of Streaming Speech Translation, which is the task of translating an unbounded audio stream under real-time constraints. The different components of the Speech Translation pipeline (Automatic Speech Recognition, Segmentation, Simultaneous Translation, and Evaluation) will be explained in detail, paying special attention to some overlooked details that differ from the standard Speech Translation task.

**Bio:**  
Javier Iranzo-Sánchez is a PhD student at the Universitat Politècnica de València, under the supervision of Professor Jorge Civera and Professor Alfons Juan. His research topic is Simultaneous Speech Translation, and he has published multiple publications at top ASR and MT conferences. Currently, he is working as a Research Scientist at Apptek while finishing his thesis.


## Isochrony for Automatic Dubbing
Prashant Mathur, Senior Applied Scientist in Amazon AI.

**Date:**  
<i class="fas fa-calendar-day"></i> Thurs 5 May 2022, 23:00 UTC [(8am Fri JST / 1am Fri CET / 7pm Thurs EST / 4pm Thurs PST)](https://www.timeanddate.com/worldclock/converter.html?iso=20220505T230000&p1=1440&p2=248&p3=5805&p4=224&p5=179)

**Recording:**  
<i class="fas fa-video"></i> Watch on [YouTube](https://youtu.be/PaxRvWzBlOI){:target="_blank"}  

**Abstract:**  
In this talk, I will focus on the problem of isochrony in automatic dubbing for media localization where the goal is to maintain synchrony of translated dialogues and original video when the speakers are on-screen. This problem requires that we first identify the location of pauses in the translation and then ensure the speech-pause arrangement as in the source audio. I will first introduce our approaches on aligning the pauses from source speech to target translation (prosodic alignment), then review a recent work on isometric machine translation and a follow-up work on isochrony aware MT. I will end the talk by providing a brief overview of the [Isometric SLT shared task](https://iwslt.org/2022/isometric) we are organizing as a part of IWSLT.

**Bio:**  
Prashant is a Senior Applied Scientist in Amazon AI. His research focuses on improving the state of the art for machine translation, and domain adaptation with special attention to the problem of Automatic Dubbing. Prior to Amazon, he was a research scientist at eBay working on language generation with structured data and machine translation for eBay’s catalog content.


## Towards Augmented Speech Translation: Joint Speech Translation and Named Entity Recognition
Marco Gaido, PhD student at Fondazione Bruno Kessler (FBK), Italy

**Date:**  
<i class="fas fa-calendar-day"></i> Wed 6 April 2022, 16:00 UTC [(1am JST / 6pm CET / 12pm EST / 9am PST)](https://www.timeanddate.com/worldclock/converter.html?iso=20220406T160000&p1=1440&p2=248&p3=5805&p4=419&p5=224)

**Recording:**  
<i class="fas fa-video"></i> Watch on [YouTube](https://www.youtube.com/watch?v=g2fIcjVWgXY){:target="_blank"}  

**Abstract:**  
Translation is a complex task involving different levels of understanding of the content being handled. The process involves grasping the semantic meaning of the source, which is conveyed through the mentioned (named) entities, the specific terminology indicating peculiar elements, and the relationships between them. However, these aspects remain implicit in the output of automatic translation systems exclusively designed to generate fluent and adequate text. Going beyond these standard output quality objectives, we envisage "augmented translation" as the task of jointly generating the output together with explicit meaning-related enrichments suitable for downstream use. In this talk, we will discuss the application of this idea to the domain of live interpreting, in which handling named entities represents a daunting task. In this framework, we will present our work on systems that jointly translate speech and recognize named entities, discussing the main challenges, possible approaches, data requirements, experimental results, and future research directions.


## Simultaneous Speech-to-Speech Translation with Transformer-based Incremental ASR, MT, and TTS
Katsuhito Sudoh PhD, Associate Professor at the Nara Institute of Science and Technology (NAIST), Japan

**Date:**  
<i class="fas fa-calendar-day"></i> Tue 1 March 2022, 8:00 UTC [(5pm JST / 9am CET / 12am PCT)](https://www.timeanddate.com/worldclock/converter.html?iso=20220301T080000&p1=1440&p2=248&p3=5805&p4=224)

**Recording:**  
<i class="fas fa-video"></i> Watch on [YouTube](https://www.youtube.com/watch?v=PH6Zlki-1pg&list=PLMS8PIkS6c4jU-4KZdhFErTYMP7KmFRw-){:target="_blank"}  

**Abstract:**  
I’ll talk about our English-to-Japanese simultaneous speech-to-speech translation (S2ST) system. It has three Transformer-based incremental processing modules for S2ST: automatic speech recognition (ASR), machine translation (MT), and text-to-speech synthesis (TTS). We also evaluated its system-level latency in addition to the module-level latency and accuracy.  
([This work](https://ieeexplore.ieee.org/document/9660477) was originally presented at Oriental COCOSDA 2021). 

