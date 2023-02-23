---
permalink: /2023/multilingual
title: "Multilingual track: ACL 60-60 initiative"
toc: true
toc_sticky: true
---

<!--
Markdown notes: comments can be formed as in this example;
bulleted lines start with a - ;
if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line
-->


## Description

At ACL 2022, an ambitious [60-60 D&I Initiative](https://www.2022.aclweb.org/dispecialinitiative){:target="_blank"} was announced, targeting text and speech translation of the ACL Anthology and past recorded talks into 60 languages for the ACL's 60th anniversary. 
Results of this ongoing effort will be shared with the community at ACL 2023 where IWSLT 2023 will be co-located. 
This track is a multilingual speech translation shared task evaluated on a subset of this data to involve the IWSLT community and larger community in this effort and spur conversations about related methodology and progress.


## Data 

This task is about speech translation by and for our field. Specifically, this track targets translation of oral presentations from past ACL events into a several languages. Talks cover a variety of technical content by speakers from around the world.

* Evaluation data (development and test sets) consists of oral presentations from past ACL talks from the Anthology, with human post-edited transcripts and translations.
<!-- * To adapt to the task domain, terminology lists and abstract (text) translations created for the 60-60 initiative are provided. No in-domain speech translation training data is provided. -->
* Training data includes publicly available corpora and pretrained models.
  * The source language and a subset of the target languages are shared with other talk translation tracks
  * Allowed training data is a superset of the data for all talk translation tracks - we include the same pretrained models and training corpora, with additional target languages
  * We encourage joint submissions across tracks to enable additional analysis and conference discussion!

### Training data

Two training conditions are proposed. First is a constrained setting in which the allowed training data is limited to a medium-sized framework in order to keep the training time and resource requirements manageable. 
In order to allow participants to leverage existing multilingual models with medium-sized resources, particularly for this task where not all language pairs share similar amounts of public datasets, we propose a "**constrained with large language models**" condition, where a specific set of pretrained models is allowed to extend capabilities.
We also encourage the participation of teams equipped with high computational power and additional resources to maximize performance on the task, and so an "**unconstrained**" setting without data restrictions is also proposed.

* **Constrained with pretrained models**: Under this condition, all the constrained resources plus a restricted selection of pretrained models are allowed. The following pretrained models are considered part of the training data and freely usable to build submission systems:  
  <details>
    <summary style="padding-top: 10px;"><em>Constrained training data (click to expand)</em></summary>
   <table><thead><tr><th>Data type</th><th>src lang</th><th>tgt lang</th><th>Training corpus (URL)</th><th>Version</th><th>Comment</th></tr></thead><tbody><tr><td>speech</td><td>en</td><td>--</td><td><a href="http://www.openslr.org/12/">LibriSpeech</a></td><td>v12</td><td></td></tr><tr><td>speech</td><td>en</td><td>--</td><td><a href="https://github.com/srvk/how2-dataset">How2</a></td><td></td><td></td></tr><tr><td>speech</td><td>en</td><td>--</td><td><a href="https://commonvoice.mozilla.org/en/datasets">Mozilla Common Voice</a></td><td>v11.0</td><td></td></tr><tr><td>speech</td><td>en</td><td>--</td><td><a href="https://lium.univ-lemans.fr/en/ted-lium3/">TED LIUM</a></td><td>V2/V3</td><td></td></tr><tr><td>speech</td><td>en</td><td>--</td><td><a href="https://github.com/facebookresearch/voxpopuli">Vox Populi</a></td><td></td><td></td></tr><tr><td>speech-to-text-parallel</td><td>en</td><td>all</td><td><a href="https://ict.fbk.eu/must-c/">MuST-C</a></td><td>v1.2/v2.0/v3.0</td><td>(10) ar, zh, nl, fr, de, ja, fa, pt, ru, tr</td></tr><tr><td>speech-to-text-parallel</td><td>en</td><td>all</td><td><a href="https://github.com/facebookresearch/covost">CoVoST</a></td><td>v2</td><td>(10) ar, zh, nl, fr, de, ja, fa, pt, ru, tr</td></tr><tr><td>speech-to-text-parallel</td><td>en</td><td>all</td><td><a href="https://www.mllp.upv.es/europarl-st/">Europarl-ST</a></td><td>v1.1</td><td>(4) fr, de, pt, tr</td></tr><tr><td>text-parallel</td><td>en</td><td>all</td><td><a href="https://www.statmt.org/europarl/v10/training">Europarl</a></td><td>v10</td><td>(2) fr, de</td></tr><tr><td>text-parallel</td><td>en</td><td>all</td><td><a href="https://www.statmt.org/europarl/v7/training">Europarl</a></td><td>v7</td><td>(4) nl, fr, de, pt</td></tr><tr><td>text-parallel</td><td>en</td><td>all</td><td><a href="https://data.statmt.org/news-commentary/v16/training">NewsCommentary</a></td><td>v16</td><td>(8) ar, zh, nl, fr, de, ja, pt, ru</td></tr><tr><td>text-parallel</td><td>en</td><td>all</td><td><a href="https://opus.nlpl.eu/OpenSubtitles-v2018.php">OpenSubtitles</a></td><td>v2018</td><td>(10) ar, zh, nl, fr, de, ja, fa, pt, ru, tr</td></tr><tr><td>text-parallel</td><td>en</td><td>de</td><td><a href="https://object.pouta.csc.fi/OPUS-TED2020/v1/tmx/de-en.tmx.gz">TED2020</a></td><td>v1</td><td>(1) de</td></tr><tr><td>text-parallel</td><td>en</td><td>all</td><td><a href="https://opus.nlpl.eu/Tatoeba.php">Tatoeba</a></td><td>v2022-03-03</td><td>(10) ar, zh, nl, fr, de, ja, fa, pt, ru, tr</td></tr><tr><td>text-parallel</td><td>en</td><td>de</td><td><a href="https://object.pouta.csc.fi/OPUS-ELRC-CORDIS_News/v1/tmx/de-en.tmx.gz">ELRC-CORDIS_News</a></td><td>v1</td><td>(1) de</td></tr></tbody></table>
  </details>

  <details>
    <summary style="padding-top: 10px; padding-bottom: 5px;"><em>Constrained pretrained models (click to expand)</em></summary><ul>
      <li><a href="https://github.com/pytorch/fairseq/blob/main/examples/wav2vec/README.md">wav2vec 2.0</a></li>
      <li><a href="https://github.com/pytorch/fairseq/tree/main/examples/hubert">HuBERT</a></li>
      <li><a href="https://github.com/microsoft/unilm/tree/master/wavlm">WavLM</a></li>
      <li><a href="https://github.com/microsoft/unilm/tree/master/speechlm">SpeechLM</a></li>
      <li><a href="https://github.com/facebookresearch/fairseq/tree/main/examples/data2vec">data2vec</a></li>
      <li><a href="https://github.com/pytorch/fairseq/blob/main/examples/mbart/README.md">MBART</a></li>
      <li><a href="https://github.com/pytorch/fairseq/tree/main/examples/multilingual#mbart50-models">MBART50</a></li>
      <li><a href="https://github.com/pytorch/fairseq/tree/main/examples/m2m_100">M2M100</a></li>
      <li><a href="https://github.com/microsoft/unilm/tree/master/deltalm">Delta LM</a></li>
      <li><a href="https://github.com/google-research/text-to-text-transfer-transformer">T5</a></li>
      <li><a href="https://huggingface.co/bigscience/bloom-560m#model-details">BLOOM (Note: only the smaller 560m parameter version)</a></li></ul>
  </details>

* **Unconstrained**: Any resource (additional datasets or pretrained language models included) can be used, with the important exception of evaluation sets and *any* data from ACL 2022 not provided on this page. 


### Development data

To mimic realistic test conditions where talk audio would be provided as a single file, not gold-segmented, we provide the full wav files and also automatically generated segments using [SHAS](https://github.com/mt-upc/SHAS) as a baseline segmentation. 
To evaluate translation quality of system output using any input segmentation, we provide gold sentence-segmented transcripts and translations, which system output can be scored against using resegmentation following the [steps below](#evaluation). 
We provide the full wav files to enable research into alternative segmentation methods. 

The development data is released [here](http://i13pc106.ira.uka.de/~jniehues/IWSLT-SLT/data/eval/en-xx/IWSLT-SLT.ACLdev2023.en-xx.tgz).


## Languages

This task covers ten language pairs with English as the source language and ten 60-60 languages as target languages. 
With this number of target languages, participants are encouraged to pursue multilingual modeling and submit results to all pairs (as opposed to individual models for each language pair), though models of any type are allowed. 

* **Source language:** English
* **Target languages:** Arabic, Chinese, Dutch, French, German, Japanese, Farsi, Portuguese, Russian, Turkish
  * Publicly available corpora are available for these language pairs for training (e.g. MuST-C) 

<!-- 
## Baselines

Links to the baselines to be used (descriptions, publications and/or links to models, code) 
-->


## Submission

Submissions should be compressed into a single .tar.gz file and emailed [here](mailto:iwslt.multilingual@gmail.com).  
Translation into all 10 target languages is expected for official ranking, though we also encourage submissions to a subset of language pairs, and strongly encourage all participants to also submit English ASR for analysis.  
Submissions should consist of plaintext files for each language pair with one sentence per line, pre-formatted for scoring (detokenized).
Multiple submissions are allowed! If multiple outputs are submitted, one system must be explicitly marked as **primary**, or the submission with the latest timestamp will be treated as primary.  

File names should follow the following structure:  
`<participant>.<constrained/unconstrained>.<primary/contrastive>.<src>-<tgt>.txt`  
e.g., `jhu.unconstrained.primary.en-de.txt`
  
Participants should specify in the submission email if their submission uses multilingual models and uses end-to-end or cascaded models for analysis. 
Training data and any pretrained models used should also be specified in the submission email; if data or pretrained models beyond the list allowed are used, the system should be marked unconstrained and will be ranked separately.


## Evaluation

Translation output will be evaluated using multiple metrics for analysis: translation output using chrF, BLEU, and recent neural metrics, and ASR output using WER. 
Translation metrics will be calculated with case and punctuation. 
WER will be computed on lowercased text with punctuation removed. 
Official metric scores will be calculated using automatic resegmentation of the hypothesis based on the reference transcripts (ASR) or translations (MT) by [mwerSegmenter](https://www-i6.informatik.rwth-aachen.de/web/Software/mwerSegmenter.tar.gz). 

### Ranking

The official task ranking will be based on the average chrF across the 10 translation language pairs, calculated by [SacreBLEU](https://github.com/mjpost/sacrebleu). 
If a submission does not include a language pair, it will receive 0 for that pair.
ASR will be evaluated separately, though it is strongly encouraged to submit ASR output as well.
We will provide human evaluation for language pairs where available; if we are able to provide human evaluation for all 10 languages, average human system ranking will be the official task ranking.

### Metrics

To compute official metrics, first download and install [mwerSegmenter](https://www-i6.informatik.rwth-aachen.de/web/Software/mwerSegmenter.tar.gz) following the instructions in `mwerSegmenter/README`.
Then, install [SacreBLEU](https://github.com/mjpost/sacrebleu#installation). 
```bash
wget https://www-i6.informatik.rwth-aachen.de/web/Software/mwerSegmenter.tar.gz
tar -zxvf mwerSegmenter.tar.gz
# set up following mwerSegmenter/README

pip install sacrebleu
```

Then, given raw text translation output, run mwerSegmenter to segment it to match the reference, and evaluate with SacreBLEU:
```bash
# example: en-de
tgt=de
src=IWSLT.ACLdev2023/text/IWSLT.ACL.ACLdev2023.en-xx.en.xml
ref=IWSLT.ACLdev2023/text/IWSLT.ACL.ACLdev2023.en-xx.${tgt}.xml
out=outs/IWSLT.ACLdev2023.en-de.hyp
sys=baseline

grep "<seg id" ${ref} | sed -e "s/<[^>]*>//g" > ${ref%.xml}.txt

mwerSegmenter/segmentBasedOnMWER.sh ${src} ${ref} ${out} ${sys} ${tgt} ${out}.sgm no_normalize 1
sed -e '/^<\/\?seg\|^<\/\?doc\|^<\/\?tstset/d' ${out}.sgm > ${out}.final

conda activate py3
sacrebleu ${ref%.xml}.txt -i ${out}.final -m chrf
```
*Note: unfortunately mwerSegmenter requires python2, and sacrebleu requires python3. You may need to switch environments between steps as shown.* 

#### Notes on Metric Tokenizers

We use chrF as the primary metric which enables use of the same metric and tokenization (sacrebleu default `13a`) for all target languages. 
For some languages, in particular those which do not mark whitespace, it can be recommended to use language-specific tokenization to create tokens for BLEU (Chinese, Japanese, Korean). 
We will evaluate chrF *without* language-specific tokenizers. For chrF, these tokenizers should not change the score. 
For BLEU, we *will* use the recommended language-specific tokenizers for Chinese, Japanese, and Korean in sacrebleu (`zh`, `ja-mecab`, `ko-mecab`) -- note, though, that BLEU will be an unofficial metric. 


## Organizers

* Elizabeth Salesky (JHU)
* Jan Niehues (KIT)
* Mona Diab (Meta)


## Contact

Chairs: iwslt.multilingual@gmail.com  
Discussion: <iwslt-evaluation-campaign@googlegroups.com>
