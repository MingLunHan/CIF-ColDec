# **CIF-ColDec**
Supporting Information for enhanced Collaborative Decoding (ColDec) on CIF-based Speech Recognition for the convenience of reproductivity and comparison.

### 1. **Data**

Note that all biasing lists are session-level, because each utterance in one test set shares the same biasing list. All our contextual biasing experiments are for open-domain scenarios where biasing phrases may appear in any textual context. 

#### a. **LibriSpeech**
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

### 2. **Config**
Complete Configuration files in config directory cover all experiments on LibriSpeech in paper. The learning rate scheduler is shown here:

![image](https://github.com/MingLunHan/CIF-ColDec/blob/main/learning_rate_scheduler.png)

### 3. **References**
\[1\] CIF-based Collaborative Decoding for End-to-end Contextual Speech Recognition https://arxiv.org/abs/2012.09466

\[2\] CIF: Continuous Integrate-and-Fire for End-to-End Speech Recognition https://arxiv.org/abs/1905.11235

