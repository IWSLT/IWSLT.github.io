---
permalink: /2022/simultaneous
title: "Simultaneous Speech Translation"
---

## Description

<!-- the task, the languages, and the type of data -->

**Note: this is a draft and feedback on the task setup is welcome, either via iwslt-evaluation-campaign@googlegroups.com or Twitter (@iwslt)**

Simultaneous translation (also known as real-time or streaming translation) is the task of generating translations incrementally given partial input only.
Simultaneous translation enables interesting applications such as automatic simultaneous interpretation or international conference translations.
Simultaneous systems are typically evaluated with respect to quality and latency. This year, we will have 2 tracks and 4 language pairs:

* Text-to-Text: translating the output of a streaming ASR system in real-time from English to German, English to Japanese, English to Mandarin Chinese and English to Czech.
* Speech-to-Text: translating speech into text in real-time from English to German, English to Japanese, English to Mandarin Chinese and English to Czech.

We want to highlight the differences with respect to last edition:
* for the text-to-text track, we will use the output of a streaming ASR system as input instead of the gold transcript. As a result, both text-to-text and speech-to-text systems will be ranked together for a given language pair.
* we are adding Mandarin Chinese and Czech as a target languages.
* in order to reduce the number of conditions, English to Japanese and English to Chinese only use segmented input. English to German and English to Czech, on the other had, use only unsegmented input.

We encourage participants to enter all tracks when possible. We also encourage participants to contrast cascaded and end-to-end solutions for the Speech-to-Text track.

## Evaluation

This year, we will use automatic evaluation very similar to the last year and we will trial manual evaluation for English-to-Czech track.

### Automatic Evalution

We will use a very similar system as last year for evaluation. The system's performance will be evaluated in two ways:

* Translation quality: we will use multiple standard metrics: BLEU, TER, and METEOR.
* Translation latency: we will use standard metrics for simultaneous machine translation including average proportion (AP), average lagging (AL) and differentiable average lagging (DAL).

Like last year, the evaluation implementation will use the [SimulEval](https://github.com/facebookresearch/SimulEval) toolkit. For latency measurement, we will contrast computation aware and non computation aware latency metrics. See the [SimulEval description](https://arxiv.org/abs/2007.16193) for how those metrics are defined. Note that the definition of average lagging has been modified from the [original definition](https://www.aclweb.org/anthology/P19-1289/) (see section 3.2 in the [SimulEval description](https://arxiv.org/abs/2007.16193)). The latency is calculated on word level for En-De systems and character level for En-Ja systems and En-Zh systems.

The participants will submit a Docker image (see below for an example) and the organizers will run the image in a controlled environment, specifically an **ap3.2xlarge AWS instance** (see details in https://aws.amazon.com/ec2/instance-types/p3/).

#### Ranking for Automatic Evaluation

We will evaluate translation quality with detokenized BLEU and latency with AP, AL and DAL. The systems will be ranked by the translation quality with different latency regimes. Three regimes, low, medium and high, will be evaluated. Each regime is determined by a maximum latency threshold. The thresholds are determined by AL, which represents the delay to the perfect real time system (milliseconds for speech and number of words for text), but all three latency metrics, AL, DAL and AP will be reported. Based on analysis on the quality-latency tradeoffs for the baseline systems, the thresholds are set as follows:

Speech Translation (English-German):

* Low Latency: AL < = 1000
* Medium Latency: AL < = 2000
* High Latency: AL < = 4000

Speech Translation (English-Mandarin):

* Low Latency: AL < = TBD
* Medium Latency: AL < = TBD
* High Latency: AL < = TBD

Text Translation (English-German):

* Low Latency: AL < = 3
* Medium Latency: AL < = 6
* High Latency: AL < = 15

Text Translation (English-Japanese):

* Low Latency: AL < = 8
* Medium Latency: AL < = 12
* High Latency: AL < = 16

Text Translation (English-Mandarin):

* Low Latency: AL < = TBD
* Medium Latency: AL < = TBD
* High Latency: AL < = TBD

The submitted systems will be categorized into different regimes based on the AL calculated on the Must-C English-German and English-Mandarin test sets (`tst-COMMON`) for English-German and English-Mandarin or on the IWSLT21 dev set for English-Japanese, while the translation quality will be calculated on the blind test set. We require participants to submit at least one system for each latency regime. Participants are encouraged to submit multiple systems for each regime in order to provide more data points for latency-quality tradeoff analyses. If multiple systems are submitted, we will keep the one with the best translation quality for ranking. In addition, within each latency regime, we will also measure computation aware AL and rank systems accordingly. Finally, we will report latency-quality trade-off curves for non computation aware AL and for computation aware AL in the findings paper.

**Note that for English-German, we will use the release v2.0 of MuST-C and for English-Mandarin, we will use the release v1.2 of MuST-C**

### Manual Evaluation

English-to-Czech track will include manual evaluation of simultaneous speech translation for at least one variant of submitted system for each participating team (based on the selection by the team).

The evaluation will consist in playing the source sound/video with live text captions to speakers fluent in the source English and native in the target Czech, and collecting "continuous ranking". This method is described in Section 3.1.1 (page 22) in the [master thesis by Dávid Javorský](https://dspace.cuni.cz/bitstream/handle/20.500.11956/147964/120397331.pdf?sequence=1&isAllowed=y).

As a benchmark, human interpretations presented in the form of live text captions, will be scored in the same setting.

## Training and Development Data

### Text-to-Text and Speech-to-Text Tracks (English to German)

You may use the same training and development data available for the [Offline Speech Translation task](https://iwslt.org/2022/offline). Specifically, please refer to the [Allowed Training Data](https://iwslt.org/2022/offline#allowed-training-data) and the [Past Editions Development Data](https://iwslt.org/2022/offline#past-editions-development-data) sections.

For English-Mandarin, data is TBD.

### Text-to-Text Track (English to Japanese)

For training, you may use the parallel data and monolingual data available for the [English-Japanese WMT20 news task](http://statmt.org/wmt20/translation-task.html).
For development, you may use the [IWSLT 2017 development sets](https://wit3.fbk.eu/2017-01-c) and [IWSLT 2021 development set](https://drive.google.com/drive/folders/1uSkOT-XqbICMohnvfXdEFffKLdaQX0X7).

#### English-to-Japanese simultaneous interpretation transcripts
You may also use [simultaneous interpretation transcripts for the IWSLT 2021 development set](https://drive.google.com/drive/folders/1bB1s9PKNoRoDFfc567J5zDMcYj_lFFEB) for the comparison with human interpretation, under the terms of use written in *README_before_download_enjaDevSI.txt*.


## Baseline Implementation and Example

### English-to-German Speech-to-Text Translation
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

If you encounter a bus error similar to this [issue](https://github.com/pytorch/pytorch/issues/2244), you can try adding `--shm-size 8G` to the `docker run` command.

When submitting your system, please make sure it works for the MuST-C dev and test sets. During the official evaluation, we will run the submitted system with the blind set.

### English-to-Japanese Text-to-Text Translation
You can find instructions to train and evaluate an English-to-Japanese baseline system [here](https://github.com/pytorch/fairseq/blob/master/examples/simultaneous_translation/docs/enja-waitk.md).

## System Submission

Participants are required to run the evaluation on the English-German dev and tst-COMMON MuST-C sets for the English-German and English-Chinese tracks and on the IWSLT21 dev set (TODO: missing speech) for the English-Japanese track and report the results as part of the submission. This is to make sure that the submitted systems work so that organizers can run them as well. The submission files should be packed into a `zip` or `tar.gz` file and uploaded to Dropbox[dropbox] prior to the deadline (TBD anywhere on earth). The submission files should include instructions on how to run the system in a `README` or `README.md` file as well as all the necessary files (Docker image, checkpoints, vocabulary, etc.) for the organizers to be able to run the system.

## Contacts

Discussion: iwslt-evaluation-campaign@googlegroups.com

## Organizers

<!-- list of names and affiliations -->

* Katsuhito Sudoh (NAIST)
* Satoshi Nakamura (NAIST)
* Ondřej Bojar (Charles University)
* Jiatong Shi (CMU)
* Shinji Watanabe (CMU)
* Xutai Ma (Johns Hopkins University, Meta)
* Maha Elbayad (Meta)
* Changhan Wang (Meta)
* Hongyu Gong (Meta)
* Juan Pino (Meta)

<!-- Markdown notes: comments can be formed as above; bulleted lines start with a - ; if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line -->
