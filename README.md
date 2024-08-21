# PRODIGy: a PROfile-based DIalogue Generation dataset

Welcome to the PRODIGy repository! PRODIGy is a collection of dialogues, featured in the work titled [**PRODIGy: a PROfile-based DIalogue Generation dataset**](https://arxiv.org/abs/2311.05195), in which each conversation is aligned with speaker profile representations, including biography, language style, gender, and personality.

## Overview

We created PRODIGy starting from the Cornell Movie Dialogs Corpus (Cristian Danescu-Niculescu-Mizil and Lillian Lee, 2011), a dataset comprising dialogues between two speakers from movie scripts. In our work, we associated the characters with personality information, specifically the Myers–Briggs Type Indicator (MBTI) personality types, biography description and gender information. To account for the diversity in the way a biography can be expressed, we generate two alternative paraphrases for every sentence in the biography, which have been incorporated into our dataset. More details on the creation of the dataset can be found in our paper.

<p align="center">
  <img src="imgs/persona_pic.png" width="400" alt="Persona Picture">
</p>

## Dataset Description

PRODIGy dialogues are aligned with the following dimensions of one of the speakers: gender, MBTI personality type, character biography, and characters' dialogues. 

The following table reports the dataset's main statistics in terms of counts.

| Statistic                | Value          |
| ------------------------ | -------------- |
| **Dialogues**            | 20850          |
| **Turns**                | 80604          |
| **Annotated Characters** | 339            |

The following table reports the dataset's main statistics in terms of averages.

| Statistic                | Value          |
| ------------------------ | -------------- |
| **Turns per Dialogue**   | 4 (&plusmn;3.28)  |
| **Dialogues per Character** | 78 (&plusmn;31.21) |
| **Sentences per Bio**    | 8 (&plusmn;1.57)  |
| **Token per Bio sentence** | 13 (&plusmn;5.66)|

## File Description

In the folder `dataset`, we provide the following files:
+ `prodigy_dataset.json`: the list of dialogues and related speakers,
+ `characters.json`: the list of characters annotated with gender, MBTI, biographies and related paraphrases.

In the folder `experimental_partitions`, we provide the following files:
+ `inter_character_partitions.json`: the list of indexes for train, valid and test partitions used in the Inter-Character experiments, in which the test characters are not used at training time,
+ `intra_character_partitions.json`: the list of indexes for train, valid and test partitions used in the Intra-Character experiments, at training time the system learns about the specific characters to be predicted at test time.

For a deeper understanding of these experimental configurations, refer to our paper.

## Citation 

Further details can be found in our paper:

Daniela Occhipinti, Serra Sinem Tekiroglu, Marco Guerini. 2023. *PRODIGy: a PROfile-based DIalogue Generation dataset*. arXiv preprint arXiv:2311.05195

```bibtex
@inproceedings{occhipinti-etal-2024-prodigy,
    title = "{PRODIG}y: a {PRO}file-based {DI}alogue Generation dataset",
    author = "Occhipinti, Daniela  and
      Tekiroglu, Serra  and
      Guerini, Marco",
    editor = "Duh, Kevin  and
      Gomez, Helena  and
      Bethard, Steven",
    booktitle = "Findings of the Association for Computational Linguistics: NAACL 2024",
    month = jun,
    year = "2024",
    address = "Mexico City, Mexico",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2024.findings-naacl.222",
    doi = "10.18653/v1/2024.findings-naacl.222",
    pages = "3500--3514",
    abstract = "Providing dialogue agents with a profile representation can improve their consistency and coherence, leading to better conversations. However, current profile-based dialogue datasets for training such agents contain either explicit profile representations that are simple and dialogue-specific, or implicit representations that are difficult to collect. In this work, we introduce the PRODIGy (PROfile-based DIalogue Generation) dataset, which brings diverse representations together, providing a more comprehensive profile dimension set for each speaker. This resource comprises more than 20k dialogues, sourced from movie scripts, aligned with speaker representations such as communication style, biography, personality and gender. Initial experiments with diverse baselines show that providing generative language models with these aspects of a profile, both separately and jointly, enhances models{'} performance. This improvement holds true in both in-domain and cross-domain settings, for both fine-tuned and instruction-based LLMs.",
}
```
