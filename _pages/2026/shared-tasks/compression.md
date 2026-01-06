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
<!-- Description of expected submission format and submission instructions -->

This year, the evaluation will be performed using the MeeTween SPEECHM centralized evaluation server: [SPEECHM Evaluation Server](https://iwslt2025.speechm.cloud.cyfronet.pl/).

### General Guidelines

* Multiple run submissions are allowed, but participants must explicitly indicate one PRIMARY run for each track. All other run submissions are treated as CONTRASTIVE runs. In the case that none of the runs is marked as PRIMARY, the latest submission (according to the file time-stamp) for the respective track will be used as the PRIMARY run.
  
* Scoring will be case-sensitive and will include punctuation. Submissions have to be in plain UTF-8 text format, with one sentence per line. Tags such as applause, laughing, etc are not considered during the evaluation.
  
* Once logged in to the [SPEECHM Evaluation Server](https://iwslt2025.speechm.cloud.cyfronet.pl/), the submission process requires participants to create one or more Models for each language pair they intend to participate in (English-German, English-Chinese).
  
* For each chosen language pair, multiple Models can be created based on the training condition (CONSTRAINED / UNCONSTRAINED) and the submission type (PRIMARY / CONTRASTIVE).
  
* The created Model(s) must be used to submit runs for each of the test sets released for the chosen language pair (i.e., 1 test set for English-Chinese, and 4 test sets for English-German).
  
* If any issues are identified, the submitted runs can be deleted or replaced with newer runs.

### Submission Steps

Once logged in to [SPEECHM](https://iwslt2025.speechm.cloud.cyfronet.pl/), proceed through the following two steps.

<a id="downloadTest"></a>
#### STEP 0: Download and process the test data
    0.1 Click on “Test sets” (at the top of the page).
    0.2 Click on the “Model Compression” button associated with the “IWSLT25INSTRUCT” test set at top of the list.
    0.3 Download the test sets for the language pair(s) chosen for participation  (1 test set for en-de, 1 test set for en-zh).
    0.4 Process the test data to obtain your candidate submission file (to be stored in plain UTF-8 text format, one sentence per line)

#### STEP 1: Create a New Model 

    1.1 Click on “My submissions” (at the top of the page).
    1.2 Click on “New model” (button at the top right).
    1.3 Create a new model:
       Insert the Model Name using the standardized format:
       
         ${TEAM}_IWSLT25_ModelCompression_${LANGUAGE_PAIR}_${BIN}_${CONDITION}_${SUBMISSION_TYPE}
         
          Where:
           - ${TEAM} → Short name of your team (e.g., KIT)
           - ${LANGUAGE_PAIR} → Choose from [en-de, en-ar, en-zh]
           - ${BIN} → Choose from [Bin1, Bin2, Bin3, Bin4, Bin5]
           - ${CONDITION} → Choose from [constrained, unconstrained]
           - ${SUBMISSION_TYPE} → Choose from [primary, contrastive]

           Example Model Names:
             KIT_IWSLT25_ModelCompression_en-de_Bin3_constrained_primary  
             KIT_IWSLT25_ModelCompression_en-de_Bin3_constrained_contrastive 
     1.4 Insert Description
       Provide a brief but accurate description of your model, including:
          - Exact storage size [MANDATORY]
          - Number of parameters [MANDATORY]
          - Applied Compression techniques [MANDATORY]
          - Datasets used [MANDATORY for submissions in the unconstrained condition]
          - Any relevant additional details (e.g. computational efficiency metrics like inference time and FLOPs) [OPTIONAL] 
     1.5 Consent Option (optional)
       Consider enabling “Consents” to freely release your submitted system output data.
     1.6 Select Task Compatibility
       Choose the Model compression Task Id in the compatibility map.
     1.7 Click “Create Model” (a “Model created” message will appear on the top right).

#### STEP 2: Submit Your Processed Test Set

    2.1 Go to “My Submissions”.
    2.2 Click on the specific model created in STEP 1 
   (e.g., KIT_IWSLT25_ModelCompression_en-de_Bin3_constrained_primary).
    2.3 Click the “MODEL COMPRESSION Hypotheses” button.
    2.4 Once you have generated the outputs with your model for the test set, click “Upload hypothesis” for the intended submission:
   ${TESTSET} / ${LANGUAGE_PAIR} (e.g., IWSLT25INSTRUCT / en-de)
    2.5 Upload your submission file (plain UTF-8 text format, one sentence per line).

### Manage Your Submission

#### Download or Delete a Submission

    1 Click on “My Submissions”.
    2 Click on the model associated with the submitted run 
   (e.g., KIT_IWSLT25_ModelCompression_en-de_Bin3_constrained_primary).
    3 Click on the “MODEL COMPRESSION Hypotheses” button.
    4 Use the three-dot menu on the right to:
    - Download the submitted run (hypothesis).
    - Delete the submitted run and confirm.

#### Replace a Submission
    1 Delete your existing run.
    2 Submit a new run file (repeat STEP 2 of “Submission steps”).

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
Chair: Marco Gaido <mgaido@fbk.eu>;  
Discussion: <iwslt-evaluation-campaign@googlegroups.com>
