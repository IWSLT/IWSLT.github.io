---
permalink: /2023/simultaneous
title: "simultaneous track"
toc: true
toc_sticky: true
---

<!--
Markdown notes: comments can be formed as in this example;
bulleted lines start with a - ;
if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line
-->

## Description

Simultaneous translation (also known as real-time or streaming translation) is the task of generating translations incrementally given partial input only.
Simultaneous translation enables interesting applications such as automatic simultaneous interpretation or international conference translations.
Simultaneous systems are typically evaluated with respect to quality and latency.

This year, there will be 2 tracks:

- Speech-to-Text: simultaneously translating speech in source language into text in target language.
- Speech-to-Speech: simultaneously translating speech in source language into speech in target language.

and three language directions:

- English -> German
- English -> Chinese
- English -> Japanese

We want to highlight the differences with respect to last edition:

- We add the new speech-to-speech track.
- Single latency constraint for simplified submission.
- New [SimulEval](https://simuleval.readthedocs.io/en/latest/) toolkit for evaluation.

<!-- Description the task, the languages, and the type of data -->

## Data

We will adapt the unconstrained data condition, including all the available data, pre-training models, and proprietary data

## Evaluation

The evaluation implementation will use the latest [SimulEval](https://github.com/facebookresearch/SimulEval) toolkit.
We will use the new [remote evaluation](https://simuleval.readthedocs.io/en/latest/tutorials/remote_evaluation.html) mode.

### Metrics

The system's performance will be evaluated in two ways:

- Translation quality metrics:
  - BLEU
  - BLASER
- Translation latency:
  - Average Lagging
  - Length Adaptive Average Lagging
  - Average Token Delay
  - Average Proportion
  - Differentiable Average Lagging

For latency measurement, we will contrast computation aware and non computation aware latency metrics.
See the [SimulEval description](https://arxiv.org/abs/2007.16193) for how those metrics are defined.
Note that the definition of average lagging has been modified from the [original definition](https://www.aclweb.org/anthology/P19-1289/) (see section 3.2 in the [SimulEval description](https://arxiv.org/abs/2007.16193)).

For speech-to-speech translation, we will run the latency metrics on aligned transcripts.

We will run the systems on the segmented blind test set.
The latency is calculated on detokenized word level for En-De systems and character level for En-Zh and En-Ja systems.

### Ranking

The systems will be ranked by the translation quality within a latency constraint.
The latency constraint is determined by the latency on MuST-C v2.0 tst-COMMON set.
The constraint is determined by the average lagging,
but all other latency metrics will be reported.
Based on analysis on the quality-latency tradeoffs for the baseline systems,
for all three languages, the thresholds are set as follows:

- Speech-to-Text Translation: 2 seconds
- Speech-to-Speech Translation: TBD

## Baselines

We provide a test-time [Wait-K](https://aclanthology.org/P19-1289/) speech-to-text baseline as follows:

| Language Direction | Latency (seconds) | Quality (BLEU) | Offline Quality (BLEU) |
| ------------------ | ----------------- | -------------- | ---------------------- |
| En -> De           | 1.98              | 14.3           | 23.2                   |
| En -> Zh           | 1.77              | 14.2           | 18.7                   |
| En -> Ja           | 1.82              | 6.63           | 11.2                   |

The instruction to reproduce the baseline results can be found [here](https://github.com/facebookresearch/fairseq/tree/iwslt2023/examples/simultaneous_translation).

## Submission

### Format

Participants can have multiple submissions,
but can only have one submission for one track (`s2t`/`s2s`), one language (`de`/`zh`/`ja`).

One submission should contain the following items:

- **A built docker image file**, named `image.tar`.
- The output logs of the system on **MuST-C v2.0 tst-COMMON** sets, named `results`.
- A **readme** file containing information needed to run the system, named `readme`.

The submission should be compressed as a `tar.gz` file,
and uploaded to the google drive (will update soon).
The name of file should be

```
{team_name}_{target_modality}_{target_language}.tar.gz
```

For instance, if one submission is named `meta_text_de.tar.gz`, and `tar -xf meta_text_de.tar.gz` should have the following output

```
tar -xf meta_text_de_low.tar.gz -C meta_text_de_low
> ls meta_text_de_low
image.tar results readme
```

### Docker Image

The docker image should already be built and able to run in a controlled environment, specifically an AWS [ap3.2xlarge](https://aws.amazon.com/ec2/instance-types/p3/) instance. Please make sure that the **docker image alone** is enough to run the system. All dependencies, such as checkpoints and dictionaries should be included inside the image.

The follow command should be able to reproduce the same output as `results` in the submission:

```bash
# Load the image
docker load -i my_docker_image.tgz

# Start the service. Exposing the 2023 for evaluation
docker run -p 2023:2023 --gpus all --shm-size 32G my_docker_image:latest

# Evaluation
simuleval --remote-eval --remote-port 2023 --source source.txt --target target.txt
```

The docker will start the service of the system, and `simuleval --remote-eval` will serve as a front-end for evaluation.

### MuST-C v2.0 tst-COMMON

The participants are required to submit the output of the system (the `--output` from `simuleval`) on MuST-C v2.0 tst-COMMON.
The segmented data can be downloaded [here](https://dl.fbaipublicfiles.com/simultaneous_translation/iwslt2023/must-c_v2.0_tst-COMMON.tgz)
The latency constraint will be check on the MuST-C v2.0 tst-COMMON set.

### Readme

A `readme` file should contains the following information

- Instruction to run the system on each track and language direction.
- Results on MuST-C v2.0 tst-COMMON of the default system.
- Any other information needed to run the system

### Example

An example of training, evaluating and submission preparation with the baseline systems can be found [here](https://github.com/facebookresearch/fairseq/tree/iwslt2023/examples/simultaneous_translation)

## Organizers

- Katsuhito Sudoh (NAIST)
- Satoshi Nakamura (NAIST)
- Yasumasa Kano (NAIST)
- Ondřej Bojar (Charles University)
- Peter Polak (Charles University)
- Shinji Watababe (CMU)
- Jiatong Shi (CMU)
- Yun Tang (Meta)
- Hirofumi Inaguma (Meta)
- Kevin Tran (Meta)
- Pengwei (Meta)
- Mingda Chen (Meta)
- Xutai Ma (Meta)
- Juan Pino (Meta)

## Contact

Chairs:

- Xutai Ma (Meta, USA)
- Juan Pino (Meta, USA)
- Katsuhito Sudoh (NAIST, Japan)

Discussion: <iwslt-evaluation-campaign@googlegroups.com>
