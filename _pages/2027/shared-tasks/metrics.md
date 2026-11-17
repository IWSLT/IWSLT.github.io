---
permalink: /2027/metrics
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
When deferring to automatically segmented speech, conventional text-to-text metrics become less reliable.
Despite this, current evaluation practices still rely heavily on these metrics, highlighting the need for more robust and realistic assessment approaches.

This shared task focuses on Quality Estimation for speech translation, a reference-free evaluation of speech translation quality.
Participants will assess the quality of translations produced in other IWSLT shared tasks, and system outputs will be evaluated based on their correlation with human judgments.

This year, the task has two tracks:

**Speech-to-Text Metrics:** quality estimation for speech-to-text translation. We consider two angles:
1. Speech sample + system translation (text) → score
2. ASR transcript + system translation (text) → score

**Speech-to-Speech Metrics (new in 2027):** quality estimation for speech-to-speech translation, where the system output is translated speech:
- Speech sample + system translation (speech) → score

To evaluate the submissions, we compute correlations with human judgments of quality.
We encourage participation in both tracks and in all scenarios, as well as exploring other approaches.
The translation segments occur in documents which can also provide additional context to the quality estimation.

We look forward to your submissions!

**Contents**
- [Data](#data): [Train + Dev Data](#train--dev-data), [Test Data](#test-data), [Example](#example)
- [Baselines](#baselines)
- [Evaluation](#evaluation)
- [Submission](#submission)
- [Important Dates](#important-dates)
- [Organizers](#organizers)
- [Contact](#contact)

<!-- Description the task, the languages, and the type of data -->

## Data

### Train + Dev Data

- **Speech-to-Text:** available on Hugging Face: [maikezu/iwslt2026-metrics-shared-train-dev](https://huggingface.co/datasets/maikezu/iwslt2026-metrics-shared-train-dev).
- **Speech-to-Speech:** TBD, will be added soon.

### Test Data

The test data will be released at the start of the [evaluation period](#important-dates).
{: .notice--info}

### Example

#### Speech-to-Text

As an example input, consider the following audio:

<audio controls>
    <source src="https://www.signalogic.com/melp/EngSamples/Orig/ENG_M.wav" type="audio/wav">
</audio>

and the corresponding testset entry:
```
{
    "audio": "sample.wav",
    "src_text": "Plans are well underway for races to Mars and the Moon in 1992, by solar sail. The race to Mars is to commemorate Columbus's journey to the New World 500 years ago, and the one to the Moon is to promote the use of solar sails in space exploration.",
    "tgt_text": "Pläne sind gut im Wege für Rennen nach Mars und der Mond in 1992, mit Sonnensegel. Das Rennen zum Mars ist zu Kolumbus' Reise in die Neue Welt vor 500 Jahren zu gedenken, und der eine zum Mond ist den Gebrauch von Sonnensegeln in Weltraum Exploration zu fördern.",
    "score": 71.5
}
```

The goal is to predict the human score `score` given the source speech `audio`, the ASR transcription `src_text`, and `tgt_text`.
The human score is not 100 because the style of the automatic translation is awkward at places.

#### Speech-to-Speech

An example for the speech-to-speech track will be added soon.

<!-- Details description of the data and links to download -->

## Baselines

### Speech-to-Text

<!-- TODO 2027: update baselines repo if a 2027 version is created -->
We consider the following quality estimation baselines, which are [available on GitHub](https://github.com/zouharvi/iwslt26-metrics):
- ASR-based [COMETKiwi-22](https://huggingface.co/Unbabel/wmt22-cometkiwi-da)
- ASR-based [COMET-partial](https://huggingface.co/zouharvi/COMET-partial)
- [SpeechQE](https://arxiv.org/pdf/2410.21485)
- [SpeechCOMET](https://aclanthology.org/2026.emnlp-main.596/)

### Speech-to-Speech

Baselines for the speech-to-speech track will be added soon.
{: .notice--info}

## Evaluation

Quality Estimation models will be evaluated by measuring their correlation with human judgments similar to [WMT Metrics Shared Task](https://www2.statmt.org/wmt25/pdf/2025.wmt-1.23.pdf).
For each language pair, we compute:
- [<b>Kendall's Tau<sub>b</sub></b>](https://aclanthology.org/2023.emnlp-main.798.pdf): segment-level measure, akin to Pearson correlation grouped by item. This measures the ability of metrics to select the best translation given a single source.
- [<b>Soft Pairwise Accuracy</b>](https://aclanthology.org/2024.wmt-1.118.pdf): system-level measure. This reveals how good the metric is at ranking the participating systems.

The scripts for meta-evaluation of metrics are available [publicly on GitHub](https://github.com/zouharvi/iwslt26-metrics).

## Submission

Submission format and instructions will be announced soon. See [Important Dates](#important-dates) for deadlines.
{: .notice--info}

<!-- Description of expected submission format and submission instructions -->


## Important Dates

The preliminary timeline is below and may be subject to minor changes.
{: .notice--info}

| Date            | Milestone                                    |
|-----------------|----------------------------------------------|
| Jan 1, 2027     | Release of shared task training and dev data |
| Apr 21, 2027    | Test set release (evaluation period)         |
| Apr 30, 2027    | System submission deadline                   |
| May 7, 2027     | System paper submission deadline             |
| Jun 7, 2027     | Notification of acceptance                   |
| Jun 21, 2027    | Camera ready deadline                        |
| Aug 17-18, 2027 | IWSLT conference                             |

**Note:** All deadlines are 11:59PM UTC-12:00.


## Organizers

<!-- List of organizers' names and affiliations -->

Listed in alphabetical order.

- Erica Cooper, NICT
- HyoJung Han, University of Maryland
- Wen-Chin Huang, Nagoya University
- Dominik Macháček, Charles University
- Matthias Sperber, Apple
- Vilém Zouhar, ETH Zurich, <vzouhar@ethz.ch> (chair)
- Maike Züfle, Karlsruhe Institute of Technology, <maike.zuefle@kit.edu> (chair)

## Contact

Chair(s): Maike Züfle <maike.zuefle@kit.edu>; Vilém Zouhar <vzouhar@ethz.ch>

Discussion: <iwslt-evaluation-campaign@googlegroups.com>
