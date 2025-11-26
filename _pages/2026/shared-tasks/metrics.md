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

An an example input, consider the following audio:

<audio controls>
    <source src="https://www.signalogic.com/melp/EngSamples/Orig/male.wav" type="audio/wav">
</audio>

and the corresponding testset entry:
```
{
    "src_wav": "sample.wav"
    "src_asr": "But what if somebody decides to break it? Be careful that you keep adequate coverage, but look for places to save money. Maybe it's taking longer to get things squared away than the bankers expected. Hiring the wife for one's company may win her tax-aided retirement income. The boost is helpful but inadequate. New self-deceiving rags are hurriedly tossed on the two naked bones. What a discussion can ensue when the title of this type of song is in question. There is no dying or waxing or gassing needed. Paperweight may be personalized on back while clay is leather hard. Place work on a flat surface and smooth out. The simplest kind of separate system uses a single self-contained unit. The old shop adage still holds: A good mechanic is usually a bad boss. Both figures would go higher in later years. Some make beautiful chairs, cabinets, chests, dollhouses, etc.",
    "tgt": "Aber was, wenn jemand beschließt, zu brechen es? Sei vorsichtig damit, dass du eine angemessene Deckung beibehältst, aber suche nach Plätzen, um Geld zu sparen. Vielleicht dauert es länger, die Dinge quadratisch zu bekommen, als die Banker erwartet hatten. Das Anstellen der Ehefrau für die eigene Firma kann erringen ihr steuerbegünstigtes Renteneinkommen. Die Steigerung ist hilfreich, aber nicht ausreichend. Neue, sich selbst täuschende Lumpen werden hastig auf die zwei nackten Knochen geworfen gewesen. Was für eine Diskussion kann erfolgen, wenn der Titel dieser Art von Lied in Frage steht. Es wird kein Sterben oder Wachsen oder Gasen benötigt. Das Papiergewicht kann auf der Rückseite personalisiert sein, während Ton Leder-hart ist. Platziere Arbeit auf einer flachen Oberfläche und glätte heraus. Die einfachste Art von separatem System benutzt eine einzige, in sich selbst enthaltene Einheit. Das alte Werkstatt-Sprichwort hält immer noch: Ein guter Mechaniker ist normalerweise ein schlechter Chef. Beide Zahlen würden höher gehen in späteren Jahren. Manche stellen schöne Stühle, Schränke, Truhen, Puppenhäuser, usw. her.",
    "score_human": 75.5,
}
```

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
- <b>acc<sub>eq</sub><sup>*</sup></b>: segment-level measure, akin to Pearson correlation groupped by item. This measures the ability of metrics to select the best translation given a single source.
- <b>Soft Pairwise Accuracy</b>: system-level measure. This reveals how good the metric is at ranking the participating systems.

We will provide evaluations scripts to verify dev data performance on January 1.

<!-- Description of metrics used for evaluation, what the official ranking is based on, links to evaluation scripts -->

## Organizers

<!-- List of organizers' names and affiliations -->

- Maike Züfle, Karlsruhe Institute of Technology, <maike.zuefle@kit.edu>
- Vilém Zouhar, ETH Zurich, <vzouhar@ethz.ch>
- Brian Thompson
- Dominik Macháček, Charles University
- Mattias Sperber, Apple
- Marine Carpuat, University of Maryland
- HyoJung Han, University of Maryland

## Contact

<!-- Add chair(s) and their contact info, as well as standard google group -->
Chair(s): Maike Züfle <maike.zuefle@kit.edu>; Vilém Zouhar <vzouhar@ethz.ch>

Discussion: <iwslt-evaluation-campaign@googlegroups.com>
