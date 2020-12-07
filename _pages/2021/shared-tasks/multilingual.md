---
permalink: /2021/multilingual
title: "Multilingual Speech Translation"
---

## Description

While multilingual translation is an established task, until recently parallel resources did not exist for speech translation from languages other than English.
Multilingual models enable transfer from related tasks, important for low-resource language pairs, and further, extend the possibility of zero-shot translation between languages which may have been observed in other pairs. 

In addition to parallel speech and translations, many sources of data may be useful for speech translation: monolingual speech and transcripts, parallel text, and data from other languages or language pairs. 
While cascades of separately trained automatic speech recognition (ASR) and machine translation (MT) models can leverage all of these data sources, how to most effectively do so with end-to-end models remains an open and exciting research question.

Motivated by the above, the multilingual speech translation task will provide data for two conditions: **supervised**, and **zero-shot**. This will be a **constrained task**: submissions should use the provided data only (e.g., no models pretrained on external data), but may use the provided resources in any way. 
![[multilingual speech translation task data image]](https://iwslt.github.io/assets/images/mst2021-data.png)
At evaluation time, we will provide speech in four languages and ask participants to generate translations in both English and Spanish.
Submitting generated transcripts (ASR) for evaluation is not mandatory but strongly encouraged as a useful diagnostic. 

We look forward to your creative submissions!  

Data, baselines, and evaluation scripts will be released Feb. 1, 2020.
{: .notice--warning}


## Organizers

Elizabeth Salesky (JHU, USA)  
Jake Bremerman (UMD, USA)  
Jan Niehues (Maastricht University, Netherlands)  
Matt Post (JHU, USA)  
Matthew Wiesner (JHU, USA)
