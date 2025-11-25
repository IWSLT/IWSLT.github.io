---
permalink: /2026/metrics
title: "Speech Translation Metrics track"
toc: true
toc_sticky: true
---

<!--
Markdown notes: comments can be formed as in this example;
bulleted lines start with a - ;
if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line
-->

## Description

Speech translation has been a core focus of IWSLT for years, yet its evaluation remains underexplored. Most existing evaluations assume gold segmentation, an unrealistic scenario for real-world systems. When working with automatically segmented speech, conventional text-to-text metrics become less reliable. Despite this, current evaluation practices still rely heavily on these metrics, highlighting the need for more robust and realistic assessment approaches.

This shared task addresses this gap by focusing on Quality Estimation (QE) for speech translation, a reference-free evaluation of speech translation quality. Participants will assess the quality of translations produced in other IWSLT shared tasks, and system outputs will be evaluated based on their correlation with human judgments.

We suggest two angles for QE for speech translation (but we also welcome submissions that explore other angles):
1. Speech sample + system translation → QE score
2. ASR transcript + system translation → QE score 

For performance evaluation, correlation rankings will be computed separately for direct systems (approach 1) and cascaded systems (approach 2), to encourage participation in both scenarios.

Participants are also encouraged to take the context of segments into account, which will be provided. 

We look forward to your submissions!


<!-- Description the task, the languages, and the type of data -->


## Data

Train and development data together with evaluation scripts will be released on January 1.

<!-- Details description of the data and links to download -->


## Baselines
Baselines will be released soon.

<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->


## Submission
More details on the submission process and timeline will be released soon.

Please note that we do not accept system submissions without a system paper. 


<!-- Description of expected submission format and submission instructions -->


## Evaluation
Quality Estimation models will be evaluated by measuring their correlation with human judgments.

More details will be released soon.

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->


## Organizers

<!-- List of organizers' names and affiliations -->

- Maike Züfle, Karlsruhe Institute of Technology, <maike.zuefle@kit.edu>
- Vilém Zouhar, ETH Zurich, <vzouhar@ethz.ch>
- Brian Thompson
- Dominik Macháček, Charles University
- Mattias Sperber, Apple
- Marine Carpuat, University of Maryland
- HyoJung Han, University of Maryland

## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair(s): Maike Züfle <maike.zuefle@kit.edu>; Vilém Zouhar <vzouhar@ethz.ch>

Discussion: <iwslt-evaluation-campaign@googlegroups.com>
