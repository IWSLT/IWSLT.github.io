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

Speech translation has been a core focus of IWSLT for years, yet its evaluation remains underexplored.
Most existing evaluations assume gold segmentation, an unrealistic scenario for real-world systems.
When defering to automatically segmented speech, conventional text-to-text metrics become less reliable.
Despite this, current evaluation practices still rely heavily on these metrics, highlighting the need for more robust and realistic assessment approaches.

This shared task focuses on Quality Estimation for speech translation, a reference-free evaluation of speech translation quality.
Participants will assess the quality of translations produced in other IWSLT shared tasks, and system outputs will be evaluated based on their correlation with human judgments.

We consider two angles for speech translation quality estimation:
1. Speech sample + system translation → score
2. ASR transcript + system translation → score 

To evaluate the submissions, we compute correlations with human judgmnets of quality.
We encourage participation in both scenarios or exploring other approaches.
The translation segments occur in documents which can also provide additional context to the quality estimation.

We look forward to your submissions!

<!-- Description the task, the languages, and the type of data -->

## Data

As an example input, consider the following audio:

<audio controls>
    <source src="https://www.signalogic.com/melp/EngSamples/Orig/ENG_M.wav" type="audio/wav">
</audio>

and the corresponding testset entry:
```
{
    "src_wav": "sample.wav"
    "src_asr": "Plans are well underway for races to Mars and the Moon in 1992, by solar sail. The race to Mars is to commemorate Columbus's journey to the New World 500 years ago, and the one to the Moon is to promote the use of solar sails in space exploration.",
    "tgt": "Pläne sind gut im Wege für Rennen nach Mars und der Mond in 1992, mit Sonnensegel. Das Rennen zum Mars ist zu Kolumbus' Reise in die Neue Welt vor 500 Jahren zu gedenken, und der eine zum Mond ist den Gebrauch von Sonnensegeln in Weltraum Exploration zu fördern.",
    "score_human": 71.5,
}
```

The goal is to predict `score_human` given `src_wav`, `src_asr`, and `tgt`.
The human score is not 100 because the style of the automatic translation is awkward at places.

Train and development data will be released on January 1.

<!-- Details description of the data and links to download -->

## Baselines

We consider the following quality estimation baselines:
- ASR-based [COMETKiwi-22](https://huggingface.co/Unbabel/wmt22-cometkiwi-da)
- ASR-based [COMET-partial](https://huggingface.co/zouharvi/COMET-partial)
- [SpeechQE](https://arxiv.org/pdf/2410.21485)
- More baseline to be announced

<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->


## Submission
More details on the submission process and timeline will be released soon.

As part of the submission, we require a system description paper to be submitted to IWLST to be reviewed.

<!-- Description of expected submission format and submission instructions -->


## Evaluation

Quality Estimation models will be evaluated by measuring their correlation with human judgments similar to [WMT Metrics Shared Task](https://www2.statmt.org/wmt25/pdf/2025.wmt-1.23.pdf).
For each language pair, we compute:
- [<b>Kendall's Tau<sub>b</sub></b>](https://aclanthology.org/2023.emnlp-main.798.pdf): segment-level measure, akin to Pearson correlation groupped by item. This measures the ability of metrics to select the best translation given a single source.
- [<b>Soft Pairwise Accuracy</b>](https://aclanthology.org/2024.wmt-1.118.pdf): system-level measure. This reveals how good the metric is at ranking the participating systems.

We will provide evaluations scripts to verify dev data performance on January 1.

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

## Important Dates
The preliminary timeline is below and may be subject to minor changes.
{: .notice--info}

|---------------------|----------------------------------------------|
| Jan 1, 2026         | Release of shared task training and dev data |
| Apr 10-22, 2026     | Evaluation period (only for Metrics Task)    |
| Apr 24, 2026        | System paper submission deadline             |
| May 15, 2026        | Notification of acceptance                   |
| June 1, 2026        | Camera ready deadline (all papers)           |
| July 3-4, 2026      | IWSLT conference                             |


## Organizers

<!-- List of organizers' names and affiliations -->

- Maike Züfle, Karlsruhe Institute of Technology, <maike.zuefle@kit.edu>
- Vilém Zouhar, ETH Zurich, <vzouhar@ethz.ch>
- Brian Thompson
- Dominik Macháček, Charles University
- Mattias Sperber, Apple
- Marine Carpuat, University of Maryland
- HyoJung Han, University of Maryland
- Marco Turchi, Zoom
- Matteo Negri, FBK

## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair(s): Maike Züfle <maike.zuefle@kit.edu>; Vilém Zouhar <vzouhar@ethz.ch>

Discussion: <iwslt-evaluation-campaign@googlegroups.com>
