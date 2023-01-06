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
* Training data includes publicly available corpora and pretrained models. <!-- XX link to list -->
  * Allowed training data is the same for all talk translation tracks, as is the source language and a subset of the target languages. 
  * We encourage joint submissions across tracks to enable additional analysis and conference discussion!

Training and development data will be released in January.
{: .notice--info}


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
e.g., `jhu.primary.en-de.txt`
  
Participants should specify in the submission email if their submission uses multilingual models and uses end-to-end or cascaded models for analysis. 
Training data and any pretrained models used should also be specified in the submission email; if data or pretrained models beyond the list allowed are used, the system should be marked unconstrained and will be ranked separately.


## Evaluation

Translation output will be evaluated using multiple metrics for analysis: translation output using chrF, BLEU, and recent neural metrics, and ASR output using WER. 
Translation metrics will be calculated with case and punctuation. 
Official chrF and BLEU scores will be calculated using automatic resegmentation of the hypothesis based on the reference translation by [mwerSegmenter](https://www-i6.informatik.rwth-aachen.de/web/Software/mwerSegmenter.tar.gz), though we will also compute segment-based scores for analysis. 
WER will be computed on lowercased text with punctuation and hesitations removed (handled by the scoring script, linked here after data is released). 

### Ranking

The official task ranking will be based on the average chrF across the 10 translation language pairs, calculated by [SacreBLEU](https://github.com/mjpost/sacrebleu). 
If a submission does not include a language pair, it will receive 0 for that pair.
ASR will be evaluated separately, though it is strongly encouraged to submit ASR output as well.
We will provide human evaluation for language pairs where available; if all 10 languages are able to be covered, average human system ranking will be the official task ranking.

<!--
### Metrics

To compute official translation scores, install [SacreBLEU](https://github.com/mjpost/sacrebleu) and use the commands: 
```bash
XX sacrebleu commands
```
WER will be computed by the [XX]() script in the official data repository: 
```bash
XX WER commands
```
-->


## Organizers

* Elizabeth Salesky (JHU)
* Jan Niehues (KIT)
* Mona Diab (Meta)


## Contact

Chairs: iwslt.multilingual@gmail.com  
Discussion: <iwslt-evaluation-campaign@googlegroups.com>
