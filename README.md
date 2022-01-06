# CIF-ColDec
Supporting Information for Collaborative Decoding (ColDec) on CIF-based Speech Recognition.

### Data
Two files in LibriSpeech directory are simulated session-level biasing phrases for test-clean and test-other, respectively.

Details about in-house test sets are listed here:

| Details                                             | test-name | test-term |
| :-----                                              | :----: | :----: |
| Number of biasing utterances                        | 654 | 916 |
| Number of total utterances                          | 748 | 1219 |
| Number of distractor pharses in biasing list        | 600 | 1775 |
| Number of all phrases in biasing list               | 633 | 2415 |
| Ratio of rare target phrases in all target phrases  | 78.79 | 39.53 |
| Type of biasing phrases                             | name | term |

### Config
Configuration files in config directory cover S1, S2, S3 and S4 experiments on LibriSpeech in paper.

### References
\[1\] CIF-based Collaborative Decoding for End-to-end Contextual Speech Recognition
