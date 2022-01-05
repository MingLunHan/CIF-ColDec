# CIF-ColDec
Supporting Information for Collaborative Decoding (ColDec) on CIF-based Speech Recognition.

ColDec transfers deep context to the CIF-based ASR \[1,2\] in a more controllable way. The CIF module in the CIF-based model non-uniformly compresses the length of acoustic features according to the acoustic boundaries of tokens, and emits token-level acoustic embeddings. These token-level acoustic embeddings provide a bridge to integrate textual context knowledge at the acoustic level. In ColDec, an extra context processing network (CPN) is trained to predict where to output which phrase according to the relevance between token-level acoustic embedding and context-specific phrases.

### data
Two files in data directory are simulated biasing phrases for test-clean and test-other, respectively.

### config
The configuration files in config directory cover S1, S2, S3 and S4 mentioned in \[2\]. Among them, 

### References
