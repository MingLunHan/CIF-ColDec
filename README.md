# CIF-ColDec
Supporting Information for Collaborative Decoding (ColDec) on CIF-based Speech Recognition.

### 1. Data
Files in data directory are simulated session-level biasing phrases for test-clean and test-other, respectively. Note that all biasing lists are session-level, because the utterances in a test set shares the same biasing list.

Details about LibriSpeech test sets and biasing lists are listed here:

| Details                                             | test-clean | test-other |
| :-----                                              | :----: | :----: |
| Number of biasing utterances                        | 654 | 916 |
| Number of total utterances                          | 748 | 1219 |
| Number of all phrases in biasing list               | 633 | 2415 |
| Coverage (%)                                        | | |

Details about in-house test sets and biasing lists are listed here:

| Details                                             | test-name | test-term |
| :-----                                              | :----: | :----: |
| Number of biasing utterances                        | 654 | 916 |
| Number of total utterances                          | 748 | 1219 |
| Number of distractor pharses in biasing list        | 600 | 1775 |
| Number of all phrases in biasing list               | 633 | 2415 |
| Rare Ratio (%) (# of rare target phrases / # of all target phrases) | 78.79 | 39.53 |
| Coverage (%)                                        |  |  |
| Type of biasing phrases                             | name | term |

### 2. Config
Configuration files in config directory cover S1, S2, S3 and S4 experiments on LibriSpeech in paper.

### 3. References
\[1\] CIF-based Collaborative Decoding for End-to-end Contextual Speech Recognition
