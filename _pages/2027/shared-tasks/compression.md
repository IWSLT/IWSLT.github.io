---
permalink: /2027/compression
title: "Model Compression"
toc: true
toc_sticky: true
---

## Description

Text and speech foundation models have revolutionized many natural language processing tasks, including speech-to-text translation. However, their large size and high computational demands pose significant challenges when deploying these models in real-world scenarios, particularly in resource-constrained environments such as mobile devices, embedded systems, and edge computing.

Reducing the size of large, general-purpose models while preserving or even improving their performance in specific tasks or language settings is essential for making them more efficient, accessible, and sustainable. This task evaluates model compression techniques for speech-to-text translation, balancing accessibility and deployment feasibility with translation performance.

## Objectives

The task evaluates participants' ability to reduce the size of large multilingual speech-to-text foundation models while minimizing performance losses. It focuses on compression techniques that balance compactness and performance, supporting the development of more accessible and easily deployable speech translation systems.

- **Model reduction:** Reduce a foundation model's number of parameters and memory usage to make it more suitable for resource-limited settings.
- **Translation performance:** Maintain high translation quality despite size reductions, ensuring the practical value and reliability of compressed models.

## Permitted Model Compression Techniques

Eligible techniques include pruning, quantization, distillation, and other methods that produce a compressed counterpart of the original model. Compression techniques may be used either in isolation or in combination.


## Evaluation

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

The evaluation will be carried out separately for each track (constrained/unconstrained) and language, and will consider two key dimensions:

1. *Quality*, assessed through automatic metrics. 

2. *Size* of the model on disk.

Translation quality will be assessed using COMET as primary metric, comparing the model’s output to reference translations. As in the offline track, COMET scores will be calculated on the test sets through automatic resegmentation of the hypothesis, aligned with the reference translation by mwerSegmenter. 

Results will be reported in a table showing all metrics. In addition, differences between systems in terms of the quality-size trade-off will be presented using Pareto frontier ranking, through quality-size graphs highlighting the models that are not outperformed in both dimensions at once.

Multiple submissions are allowed for each track and language direction. If participants submit multiple systems for the track and language, they must explicitly designate one as the PRIMARY submission, while all others will be considered CONTRASTIVE submissions. If no submission is marked as PRIMARY, the most recent one (determined by the file timestamp) will automatically be used as the PRIMARY submission.

## Test data 
All test data can be downloaded from the [SPEECHM Evaluation Server](https://speechm.cloud.cyfronet.pl/0000005), see Submission STEP 0 below. 

## Submission

The evaluation will be performed using the MeeTween SPEECHM centralized evaluation server:
[SPEECHM Evaluation Server](https://speechm.cloud.cyfronet.pl/0000005).

### General Guidelines

* Multiple run submissions are allowed, but participants must explicitly indicate one PRIMARY run for each track. All other run submissions are treated as CONTRASTIVE runs. In the case that none of the runs is marked as PRIMARY, the latest submission (according to the file time-stamp) for the respective track will be used as the PRIMARY run.

* Scoring will be case-sensitive and will include punctuation. Submissions have to be in plain UTF-8 text format, with one sentence per line. Tags such as applause, laughing, etc are not considered during the evaluation.


* Once logged in to the  [SPEECHM Evaluation Server](https://speechm.cloud.cyfronet.pl/0000005), the submission process requires participants to create one or more Models for each language pair they intend to participate in (English-German, English-Chinese).

* For each chosen language pair, multiple Models can be created based on the training condition (CONSTRAINED / UNCONSTRAINED) and the submission type (PRIMARY / CONTRASTIVE).

* The created Model(s) must be used to submit runs for each of the test sets released for the chosen language pair (i.e., **5 test sets for English-Chinese**, and **6 test sets for English-German**).

* If any issues are identified, the submitted runs can be deleted or replaced with newer runs.

### Submission Steps

Once logged in to [SPEECHM Evaluation Server](https://speechm.cloud.cyfronet.pl/0000005), proceed through the following two steps. 


<a id="downloadTest"></a>
#### STEP 0: Download and process the test data
    0.1 Click on “Test sets” (at the top of the page).
    0.2 Click on the “Model Compression” button associated with any of the visible test sets in the list.
    0.3 Download ALL the test sets for the language pair(s) chosen for participation  (6 test set for en-de, 5 test set for en-zh).
    0.4 Process the test data to obtain your candidate submission file (to be stored in plain UTF-8 text format, one sentence per line)


#### STEP 1: Create a New Model

<!-- To create a new model, follow these steps: --> 

    1.1 Click on “My submissions” (at the top of the page).
    1.2 Click on “New model” (button at the top right).
    1.3 Create a new model:
       Insert the Model Name using the standardized format:
       
         ${TEAM}_IWSLT27_ModelCompression_${LANGUAGE_PAIR}_${CONDITION}_${SUBMISSION_TYPE}
         
          Where:
           - ${TEAM} → Short name of your team (e.g., KIT)
           - ${LANGUAGE_PAIR} → Choose from [en-de, en-ar, en-zh]
           - ${CONDITION} → Choose from [constrained, unconstrained]
           - ${SUBMISSION_TYPE} → Choose from [primary, contrastive]

           Example Model Names:
             KIT_IWSLT27_ModelCompression_en-de_constrained_primary  
             KIT_IWSLT27_ModelCompression_en-de_constrained_contrastive 
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
       (e.g., KIT_IWSLT27_ModelCompression_en-de_constrained_primary).
    2.3 Click the “MODEL COMPRESSION Hypotheses” button.
    2.4 Once you have generated the outputs with your model for the test set, click “Upload hypothesis” for the intended submission:
       ${TESTSET} / ${LANGUAGE_PAIR} (e.g., TVSERIES / en-de)
    2.5 Upload your submission file (plain UTF-8 text format, one sentence per line).

    

### Manage Your Submission

#### Download or Delete a Submission
    1 Click on “My Submissions”.
    2 Click on the model associated with the submitted run 
       (e.g., KIT_IWSLT27_ModelCompression_en-de_constrained_primary).
    3 Click on the “MODEL COMPRESSION Hypotheses” button.
    4 Use the three-dot menu on the right to:
        - Download the submitted run (hypothesis).
        - Delete the submitted run and confirm.
        
#### Replace a Submission
    1 Delete your existing run.
    2 Submit a new run file (repeat STEP 2 of “Submission steps”).


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
