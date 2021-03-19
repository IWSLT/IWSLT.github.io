---
permalink: /2021/simultaneous
title: "Simultaneous Speech Translation"
---

## Description

<!-- the task, the languages, and the type of data -->

This task focuses on the real time (also known as simultaneous or streaming) aspect of speech and machine translation as it enables interesting applications such as simultaneous interpretation or international conference live translations. Real-time systems are typically evaluated with respect to quality and latency. This year, we will have 3 tracks:

* Text-to-Text: translating ground-truth transcripts in real-time from English to German, English to Japanese.
* Speech-to-Text: directly translating speech into text in real-time from English to German.

We encourage participants to enter all tracks when possible. We also encourage participants to contrast cascaded and end-to-end solutions for the Speech-to-Text track.

## Evaluation

We will use a very similar system as last year for evaluation. The system's performance will be evaluated in two ways:

* Translation quality: we will use multiple standard metrics: BLEU, TER, and METEOR.
* Translation latency: we will make use of the recently developed metrics for simultaneous machine translation including average proportion (AP), average lagging (AL) and differentiable average lagging (DAL).

This year, the evaluation implementation will use the [SimulEval](https://github.com/facebookresearch/SimulEval) toolkit. For latency measurement, we will contrast computation aware and non computation aware latency metrics. See the [SimulEval description](https://arxiv.org/abs/2007.16193) for how those metrics are defined. Note that the definition of average lagging has been modified from the [original definition](https://www.aclweb.org/anthology/P19-1289/) (see section 3.2 in the [SimulEval description](https://arxiv.org/abs/2007.16193)).

### Ranking

Note: this section is under development and subject to changes.

We will evaluate translation quality with detokenized BLEU and latency with AP, AL and DAL. The systems will be ranked by the translation quality with different latency regimes. Three regimes, low, medium and high, will be evaluated. Each regime is determined by a maximum latency threshold. The thresholds are determined by AL, which represents the delay to the perfect real time system (milliseconds for speech and number of words for text), but all three latency metrics, AL, DAL and AP will be reported. Based on analysis on the quality-latency tradeoffs for the baseline systems, the thresholds are set as follows:

Speech Translation:

* Low latency: AL < = 1000
* Medium latency: AL < = 2000
* High Latency: AL < = 4000

Text Translation

* Low latency: AL < = 3
* Medium Latency: AL < = 6
* High Latency: AL < = 15

The submitted systems will be categorized into different regimes based on the AL calculated on the Must-C English-German test set (`tst-COMMON`), while the translation quality will be calculated on the blind test set. We require participants to submit at least one system for each latency regime. Participants are encouraged to submit multiple systems for each regime in order to provide more data points for latency-quality tradeoff analyses. If multiple systems are submitted, we will keep the one with the best translation quality for ranking. In addition, within each latency regime, we will also measure computation aware AL and rank systems accordingly. Finally, we will report latency-quality trade-off curves for non computation aware AL and for computation aware AL in the findings paper.

## Training and Development Data

### Text-to-Text and Speech-to-Text Tracks (English to German)

You may use the same training and development data available for the [Offline Speech Translation task](https://iwslt.org/2021/offline). Specifically, please refer to the [Allowed Training Data](https://iwslt.org/2021/offline#allowed-training-data) and the [Past Editions Development Data](https://iwslt.org/2021/offline#past-editions-development-data) sections.

### Text-to-Text Track (English to Japanese)

For training, you may use the parallel data and monolingual data available for the [English-Japanese WMT20 news task](http://statmt.org/wmt20/translation-task.html).
For development, you may use the [IWSLT 2017 development sets](https://wit3.fbk.eu/2017-01-c) and [IWSLT 2021 development set](https://drive.google.com/drive/folders/1uSkOT-XqbICMohnvfXdEFffKLdaQX0X7).

#### English-to-Japanese simultaneous interpretation transcripts
You may also use [simultaneous interpretation transcripts for the IWSLT 2021 development set](https://drive.google.com/drive/folders/1bB1s9PKNoRoDFfc567J5zDMcYj_lFFEB) for the comparison with human interpretation, under the terms of use written in *README_before_download_enjaDevSI.txt*.


## Baseline Implementation and Example

You can find a baseline and instructions on how to reproduce it [here](https://github.com/pytorch/fairseq/blob/master/examples/speech_to_text/docs/simulst_mustc_example.md).
Our final evaluation will be run inside Docker. To run an evaluation with Docker, first build a Docker image from the Dockerfile. Here is an example Dockerfile for the baseline:

```
FROM ubuntu:20.04

MAINTAINER Juan Pino (juancarabina@fb.com)

RUN apt-get update && apt-get install -y build-essential git python3 python3-pip libsndfile1
RUN git clone https://github.com/pytorch/fairseq.git /fairseq
RUN pip3 install torch torchaudio vizseq soundfile sentencepiece sacrebleu=="1.5.1"
WORKDIR /fairseq
RUN pip3 install -e .
RUN git clone https://github.com/facebookresearch/SimulEval.git /SimulEval
WORKDIR /SimulEval
RUN pip3 install -e .
RUN ln -s /usr/bin/python3 /usr/bin/python

ENTRYPOINT simuleval \
    --agent $AGENT \
    --source $SRC_FILE \
    --target $TGT_FILE \
    --output $OUTPUT \
    --scores $EXTRA_AGENT_ARGS
```

Assuming your current directory contains the Dockerfile above, you can run the following commands to run the baseline evaluation inside Docker:

```
FAIRSEQ=<PATH TO fairseq>
AGENT=fairseq/examples/speech_to_text/simultaneous_translation/agents/fairseq_simul_st_agent.py
WORKDIR=<WORKING DIRECTORY> # `input` contains source/target files and wav files, `models` contains databin and the checkpoint
SRC_FILE=input/dev.wav_list
TGT_FILE=input/dev.de
DATA=models/databin
CONFIG_YAML=config_st.yaml
MODEL=models/convtransformer_wait5_pre7
EXTRA_AGENT_ARGS="--data-bin $DATA --config $CONFIG_YAML --model-path $MODEL"
OUTPUT=output

docker build -t iwslt2021_simulst_baseline:latest .
docker run -e AGENT="$AGENT" -e SRC_FILE="$SRC_FILE" -e TGT_FILE="$TGT_FILE" -e EXTRA_AGENT_ARGS="$EXTRA_AGENT_ARGS" -e OUTPUT="$OUTPUT" -v $FAIRSEQ:/SimulEval/fairseq -v $WORKDIR/input:/SimulEval/input -v $WORKDIR/models:/SimulEval/models -it iwslt2021_simulst_baseline
```

When submitting your system, please make sure it works for the MuST-C dev and test sets. During the official evaluation, we will run the submitted system with the blind set.

## System Submission

Participants are required to run the evaluation on the English-German dev and tst-COMMON MuST-C sets and report the results as part of the submission. This is to make sure that the submitted systems work so that organizers can run them as well.

## Contacts

Discussion: iwslt-evaluation-campaign@googlegroups.com

## Organizers

<!-- list of names and affiliations -->

* Katsuhito Sudoh (NAIST)
* Satoshi Nakamura (NAIST)
* Ondřej Bojar (Charles University)
* Xutai Ma (Johns Hopkins University, Facebook)
* Maha Elbayad (Facebook)
* Changhan Wang (Facebook)
* Juan Pino (Facebook)

<!-- Markdown notes: comments can be formed as above; bulleted lines start with a - ; if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line -->
