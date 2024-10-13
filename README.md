


# Neural POS Tagging

## Description

This project implements two models for **Part-of-Speech (POS) Tagging**:
1. A **Feed-Forward Neural Network (FFN)** that uses a fixed window of context tokens to predict the POS tag of a word.
2. A **Recurrent Neural Network (RNN)** (Vanilla RNN, LSTM, or GRU) that predicts the POS tags for all tokens in a sentence by processing the entire sentence as a sequence.

The assignment also involves experimenting with different hyperparameters and evaluating the models using various performance metrics.

## Requirements

- **Language**: Python
- **Framework**: PyTorch
- **Dataset**: Universal Dependencies dataset (EN_ATIS)
  - Use the files located at `ud-treebanks-v2.13/UD_English-Atis/en_atis-ud-{train,dev,test}.conllu`
  - Only use the first, second, and fourth columns (word index, lowercase word, POS tag).
- **Additional Libraries**:
  - `conllu` (for parsing the dataset)

## Features

### 1. Feed-Forward Neural Network POS Tagger
- Takes the embeddings of a token and its surrounding context (previous `p` and successive `s` tokens) and predicts the POS tag for the target token.

### 2. Recurrent Neural Network POS Tagger
- Takes embeddings for all tokens in a sentence and predicts POS tags for the entire sequence. You can implement this using a Vanilla RNN, LSTM, or GRU.

### 3. Hyperparameter Tuning
- Experiment with different hyperparameters for both models:
  - FFN: Number of hidden layers, hidden layer size, embedding size, activation functions, etc.
  - RNN: Number of layers, hidden state sizes, bidirectionality, etc.
  
## Evaluation Metrics
- Accuracy
- Precision, Recall, F1 Score (micro and macro)
- Confusion Matrices

## Graphs
- For FFN: Plot **context window size** vs **dev set accuracy**.
- For RNN: Plot **epoch** vs **dev set accuracy** for the three configurations being evaluated.

## Dataset
- **Universal Dependencies dataset**: You can download it from [this link](https://lindat.mff.cuni.cz/repository/xmlui/bitstream/handle/11234/1-5287/ud-treebanks-v2.13.tgz).
- The dataset does not contain punctuation. You can remove punctuation from input sentences before tagging.

## How to Run

1. **Clone the Repository**:
   ```bash
   git clone <repo-url>
   cd <repo-directory>
   ```

2. **Install Dependencies**:
   Install the required Python libraries:
   ```bash
   pip install torch conllu
   ```

3. **Run POS Tagger**:
   - For **Feed-Forward Neural Network** (FFN) POS Tagging:
     ```bash
     python pos_tagger.py -f
     ```
   - For **Recurrent Neural Network** (RNN) POS Tagging:
     ```bash
     python pos_tagger.py -r
     ```
   You will be prompted to enter a sentence for POS tagging. For example:
   ```bash
   > An apple a day
   ```
   The output will be:
   ```bash
   an DET
   apple NOUN
   a DET
   day NOUN
   ```

4. **Pretrained Models**:
   - If you have pretrained models, place them in the repository and ensure the `pos_tagger.py` script can load them using command-line arguments or paths mentioned in the code.

## Hyperparameter Tuning

1. **FFN Hyperparameters**: Experiment with different values for hidden layers, sizes, embeddings, and context windows.
2. **RNN Hyperparameters**: Experiment with different architectures (LSTM, GRU), number of layers, bidirectionality, and hidden sizes.

The tuning results and corresponding graphs will be documented in the accompanying report.


---

### Example Usage:

```bash
python pos_tagger.py -f
# Enter sentence for POS tagging:
An apple a day
# Output:
an DET
apple NOUN
a DET
day NOUN
```

---

