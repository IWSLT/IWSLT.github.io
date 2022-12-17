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

This year, we will have 2 tracks:

* Speech-to-Text translation: simultaneously translating speech in source language into text in target language.
* Speech-to-Speech translation: simultaneously translating speech in source language into speech in target language.


There will be three language directions:

* English -> German
* English -> Chinese
* English -> Japanese


We want to highlight the differences with respect to last edition:
* We add the new speech-to-speech track.
* Remove the high latency setting and on low latency scenarios.
* New [SimulEval](https://simuleval.readthedocs.io/en/latest/) toolkit for evaluation.


<!-- Description the task, the languages, and the type of data -->


## Data
You may use the same training and development data available for the [Offline Speech Translation task](https://iwslt.org/2023/offline). Specifically, please refer to the [Allowed Training Data](https://iwslt.org/2023/offline#allowed-training-data) and the [Past Editions Development Data](https://iwslt.org/2023/offline#past-editions-development-data) sections.


## Evaluation

The evaluation implementation will use the latest [SimulEval](https://github.com/facebookresearch/SimulEval) toolkit.
We will use the new [remote evaluation](https://simuleval.readthedocs.io/en/latest/tutorials/remote_evaluation.html) mode.

### Metrics

The system's performance will be evaluated in two ways:
* Translation quality metrics:
    * BLEU
    * BLASER
* Translation latency:
    * Average Lagging
    * Average Token Delay
    * Average Proportion
    * Differentiable Average Lagging

For latency measurement, we will contrast computation aware and non computation aware latency metrics. See the [SimulEval description](https://arxiv.org/abs/2007.16193) for how those metrics are defined. Note that the definition of average lagging has been modified from the [original definition](https://www.aclweb.org/anthology/P19-1289/) (see section 3.2 in the [SimulEval description](https://arxiv.org/abs/2007.16193)).

For speech-to-speech translation, we will run the latency metrics on aligned transcripts. We will run the systems on the segmented blind test set.
The latency is calculated on word level for En-De systems and character level for En-Zh and En-Ja systems.

### Ranking

The systems will be ranked by the translation quality with different latency regimes.
Two regimes, low, medium, will be evaluated.
Each regime is determined by a maximum latency threshold on MuST-C v2.0 tst-COMMON set.
The thresholds are determined by average lagging,
which represents the delay to the perfect real time system,
but all other latency metrics will be reported.
Based on analysis on the quality-latency tradeoffs for the baseline systems,
the thresholds are set as follows:

* Speech-to-Text Translation:
    * Low latency: AL < = TBD
    * Medium latency: AL < = TBD
* Speech-to-Speech Translation:
    * Low latency: AL < = TBD
    * Medium latency: AL < = TBD


## Baselines

We will provide speech-to-text and speech-to-speech baselines on all directions. More details coming soon




## Submission
Participants are required submit the following items:
* **Built docker images** or **docker hub links**.
* The output of the system on **MuST-C v2.0 tst-COMMON** sets.
* **A readme file** contains information needed to run the system.

One submission is for one track, one language and one latency_regime.
The submission should be compressed as a `tar.gz` file,
and uploaded to the google drive (will update soon).
The name of file should be
* `{team_name}_{target_modality}_{target_language}_{latency_regime}.tar.gz`

For instance, the file name is `meta_text_de_low.tar.gz`,
and `tar -xf` should have the following output
```bash
> tar -xf meta_text_de_low.tar.gz -C meta_text_de_low
> ls meta_text_de_low
meta_text_de_low_docker_image.tgz
meta_text_de_low_must_c_tst-COMMON_results
readme
```


### Docker Image
The docker image should already be built and able to run in a controlled environment, specifically an AWS [ap3.2xlarge](https://aws.amazon.com/ec2/instance-types/p3/) instance.

For instance, if submitted docker image is named `my_docker_image.tgz` or the docker hub link is `hub.docker.com/my_username/my_docker_image`,
the system should be able to run as follow.

```bash
# Load the image
docker load -i my_docker_image.tgz

# Or a from docker hub
docker pull hub.docker.com/user/my_docker_image

# Start the service. exposing the 2023 for evaluation
docker run -p 2023:2023 my_docker_image:latest

# Evaluation
simuleval --remote-eval --remote-port 2023 --source source.txt --target target.txt
```
The docker will start the service of the system, and `simuleval --remote-eval` will serve as a front-end for evaluation.

Please following the requirements
* **One docker image for one track, one language direction and one latency regime**.
The default system should be `docker run -p 2023:2023 my_docker_image:latest`,
without any other arguments, except `--device` to pass the device information (e.g. GPU index).
* **No dependencies on external files**. Please make sure that the docker image alone is enough to run the system. All necessary files, such as checkpoints and dictionaries should be included inside the image.
* Optionally, you may (and are encourage to) submit multiple versions by passing `-e` options to `docker run`, as long as they fulfill the latency thresholds.
We will choose the best version for ranking.
If so, please give us the instructions in the `readme` file.
However, given the evaluation will be done in a short period of time,
we do not guarantee that we will finish all the other versions than default.
We will report the default version if we are not able to finish all.

We will provide an example on how to submit a system based the baseline model.
Details coming soon!

### MuST-C v2.0 tst-COMMON
The participants are required to submit the output of the system (the `--output` from `simuleval`) for each version of system submitted.
The latency regime of systems will be categorized based on the output.
The organizers may also run the systems on tst-COMMON for sanity check.

### Readme
A readme file should contains the following information
* Instruction to run the default system on each track, latency regime and language direction.
* Results on MuST-C v2.0 tst-COMMON of the default system.
* [Optional] Instructions to run other versions of a system.
* [Optional] Results on MuST-C v2.0 tst-COMMON of other versions of the system.

We will provide an example readme based the baseline model.
Details coming soon!


## Organizers

* Katsuhito Sudoh (NAIST)
* Satoshi Nakamura (NAIST)
* Yasumasa Kano (NAIST)
* Ondřej Bojar (Charles University)
* Peter Polak (Charles University)
* Shinji Watababe (CMU)
* Jiatong Shi (CMU)
* Yun Tang (Meta)
* Hirofumi Inaguma (Meta)
* Kevin Tran (Meta)
* Pengwei (Meta)
* Mingda Chen (Meta)
* Xutai Ma (Meta)
* Juan Pino (Meta)

## Contact
Chairs:
* Xutai Ma (Meta, USA)
* Juan Pino (Meta, USA)
* Katsuhito Sudoh (NAIST, Japan)

Discussion: <iwslt-evaluation-campaign@googlegroups.com>
