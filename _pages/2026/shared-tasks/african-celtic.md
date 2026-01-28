---
permalink: /2026/african-celtic
title: "African & Celtic ST track"
toc: true
toc_sticky: true
---

<!--
Markdown notes: comments can be formed as in this example;
bulleted lines start with a - ;
if you want to have a line break either put a blank line in between the text or leave two spaces at the end of the line
-->

## Description

<!-- Description the task, the languages, and the type of data -->

The advancement of speech and language technology is critically dependent on large-scale data, often leaving low-resource language communities at a disadvantage. While recent progress in automatic speech translation (S2T and S2S) has begun to address low-resource settings
([Lupașcu et al., 2025](#ref-lupascu_large_2025);
[Mingote et al., 2023](#ref-10246390);
[Nabhani et al., 2024](#ref-nabhani-etal-2024-um);
[Pothula et al., 2025](#ref-e2e_speech_translation_2025);
[SeamlessM4T, 2023](#ref-communication2023seamlessm4tmassivelymultilingual)),
many languages remain severely underrepresented. A critical, yet often overlooked, challenge is the loss of linguistic and cultural fidelity when translating between low- and high-resource languages; key phonetic features, proper nouns, and culturally specific expressions are frequently distorted by models' lack of familiarity with the source language's nuances
([Goyle et al., 2023](#ref-goyle_neural_2023);
[Mishra et al., 2025](#ref-mishra2025languagetranslationchangeaccent);
[Prabhu et al., 2023](#ref-prabhu2023accentedspeechrecognitionaccentspecific)).
This shared task is designed to spur innovation in speech translation for underserved languages, with a focus on improving the preservation of these vital cultural and linguistic details.

The goal of this shared task is to advance speech translation for low-resource languages, focusing on challenges central to linguistic and cultural fidelity, such as the translation of proper nouns, named entities, and culturally specific terminology. The task is organized into two primary modeling tracks.

## Modeling Tracks

We host two official modeling tracks. The primary evaluation direction for both tracks is from the three low-resource source languages **into English**.

- **Track 1: Speech-to-Text Translation (S2T).**  
  This is the primary and foundational track. The goal is to **translate source-language speech into high-quality English text**. We encourage submission for any number of language pairs. The submission systems will be ranked per language, using evaluation metrics BLEU (official) and MetricX (provided for analysis)
  ([Juraska et al., 2024](#ref-juraska2024metricx24googlesubmissionwmt)). 
  For a particular interest in S2T translation, we also encourage participation in the multilingual low-resource track: [IWSLT 2026 Low Resource ST Track](https://iwslt.org/2026/low-resource)

- **Track 2: Speech-to-Speech Translation (S2S).**  
  This is the advanced track, targeting the holistic challenge of **end-to-end speech translation**. The goal is to translate source-language speech into English speech that is not only accurate in content but also natural and intelligible. Our unique dataset, which contains target-side English speech recorded by native speakers of the source languages, enables a rich analysis of how systems render paralinguistic features. The official evaluation metric will be ASR + CER (details provided below), with additional unofficial evaluation metrics provided for further analysis of the synthesized speech quality.


The official, ranked language direction is **from the three source languages** (Hausa, Igbo, Yorùbá) **into English**. While the provided parallel data also enables translation from English into the source languages, this direction is considered **exploratory**. We encourage participants to submit systems for these exploratory directions; results will be included and analyzed in the final overview paper but will not be part of the official ranking. Participants in the modeling tracks are free to submit to one or both tracks (S2T and S2S).

Any pretrained models and additional datasets are welcomed for the training portion of the task. 

## Data

Data is now available at [huggingface.co/datasets/McGill-NLP/african_celtic_dataset](https://huggingface.co/datasets/McGill-NLP/african_celtic_dataset)
<!-- Details description of the data and links to download -->
<!--*The dataset will be available on January 16th, 2026.* -->

<!-- Dataset Overview -->

The newly collected dataset comprises approximately **75 hours of newly recorded speech** derived from news articles in three African languages: Yorùbá, Igbo, and Hausa.
Utterances are split per language into **training, development, and test sets** (5,000 / 500 / 500 sentences, respectively). Segmentation is provided.
Training and development splits will be released in January for system development, with a held-out test set released during the evaluation period in April.

<!-- Data Splits and Speaker Information-->

The dataset includes **parallel source-language speech, source-language text, English text, and English speech** for each of the three African languages. The three African languages (Yorùbá, Igbo, Hausa) are not parallel with each other. The data includes up to 70 speakers per language, with held-out speakers in each of the development and test sets. Each low-resource language sentence in the training split is recorded by three different speakers, for a total of 15,000 sentences per language (5,000 unique), amounting to approximately **60–70 hours of training data per language pair.**
**Parallel English recordings** are included to capture accented English speech corresponding to the speaker’s native language (L1). The English test sets contain two varieties of **accented English: Northern Nigerian (N) and Southern Nigerian (Y).**
Each English sentence in the test sets is recorded twice (once per accent), while each English sentence in the training set is recorded once.

<!--Source Text and Data Curation-->

The original text source material was collected in English and manually translated into Hausa, Igbo, and Yorùbá by native speakers.

The training data consists of sentences drawn from three existing world-news text datasets:
- **MAFAND** ([Adelani et al., 2022](#ref-adelani-etal-2022-thousand))
- **NTREX** ([Barrault et al., 2019](#ref-barrault-etal-2019-findings); [Federmann et al., 2022](#ref-federmann-etal-2022-ntrex))
- **SSA-MT** ([Li et al., 2025](#ref-li2025ssacometllmsoutperformlearned))

The newly introduced test sets were curated from a combination of open-source newspapers, with a focus on arts and culture, business, and sports articles from *Voice of America*. Test data is evenly split between European-context and African-context articles.

*An optional additional Irish–English track may be added in February/March.*

### Data Format

All speech data is recorded at a **48 kHz sample rate** and saved as `.wav` files. There should be no need for additional audio post-processing.

The training and test data directories follow the structure below:

```text
train_set/
    English/
        USER_ID1/
            [LANGUAGE][DATASET]_[SENTENCE-NUMBER].wav
            text_ID.wav
        USER_ID2/
            text_ID.wav
            text_ID.wav
    Hausa/
        USER_ID1/
            text_ID.wav
            text_ID.wav
    Igbo/
        USER_ID/
            text_ID.wav
    Yoruba/
        USER_ID/
            text_ID.wav
```

All text transcriptions are available in `recordings_metadata.xlsx`, along with recording and sound information. All data should be shuffled before being used during training or testing. All text data should be normalized to remove punctuation, capitalization, etc. before training and testing. The following table details the file naming code:


| ID Dataset Code | Dataset |
|-----------------|---------|
| MD | MAFAND ([Adelani et al., 2022](#ref-adelani-etal-2022-thousand)) |
| NX | NTREX ([Barrault et al., 2019](#ref-barrault-etal-2019-findings); [Federmann et al., 2022](#ref-federmann-etal-2022-ntrex)) |
| TE | Test Set |
| TR | SSA-MT ([Li et al., 2025](#ref-li2025ssacometllmsoutperformlearned)) |



| Language Code | Language |
|---------------|----------|
| E | English |
| EN | English (North Nigeria accent) |
| EY | English (South Nigeria accent) |
| H | Hausa |
| I | Igbo |
| Y | Yoruba |


## Baselines
<!-- Links to the baselines to be used (descriptions, publications and/or links to models, code) -->

*Baseline results will be added in February.*

| Task | Baseline |
|------|----------|
| STT | SeamlessM4T ([Seamless, 2023](#ref-seamless2023))<br>Omnilingual ASR ([Omnilingual ASR Team, 2025](#ref-omnilingualasrteam2025omnilingualasropensourcemultilingual))<br>+ NLLB200 ([NLLB Team, 2022](#ref-nllb2022)) |
| STS | SeamlessM4T ([Seamless, 2023](#ref-seamless2023)) |




## Submission

*Submission instructions will be added before the evaluation period in April.*

<!-- Description of expected submission format and submission instructions -->


## Evaluation

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

| Track | Metrics |
|-------|---------|
| Speech-to-text | BLEU |
| Speech-to-speech | ASR + CER |

Additional unofficial metrics will be used for further analysis, such as MetricX and SQuID. 
The ASR system to be used for S2S evaluation is Omnilingual ASR (OmniASR_CTC_1B) ([Omnilingual ASR Team, 2025](#ref-omnilingualasrteam2025omnilingualasropensourcemultilingual)).


## Organizers
<!-- List of organizers' names and affiliations -->

- David Ifeoluwa Adelani, Mila - Quebec AI Institute & McGill University: david.adelani@mila.quebec
- Marie Maltais, Mila - Quebec AI Institute & McGill University: marie.maltais@mila.quebec
- Min Ma, Google DeepMind: minm@google.com
- Elizabeth Salesky, Google DeepMind: esalesky@google.com

### Contact
<!-- Add chair(s) and their contact info, as well as standard google group -->

- Chair(s): David Adelani david.adelani@mila.quebec
- Discussion: iwslt-evaluation-campaign@googlegroups.com


## References

- <a id="ref-adelani-etal-2022-thousand"></a>
  Adelani, D. I., Alabi, J., Fan, A., et al. (2022).
  *A Few Thousand Translations Go a Long Way! Leveraging Pre-trained Models for African News Translation*
  In *Proceedings of NAACL 2022*.
  https://aclanthology.org/2022.naacl-main.223

- <a id="ref-barrault-etal-2019-findings"></a>
  Barrault, L., Bojar, O., Costa-jussà, M. R., et al. (2019).
  *Findings of the 2019 Conference on Machine Translation (WMT19).*
  In *Proceedings of WMT 2019*.
  https://aclanthology.org/W19-5301

- <a id="ref-communication2023seamlessm4tmassivelymultilingual"></a>
  Barrault, L., Chung, Y.-A., Meglioli, M. C., et al. (2023).
  *SeamlessM4T: Massively multilingual & multimodal machine translation.*
  arXiv:2308.11596. https://arxiv.org/abs/2308.11596

- <a id="ref-nllb2022"></a>
  Costa-Jussà, M. R., Cross, J., Çelebi, O., Elbayad, M., Heafield, K., Heffernan, K., ... & NLLB Team. (2022). *No language left behind: Scaling human-centered machine translation.* arXiv preprint arXiv:2207.04672.

- <a id="ref-federmann-etal-2022-ntrex"></a>
  Federmann, C., Kocmi, T., & Xin, Y. (2022).
  *NTREX-128: News test references for MT evaluation of 128 languages.*
  https://aclanthology.org/2022.sumeval-1.4

- <a id="ref-goyle_neural_2023"></a>
  Goyle, V., Krishnaswamy, P., Ravikumar, K. G., Chattopadhyay, U., & Goyle, K. (2023).
  *Neural machine translation for low-resource languages.*
  arXiv:2304.07869. https://arxiv.org/abs/2304.07869

- <a id="ref-juraska2024metricx24googlesubmissionwmt"></a>
  Juraska, J., Deutsch, D., Finkelstein, M., & Freitag, M. (2024).
  *MetricX-24: The Google submission to the WMT 2024 metrics shared task.*
  arXiv:2410.03983. https://arxiv.org/abs/2410.03983

<!-- - <a id="ref-lee-etal-2022-direct"></a>
  Lee, A., Chen, P.-J., Wang, C., et al. (2022).
  *Direct speech-to-speech translation with discrete units.*
  In *Proceedings of ACL 2022*.
  https://aclanthology.org/2022.acl-long.235/ -->

- <a id="ref-li2025ssacometllmsoutperformlearned"></a>
  Li, S., Wang, J., Ali, F. D. M. A., et al. (2025).
  *SSA-COMET: Do LLMs outperform learned metrics in evaluating MT for under-resourced African languages?*
  arXiv:2506.04557. https://arxiv.org/abs/2506.04557

- <a id="ref-lupascu_large_2025"></a>
  Lupascu, M., Rogoz, A.-C., Stupariu, M. S., & Ionescu, R. T. (2025).
  *Large multimodal models for low-resource languages: A survey.*
  arXiv:2502.05568. https://arxiv.org/abs/2502.05568

- <a id="ref-10246390"></a>
  Mingote, V., Gimeno, P., Vicente, L., et al. (2023).
  *Direct text to speech translation system using acoustic units.*
  *IEEE Signal Processing Letters*, 30, 1262–1266.
  https://doi.org/10.1109/LSP.2023.3313513

- <a id="ref-mishra2025languagetranslationchangeaccent"></a>
  Mishra, A., Chowdhury, R. S., Bahuguna, V., Pandey, I., & Ramakrishnan, G. (2025).
  *Language translation, and change of accent for speech-to-speech task using diffusion model.*
  arXiv:2505.04639. https://arxiv.org/abs/2505.04639

- <a id="ref-nabhani-etal-2024-um"></a>
  Nabhani, S., Williams, A., Jannat, M., et al. (2024).
  *UM IWSLT 2024 low-resource speech translation.*
  In *Proceedings of IWSLT 2024*, ACL.
  https://aclanthology.org/2024.iwslt-1.14/

- <a id="ref-omnilingualasrteam2025omnilingualasropensourcemultilingual"></a>
  Omnilingual ASR Team et al. (2025).
  *Omnilingual ASR: Open-source multilingual speech recognition for 1600+ languages.*
  arXiv:2511.09690. https://arxiv.org/abs/2511.09690

- <a id="ref-e2e_speech_translation_2025"></a>
  Pothula, A., Akkiraju, B., Bandarupalli, S., Kesiraju, S., & Vuppala, A. K. (2025). *End-to-End Speech Translation for Low-Resource Languages Using Weakly Labeled Data.* arXiv preprint arXiv:2506.16251.

- <a id="ref-prabhu2023accentedspeechrecognitionaccentspecific"></a>
  Prabhu, D., Jyothi, P., Ganapathy, S., & Unni, V. (2023).
  *Accented speech recognition with accent-specific codebooks.*
  arXiv:2310.15970. https://arxiv.org/abs/2310.15970

- <a id="ref-sellam2023squid"></a>
  Sellam, T., Bapna, A., Camp, J., Mackinnon, D., Parikh, A. P., & Riesa, J. (2023).
  *SQuID: Measuring speech naturalness in many languages.*
  In *ICASSP 2023*. IEEE.

- <a id="ref-seamless2023"></a>
  Seamless Communication et al. (2023).
  *Seamless: Multilingual expressive and streaming speech translation.*
  arXiv. https://arxiv.org/abs/2308.11596

