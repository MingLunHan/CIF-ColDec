# **CIF-ColDec**

Collaborative decoding (ColDec) is proposed to customize the CIF-based ASR models. The application of ColDec in the field of ASR contextualization, customization and personalization is the first attempt to integrate textual knowledge or contents using token-level acoustic representations in the CIF-based models.

This repository includes all supporting information of paper **IMPROVING END-TO-END CONTEXTUAL SPEECH RECOGNITION WITH FINE-GRAINED CONTEXTUAL KNOWLEDGE SELECTION** https://ieeexplore.ieee.org/document/9747101 (which has been accepted for presentation at IEEE ICASSP 2022) for the convenience of reproductivity and comparison.

If you have any questions, please consult hanminglun1996@foxmail.com .

### 1. **Datasets**

Note that all biasing lists are session-level, because each utterance in one test set shares the same biasing list. All our contextual biasing experiments are for open-domain scenarios where biasing phrases may appear in any textual context. 

#### a. **LibriSpeech Public Dataset**

Files in data directory are simulated session-level biasing phrases for test-clean and test-other, respectively. Details about LibriSpeech test sets and biasing lists are listed as follows:

| Details                                             | test-clean | test-other |
| :-----                                              | :----: | :----: |
| Number of biasing utterances                        | 955 | 1032 |
| Number of total utterances                          | 2620 | 2939 |
| Number of all phrases in biasing list               | 1171 | 1129 |
| Coverage (%) (# of all biasing words in references / # of all words in references) | 2.74 | 2.78 |

#### b. **In-house Large-scale 160k Hours Dataset**

The in-house 160k hours ASR datasets contains Chinese Mandarin audios and English audios. Most of the data are self-collected and manually labeled. Audios are collected from some common acoustic scenarios and videos. Its test sets are collected from internal real meetings. The names of participants and the terms of aritificial intelligence, pattern recognition, signal processing, are treated as contextual information. Details about the in-house test sets and biasing lists are listed as follows:

| Details                                             | test-name | test-term |
| :-----                                              | :----: | :----: |
| Number of biasing utterances                        | 654 | 916 |
| Number of total utterances                          | 748 | 1219 |
| Number of distractors in biasing list        | 600 | 1775 |
| Number of all phrases in biasing list               | 633 | 2415 |
| Rare Ratio (%) (# of rare target phrases / # of all target phrases) | 78.79 | 39.53 |
| Type of biasing phrases                             | name | term |
| Coverage (%) (# of all biasing tokens in references / # of all tokens in references) | 18.7 | 35.5 |

Here are some examples of test-term:

1) 波峰我最多我希望只拿到他的一个 **包络线** (Target biasing phrases: 包络线)

2) 然后我得到文本序列以后我有可能进一步进步 **数据挖掘** **意图识别** 视频识别 **句法分析** 等等等等  (Target biasing phrases: 数据挖掘、意图识别、句法分析)

3) 汉字是由 **象形文字** 发展而来的因此可以采用类似于图像识别的方式对汉字进行 **形近字挖掘**  (Target biasing phrases: 象形文字、形近字挖掘)

Here are some examples of test-name:

1) **肇兴** 一起加进来我们聊一下数据合规性的事吧 (Target biasing phrases: 肇兴)

2) 所以你刚刚举的 **张小花** 这个我觉得不是一个特别典型的一个例子吧但是的确是其中的一种情况（Target biasing phrases: 张小花）

### 2. **Configurations**

Complete Configuration files in config directory cover all experiments on LibriSpeech. The learning rate scheduler is shown as follows:

<img src="https://github.com/MingLunHan/CIF-ColDec/blob/main/learning_rate_scheduler.png" width="50%" height="50%">

### 3. **Results on LibriSpeech**

<img src="https://github.com/MingLunHan/CIF-ColDec/blob/main/res_on_librispeech.png" width="50%" height="50%">

### 4. **References**

\[1\] CIF-based Collaborative Decoding for End-to-End Contextual Speech Recognition https://ieeexplore.ieee.org/document/9415054

\[2\] Improving End-to-End Contextual Speech Recognition with Fine-Grained Contextual Knowledge Selection https://ieeexplore.ieee.org/document/9747101

\[3\] CIF: Continuous Integrate-and-Fire for End-to-End Speech Recognition https://ieeexplore.ieee.org/document/9054250

### 5. **Other CIF Resources**

#### a. Papers:

**ASR**:
  - CIF: Continuous Integrate-and-Fire for End-to-End Speech Recognition https://ieeexplore.ieee.org/document/9054250
  - A Comparison of Label-Synchronous and Frame-Synchronous End-to-End Models for Speech Recognition https://arxiv.org/abs/2005.10113

**ASR Contextualization & Customization & Personalization**:
  - CIF-based Collaborative Decoding for End-to-End Contextual Speech Recognition https://ieeexplore.ieee.org/document/9415054
  - Improving End-to-End Contextual Speech Recognition with Fine-Grained Contextual Knowledge Selection https://ieeexplore.ieee.org/document/9747101

**Low-resource Speech Recognition**:
  - Efficiently Fusing Pretrained Acoustic and Linguistic Encoders for Low-resource Speech Recognition https://arxiv.org/abs/2101.06699

**Non-autoregressive ASR**:
  - Boundary and Context Aware Training for CIF-based Non-Autoregressive End-to-end ASR https://arxiv.org/abs/2104.04702
  - A Comparative Study on Non-Autoregressive Modelings for Speech-to-Text Generation https://arxiv.org/abs/2110.05249
  - Non-Autoregressive Lipreading Model with Integrate-and-Fire https://arxiv.org/abs/2008.02516
  - FastLR: non-autoregressive lipreading model with integrate-and-fire https://arxiv.org/pdf/2008.02516

**Speech Translation**:
  - Exploring Continuous Integrate-and-Fire for Adaptive Simultaneous Speech Translation https://arxiv.org/abs/2204.09595

#### b. Repositories:

- A PyTorch implementation of a independent CIF module: https://github.com/MingLunHan/CIF-PyTorch

- CIF-based Contextualization: https://github.com/MingLunHan/CIF-ColDec

### 6. **Citing ColDec**

If you are inspired by ColDec or need to cite it, please use following format.

#### a. Original ColDec:

```
@INPROCEEDINGS{9415054,
  author={Han, Minglun and Dong, Linhao and Zhou, Shiyu and Xu, Bo},
  booktitle={ICASSP 2021 - 2021 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP)}, 
  title={Cif-Based Collaborative Decoding for End-to-End Contextual Speech Recognition}, 
  year={2021},
  volume={},
  number={},
  pages={6528-6532},
  doi={10.1109/ICASSP39728.2021.9415054}
}
```
#### b. Enhanced ColDec with Fine-grained Knowledge:
```
@INPROCEEDINGS{9747101,  
  author={Han, Minglun and Dong, Linhao and Liang, Zhenlin and Cai, Meng and Zhou, Shiyu and Ma, Zejun and Xu, Bo},  
  booktitle={ICASSP 2022 - 2022 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP)},  
  title={Improving End-to-End Contextual Speech Recognition with Fine-Grained Contextual Knowledge Selection}, 
  year={2022},  
  volume={}, 
  number={}, 
  pages={8532-8536}, 
  doi={10.1109/ICASSP43922.2022.9747101}
}
```


