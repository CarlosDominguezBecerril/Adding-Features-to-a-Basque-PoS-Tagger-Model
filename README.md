# Adding Features to a Basque PoS Tagger Model

## Project description

Part-of-speech (PoS) tagging is a popular Natural Language Processing task (NLP) that refers to categorizing words in a text (corpus) with respect to a specific part of speech, depending on the definition of the word and its context. Part-of-speech tags describe the characteristic structure of lexical terms within a sentence or text. Therefore, we can use them for making assumptions about semantics. In this project, we propose to use the Flair framework to predict the PoS tags for the Basque language in three different ways: predict only the basic tags, predict the basic tags together with another feature, and predict the basic tags along with two additional features.


## Paper

The paper is available as part of this repository

## Code

The code is available in a Jupyter Notebook

## Results


The performance results of the final models:

| Model            | Annotations | Loss   | Precision | Recall | F1     | Accuracy |
|------------------|-------------|--------|----------|--------|--------|----------|
| lemma_rule       | 72,974      | 0.3164 | 93.26    | 93.26  | 93.26  | 93.26    |
| definite         | 22,822      | 0.0851 | 29.92    | 95.38  | 45.56  | 29.92    |
| number           | 19,419      | 0.0714 | 25.52    | 95.93  | 40.31  | 25.52    |
| case             | 25,450      | 0.0878 | 33.31    | 95.91  | 49.45  | 33.31    |
| dependency       | 72,974      | 0.3454 | 90.31    | 90.31  | 90.31  | 90.31    |
| upos             | 72,974      | 0.1128 | 97.07    | 97.07  | 97.07  | 97.07    |
|------------------|-------------|--------|----------|--------|--------|----------|
| upos+lemma_rule  | 72,974      | 0.4670 | 90.41    | 90.41  | 90.41  | 90.41    |
| upos+definite    | 22,822      | 0.1203 | 29.09    | 92.72  | 44.29  | 29.09    |
| upos+number      | 19,419      | 0.0937 | 24.88    | 93.53  | 39.31  | 24.88    |
| upos+case        | 25,450      | 0.1412 | 32.12    | 92.47  | 47.68  | 32.12    |
| upos+dependency  | 72,974      | 0.4523 | 88.34    | 88.34  | 88.34  | 88.34    |
|------------------|-------------|--------|----------|--------|--------|----------|
| upos+definite+number | 19,150 | 0.0962 | 24.48   | 93.28  | 38.78  | 24.48    |
| upos+definite+case   | 22,501 | 0.1555 | 28.11   | 90.87  | 42.94  | 28.11    |
| upos+definite+dependency | 22,822 | 0.2849 | 25.26   | 80.51  | 38.45  | 25.26    |
| upos+number+case       | 22,501 | 0.1189 | 24.32   | 92.69  | 38.54  | 24.32    |
| upos+number+dependency | 19,419 | 0.2226 | 21.85   | 82.14  | 34.52  | 21.85    |
| upos+case+dependency   | 25,450 | 0.3335 | 27.82   | 80.11  | 41.30  | 27.82    |



The effects on models when merging each of the features:

| Feature | Precision (2-label) | Precision (3-label) | Recall (2-label) | Recall (3-label) | F1 (2-label) | F1 (3-label) |
|---------|---------------------|----------------------|------------------|------------------|-------------|-------------|
| +lemma\_rule | -2.8 |   | -2.8 |   | -2.8 |   |
| +definite | -0.8 | -22.5±28.7 | -2.7 | -3.2±3.3 | -1.3 | -18.4±22.3 |
| +number | **-0.6** | -26.3±28.4 | -2.4 | **-1.8**±3.1 | **-1.0** | -22.8±22.0 |
| +case | -1.2 | -20.7±28.2 | -3.4 | -3.64±3.3 | -1.8 | -16.4±21.7 |
| +dependency | -2.0 | **-3.7±\ 0.5** | **-2.0** | -12.0**±0.4** | -2.0 | **-5.7±\ 0.7** |
