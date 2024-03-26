# CSCI544-Predicting_Part_of_Speech_tag

## Overview
This project focuses on implementing Hidden Markov Models (HMMs) for part-of-speech (POS) tagging using the Wall Street Journal section of the Penn Treebank dataset. The tasks include creating a vocabulary, learning an HMM model, and implementing both greedy and Viterbi decoding algorithms to predict POS tags.

## Tasks and Solutions

### Vocabulary Creation
- **Objective**: Create a vocabulary from the training data, replacing rare words with a special token `<unk>`.
- **Threshold**: Words with occurrences below 2 are considered rare and replaced with `<unk>`.
- **Vocabulary Size**: 23,182 words, including `<unk>`.
- **Occurrences of `<unk>`**: 20,011.

### Model Learning
- **Objective**: Learn an HMM model from the training data, calculating emission and transition probabilities.
- **Model Details**: The HMM model consists of 2,070 transition parameters and 1,043,190 emission parameters.

### Greedy Decoding with HMM
- **Objective**: Implement and evaluate the greedy decoding algorithm on the development data.
- **Accuracy on Dev Data**: 93.51%.
- **Implementation Details**: The algorithm iterates through sentences, selecting tags based on the highest probability considering transition and emission probabilities.

### Viterbi Decoding with HMM
- **Objective**: Implement and evaluate the Viterbi decoding algorithm on the development data.
- **Accuracy on Dev Data**: 94.81%.
- **Implementation Details**: Utilizes dynamic programming to find the most likely sequence of tags for each sentence.

## File Descriptions

- `vocab.txt`: Contains the vocabulary created from the training data. Each line includes a word, its index, and occurrences, separated by a tab.
- `hmm.json`: Contains the HMM model parameters, including emission and transition probabilities in JSON format.
- `greedy.out`: Predictions made using the greedy decoding algorithm on the test data.
- `viterbi.out`: Predictions made using the Viterbi decoding algorithm on the test data.

## Evaluation
To evaluate the performance of the POS tagging models, use the provided `eval.py` script with the following command:

```bash
python eval.py -p {predicted_file} -g {gold_standard_file}

