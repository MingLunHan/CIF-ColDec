# CIF-ColDec

<div align="center">

**Collaborative Decoding (ColDec) for Contextual & Customized CIF-based ASR**

[![Paper](https://img.shields.io/badge/Paper-ICASSP%202022-blue)](https://ieeexplore.ieee.org/document/9747101)
[![Original](https://img.shields.io/badge/Original-ICASSP%202021-blue)](https://ieeexplore.ieee.org/document/9415054)
[![Framework](https://img.shields.io/badge/Framework-PyTorch-ee4c2c)](https://pytorch.org/)
[![License](https://img.shields.io/badge/License-MIT-lightgrey)](./LICENSE)

</div>

> 📌 **Collaborative Decoding (ColDec)** is proposed to customize CIF-based ASR models. Its application to ASR **contextualization, customization, and personalization** is the first attempt to integrate textual knowledge or content using **token-level acoustic representations** in CIF-based models.

This repository provides all supporting materials for the paper [**Improving End-to-End Contextual Speech Recognition with Fine-Grained Contextual Knowledge Selection**](https://ieeexplore.ieee.org/document/9747101) (accepted at **IEEE ICASSP 2022**), for the convenience of reproducibility and comparison.

📧 If you have any questions, feel free to contact me at hanminglun1996@foxmail.com.

---

## Table of Contents

- [1. Datasets](#1-datasets)
  - [a. LibriSpeech (Public)](#a-librispeech-public)
  - [b. In-house 160k-Hour Dataset](#b-in-house-160k-hour-dataset)
- [2. Configurations](#2-configurations)
- [3. Results on LibriSpeech](#3-results-on-librispeech)
- [4. References](#4-references)
- [5. Other CIF Resources](#5-other-cif-resources)
- [6. Citing ColDec](#6-citing-coldec)

---

## 1. Datasets

> **Note:** All biasing lists are **session-level** — every utterance in a given test set shares the same biasing list. All contextual biasing experiments target **open-domain** scenarios, where biasing phrases may appear in any textual context.

### a. LibriSpeech (Public)

Files in the `data/` directory are simulated session-level biasing phrases for `test-clean` and `test-other`, respectively. Details of the LibriSpeech test sets and biasing lists:

| Details | test-clean | test-other |
| :--- | :---: | :---: |
| Number of biasing utterances | 955 | 1032 |
| Number of total utterances | 2620 | 2939 |
| Number of all phrases in biasing list | 1171 | 1129 |
| Coverage (%) — biasing words / all words in references | 2.74 | 2.78 |

### b. In-house 160k-Hour Dataset

The in-house 160k-hour ASR dataset contains Mandarin Chinese and English audio. Most data are self-collected and manually labeled, covering common acoustic scenarios and videos. The test sets are collected from **internal real meetings**; participant **names** and **terms** (artificial intelligence, pattern recognition, signal processing, etc.) are treated as contextual information.

| Details | test-name | test-term |
| :--- | :---: | :---: |
| Number of biasing utterances | 654 | 916 |
| Number of total utterances | 748 | 1219 |
| Number of distractors in biasing list | 600 | 1775 |
| Number of all phrases in biasing list | 633 | 2415 |
| Rare Ratio (%) — rare target phrases / all target phrases | 78.79 | 39.53 |
| Type of biasing phrases | name | term |
| Coverage (%) — biasing tokens / all tokens in references | 18.7 | 35.5 |

<details>
<summary><b>Examples — test-term</b> (target biasing phrases in <b>bold</b>)</summary>

1. 波峰我最多我希望只拿到他的一个 **包络线**
   - Target: 包络线
2. 然后我得到文本序列以后我有可能进一步进步 **数据挖掘** **意图识别** 视频识别 **句法分析** 等等等等
   - Target: 数据挖掘、意图识别、句法分析
3. 汉字是由 **象形文字** 发展而来的因此可以采用类似于图像识别的方式对汉字进行 **形近字挖掘**
   - Target: 象形文字、形近字挖掘

</details>

<details>
<summary><b>Examples — test-name</b> (target biasing phrases in <b>bold</b>)</summary>

1. **肇兴** 一起加进来我们聊一下数据合规性的事吧
   - Target: 肇兴
2. 所以你刚刚举的 **张小花** 这个我觉得不是一个特别典型的一个例子吧但是的确是其中的一种情况
   - Target: 张小花

</details>

---

## 2. Configurations

Complete configuration files in the `config/` directory cover all experiments on LibriSpeech. The learning-rate scheduler is shown below:

<div align="center">
  <img src="https://github.com/MingLunHan/CIF-ColDec/blob/main/learning_rate_scheduler.png" alt="Learning-rate scheduler" width="50%" />
</div>

---

## 3. Results on LibriSpeech

<div align="center">
  <img src="https://github.com/MingLunHan/CIF-ColDec/blob/main/res_on_librispeech.png" alt="Results on LibriSpeech" width="50%" />
</div>

---

## 4. References

1. [CIF-based Collaborative Decoding for End-to-End Contextual Speech Recognition](https://ieeexplore.ieee.org/document/9415054)
2. [Improving End-to-End Contextual Speech Recognition with Fine-Grained Contextual Knowledge Selection](https://ieeexplore.ieee.org/document/9747101)
3. [CIF: Continuous Integrate-and-Fire for End-to-End Speech Recognition](https://ieeexplore.ieee.org/document/9054250)

---

## 5. Other CIF Resources

### a. Papers

- **ASR**
  - [CIF: Continuous Integrate-and-Fire for End-to-End Speech Recognition](https://ieeexplore.ieee.org/document/9054250)
  - [A Comparison of Label-Synchronous and Frame-Synchronous End-to-End Models for Speech Recognition](https://arxiv.org/abs/2005.10113)

- **ASR Contextualization / Customization / Personalization**
  - [CIF-based Collaborative Decoding for End-to-End Contextual Speech Recognition](https://ieeexplore.ieee.org/document/9415054)
  - [Improving End-to-End Contextual Speech Recognition with Fine-Grained Contextual Knowledge Selection](https://ieeexplore.ieee.org/document/9747101)

- **Low-resource Speech Recognition**
  - [Efficiently Fusing Pretrained Acoustic and Linguistic Encoders for Low-resource Speech Recognition](https://arxiv.org/abs/2101.06699)

- **Non-Autoregressive ASR**
  - [Boundary and Context Aware Training for CIF-based Non-Autoregressive End-to-End ASR](https://arxiv.org/abs/2104.04702)
  - [A Comparative Study on Non-Autoregressive Modelings for Speech-to-Text Generation](https://arxiv.org/abs/2110.05249)
  - [Non-Autoregressive Lipreading Model with Integrate-and-Fire](https://arxiv.org/abs/2008.02516)
  - [FastLR: Non-Autoregressive Lipreading Model with Integrate-and-Fire](https://arxiv.org/pdf/2008.02516)

- **Speech Translation**
  - [Exploring Continuous Integrate-and-Fire for Adaptive Simultaneous Speech Translation](https://arxiv.org/abs/2204.09595)

### b. Repositories

- [**CIF-PyTorch**](https://github.com/MingLunHan/CIF-PyTorch) — A PyTorch implementation of a standalone CIF module.
- [**CIF-ColDec**](https://github.com/MingLunHan/CIF-ColDec) — CIF-based Contextualization and Collaborative Decoding.

---

## 6. Citing ColDec

If ColDec inspires your research or you need to cite it, please use the following formats.

### a. Original ColDec (ICASSP 2021)

```bibtex
@inproceedings{9415054,
  author    = {Han, Minglun and Dong, Linhao and Zhou, Shiyu and Xu, Bo},
  booktitle = {ICASSP 2021 - 2021 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP)},
  title     = {Cif-Based Collaborative Decoding for End-to-End Contextual Speech Recognition},
  year      = {2021},
  pages     = {6528--6532},
  doi       = {10.1109/ICASSP39728.2021.9415054}
}
```

### b. Enhanced ColDec with Fine-grained Knowledge (ICASSP 2022)

```bibtex
@inproceedings{9747101,
  author    = {Han, Minglun and Dong, Linhao and Liang, Zhenlin and Cai, Meng and Zhou, Shiyu and Ma, Zejun and Xu, Bo},
  booktitle = {ICASSP 2022 - 2022 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP)},
  title     = {Improving End-to-End Contextual Speech Recognition with Fine-Grained Contextual Knowledge Selection},
  year      = {2022},
  pages     = {8532--8536},
  doi       = {10.1109/ICASSP43922.2022.9747101}
}
```

---

⭐ If you find this repository helpful, please consider giving it a star.
