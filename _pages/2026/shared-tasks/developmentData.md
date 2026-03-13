---
permalink: /2026/developmentData
title: "Development data"
toc: true
toc_sticky: true
---

## Development data for IWSLT 2026
  
Audio-visual documents of development sets are provided in MP4 format (asharq-bloomberg and ITV) and WAV format (YODAS); subtitles of development sets are released in SRT (SubRip File Format) UTF-8 encoded files, the same format required for submissions.

* [ITV Studios](https://www.itvstudios.com/) is part of ITV Plc, which includes the UK's largest commercial broadcaster. They create and produce a broad range of programming (drama, entertainment, factual) in 13 countries, which they distribute globally, providing high-quality subtitles. We would like to thank ITV Studios for providing IWLST with samples of their video content for research and evaluation purposes and would like to ask you not to use these videos and/or the accompanying subtitles for any commercial purposes or to make them publicly available on any other website. 

  * As a new **dev2026** development set, 3 episodes of a television series,  with an approximate duration of 2.5 hours in total, can be downloaded from [here](https://fbk.sharepoint.com/:u:/s/MTUnit/IQCsSfKNTQaZRpJa_o42z7OIAUG-vRXKC5zsgH4WXXy-_yc?e=o7you5).\
    NOTES: English SRT files are provided for informational purposes only. The [dev set](https://iwslt.org/2025/subtitling#development-and-evaluation-data) from previous years can also be used for system development and training.    


* [Asharq Business with Bloomberg](https://asharqbusiness.com/) is part of SRMG, the largest integrated media group in the MENA (Middle East and North Africa) region. An exclusive content agreement with 'Bloomberg Media' powers this distinguished business news multi-platform, drawing on Bloomberg's comprehensive coverage from more than 2,700 journalists and analysts globally. Asharq Business with Bloomberg is a leading source for Arabic economic news rich in context and content and unparalleled market data, delivered through a TV channel and across digital and social media platforms. Professional human reference translations into Chinese, Japanese, Arabic, and German have been created by [AppTek](https://apptek.ai).

  * As a **dev2026** set, 2 recordings of about 2.5 hours each, including actual Asharq-Bloomberg news content, can be downloaded from [here](https://fbk.sharepoint.com/:u:/s/MTUnit/IQCdLQi6CvMVTp30OP-yv_XOAeXoxXeqFGjQTUsV0nI_rFg?e=kESdHA).  The archive contains a README file with important infos, audios, reference subtitles, and YAML files which provide the audio segments for which subtitles must be created (the rest of the video file can be ignored). The dev set was already used in the 2025 evaluation, but now Chinese and Japanese were added as the additional target languages.


* [YODAS](https://huggingface.co/datasets/espnet/yodas) (YouTube-Oriented Dataset for Audio and Speech) is *"a large-scale, multilingual dataset comprising currently over 500k hours of speech data in more than 100 languages, sourced from both labeled and unlabeled YouTube speech datasets.*" Refer to this [paper](https://ieeexplore.ieee.org/abstract/document/10389689) for more details.\
IMPORTANT NOTE: the "[en003](https://huggingface.co/datasets/espnet/yodas/tree/main/data/en003)" partition of the Yodas dataset is used for selecting dev/test data and is therefore not permitted for training (e.g. for an auxiliary ASR task). This partition had also been used to select a speech recognition benchmarking test set by the creators of the [Loquacious](https://huggingface.co/datasets/speechbrain/LoquaciousSet) dataset and thus is a natural held-out choice. Professional human reference translations into Chinese, Japanese, and German have been created by [AppTek](https://apptek.ai).
  * The **dev2026** development set, consisting of 6 files, can be downloaded from [here](https://fbk.sharepoint.com/:u:/s/MTUnit/IQCxga_cA9xcQLbQhuOSwhRUAcWmw8Se2Tq-24yfBfodOjQ?e=s49yng)

Verbatim transcripts are available under the above links for each development set, except ITV Studios.
