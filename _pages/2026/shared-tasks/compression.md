---
permalink: /2026/compression
title: "Compression track"
toc: true
toc_sticky: true
---

<!--
Markdown notes: comments can be formed as in this example;
bulleted lines start with a - ;
if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line
-->

## Description
Text and speech foundation models have revolutionized many natural language processing tasks, including speech-to-text translation. However, their large size and high computational demands pose significant challenges when deploying these models in real-world scenarios, particularly in resource-constrained environments such as mobile devices, embedded systems, and edge computing. Reducing the size of large, general-purpose models while preserving or even improving their performance in specific tasks or language settings is essential for making them more efficient, accessible, and sustainable. This task focuses on evaluating participants’ ability to apply model compression techniques to a large multilingual speech-to-text model, balancing the need for accessibility and deployment feasibility with the requirement for good performance in English-German and English-Chinese speech translation.

<!-- Description the task, the languages, and the type of data -->

## Objectives

The goal of this task is to evaluate participants’ ability to effectively reduce the size of a large multilingual speech-to-text foundation model while minimizing performance drops in the task of translating English speech to written German or Chinese text. The model in question, [Qwen2-Audio](https://huggingface.co/Qwen/Qwen2-Audio-7B) (Chu et al., 2024), has been selected for its size (8.2 billion parameters, requiring approximately 16 GB of memory storage), its support to a variety of speech processing tasks across multiple language directions, and its permissive license (Apache 2.0). Due to its computational expense, memory-intensive nature, and versatility, it is an ideal candidate for task-oriented model compression.
The evaluation focuses on innovative compression techniques that strike a balance between compactness and performance, paving the way for the development of more accessible and easily deployable speech translation systems. Accordingly, this first edition of the task concentrates on:
* **Model Reduction**: shrink the size of the foundation model, defined by its number of parameters and memory usage, to make it more suitable for resource-limited settings.
* **Translation Performance**: maintain high translation quality despite the size reduction, ensuring the practical value and reliability of the compressed models.

While computational efficiency (i.e., speed) is recognized as a critical factor for deploying models in resource-constrained environments, it is excluded from the evaluation framework in this initial round. However, the task will follow a phased approach over the years, with future rounds set to include computational efficiency, thereby broadening the evaluation scope.

## Permitted Model Compression Techniques

The allowed techniques for reducing the model focus solely on modifying or optimizing the model’s internal parameters **<ins>while ensuring that the final compressed model remains strictly derived from the original</ins> [Qwen2-Audio](https://huggingface.co/Qwen/Qwen2-Audio-7B) <ins>model</ins>**.

Therefore, eligible techniques include pruning (i.e. the removal of less important neurons and/or entire layers within the model, by identifying and reducing parameters that contribute minimally to the model’s output), quantization (i.e. the reduction of the precision of the model’s weights (e.g., from 32-bit to 16-bit, 8-bit, or less) to lower the model’s memory footprint), distillation (i.e. the creation of a smaller “student” model derived from Qwen2-Audio, for instance through pruning, to replicate the behavior of the original “teacher” model), as well as any other technique that produces a compressed counterpart of the original model.

Compression techniques can be used either in isolation or in combination.

## Data Conditions
<!-- Details description of the data and links to download -->
<!-- Data will be released in January. -->

Participants can submit their runs under two data conditions: **constrained** and **unconstrained**. The two conditions differ in the datasets allowed to support the model compression process (e.g., for fine-tuning the reduced model after pruning, quantization, or other compression techniques, or for training the student model in knowledge distillation using the outputs of the larger teacher model).

* ***Constrained*** In this condition, participants are allowed to use only the [ACL60/60](https://aclanthology.org/attachments/2023.iwslt-1.2.dataset.zip) data. These data are identical in terms of size and source audio content for the two language directions and, though small, they are domain-consistent with the [evaluation sets](https://iwslt.org/2025/model-compression#test-data).

* ***Unconstrained*** In this condition, there are no restrictions on data usage.

<!-- ## Baselines  -->
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->

## Submission

The evaluation will be performed using the Meetween SPEECHM Evaluation Server. More info are coming in March.

## Evaluation

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

The evaluation will be carried out separately for each track (constrained/unconstrained) and language, and will consider two key dimensions:

1. *Quality*, automatically assessed based on a panel of LLM-as-judges to minimize metric bias. 

2. *Size* of the model on disk.

Translation quality will be assessed using COMET, comparing the model’s output to reference translations. As in the offline track, COMET scores will be calculated on the test sets through automatic resegmentation of the hypothesis, aligned with the reference translation by mwerSegmenter. The detailed evaluation script can be found in the SLT.KIT.

Results will be reported in a table showing all metrics. In addition, differences between systems in terms of the quality-size trade-off will be presented using Pareto frontier ranking, through quality-size graphs highlighting the models that are not outperformed in both dimensions at once.

Multiple submissions are allowed for each track and language direction. If participants submit multiple systems for the track and language, they must explicitly designate one as the PRIMARY submission, while all others will be considered CONTRASTIVE submissions. If no submission is marked as PRIMARY, the most recent one (determined by the file timestamp) will automatically be used as the PRIMARY submission.


## Organizers

<!-- List of organizers' names and affiliations -->

Marco Gaido (Fondazione Bruno Kessler)  
Matteo Negri (Fondazione Bruno Kessler)  
Marco Turchi (Zoom Video Communications)  
Sebastian Stüker (Zoom Video Communications)  
Jan Niehues (Karlsruhe Institute for Technology)  

## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chairs: Marco Gaido <mgaido@fbk.eu> & Matteo Negri <negri@fbk.eu>;  
Discussion: <iwslt-evaluation-campaign@googlegroups.com>
