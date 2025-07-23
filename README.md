
# A Dual Encoder Architecture for Robust,Adversarial Aware Sarcasm Detection across Heterogeneous Text Corpora.

**Author**: Ramakrishna Bodige  
**Email**: ramakrishnamail4u@gmail.com  
**Institution**: Department of Computer Science, SR University, Warangal, Telangana, India
# 1 Project Statement
Sarcasm detection is a critical challenge in natural language processing (NLP) due to its dependence on contextual, emotional, and cultural nuances. Detecting sarcasm accurately is essential for improving the understanding of human communication, especially in online interactions. This paper aims to propose an effective model for sarcasm detection with the Double BERT approach, addressing the challenges of capturing contextual, demographic diversity, cultural variance and emotional patterns from text. Existing sarcasm detection models often struggle with handling diverse linguistic features and contextual variations, leading to suboptimal performance across different datasets and domains.We developed a robust sarcasm detection model using Double BERT, trained on a mixed dataset consisting of 149,480 samples.
### Keywords: Sarcasm detection, contextual understanding, NLP, BERT, adversarial study
### Contributions:
1. Implemented Double BERT combining contextual embedding and classification
2. Trained/tested on mixed datasets across demographic/cultural contexts
3. Evaluated robustness via adversarial examples
4. Achieved **91.4% accuracy** and **91.2 weighted F1-score**
# 2 Method Overview

We implemented a Double BERT model for sarcasm detection by concatenating two BERT models:  
- First model for text embedding  
- Second model for classification  

**Implementation Steps**:  
1. Tokenize mixed dataset text into 768-dimensional vectors  
2. Generate position-level word embeddings (dimension: 30522 × 768)  
3. Process through BERT Encoder-1 for contextual embeddings  
4. Pass outputs to classification BERT for feature refinement  
5. Concatenate outputs from both BERT components  
6. Apply dropout layer to prevent overfitting  
7. Generate class probabilities via linear layer  

### 2.1 Text Embedding with BERT
**Process**:
1. WordPiece tokenization
2. Triple embedding:
   - **Word Embeddings**: 30522×768 dimensions
   - **Position Embeddings**: 512×768 dimensions
   - **Token Embeddings**: 2×768 dimensions

### 2.2 Classification BERT
Processes contextual embeddings using:
- Self-attention mechanism
- Feed-forward network
- Layer normalization

## 3 Dataset

**Sources**:
- SemEval-2020 (structured annotations)
- Reddit (conversational sarcasm)
- The Onion (cultural satire)
- Twitter (emotional/spontaneous sarcasm)

**Class Distribution**:
- Sarcastic: 47.2%
- Non-sarcastic: 52.8%
## Classification Report:
| Class         | Precision | Recall | F1-Score | Support |
|---------------|-----------|--------|----------|---------|
| Sarcasm (0)   | 0.89      | 0.90   | 0.90     | 2103    |
| Non-Sarcasm (1)| 0.92      | 0.91   | 0.92     | 2607    |
| **Accuracy**  |           |        | **0.91** | 4710    |
| Macro Avg     | 0.91      | 0.91   | 0.91     | 4710    |
| Weighted Avg  | 0.91      | 0.91   | 0.91     | 4710    |
## 4 Results
Twitter Dataset Comparison
| Category                    | Model              | Accuracy | Precision | Recall | F1-Score |
|-----------------------------|--------------------|----------|-----------|--------|----------|
| **Deep Learning Models**    | Bi-LSTM*           | 73.0     | 71.8      | 71.7   | 71.7     |
|                             | CNN-LSTM-DNN*      | 72.3     | 71.9      | 72.9   | 71.9     |
|                             | MIARN*             | 70.2     | 68.6      | 68.8   | 68.8     |
|                             | ADGCN*             | 73.6     | 72.6      | 73.2   | 72.8     |
|                             | DCNET*             | 76.7     | 76.4      | 77.5   | 76.3     |
| **Pre-trained Models**      | RoBERT*            | 73.9     | 72.7      | 72.8   | 72.8     |
|                             | ADGCN-RoBERT*      | 72.2     | 71.3      | 71.9   | 71.4     |
|                             | DC-Net-RoBERT*     | 70.9     | 69.7      | 68.3   | 68.7     |
| Eke et al. (2021)    | BERT+LSTM Fusion   | 76.3     | 81.2      | 78.5   | 76.3     |
| Srivastava et al. (2020)| BERT+BERT+Bi-LSTM  | 74.0†    | -         | -      | -        |
| Liu et al. (2023)       | SarcPrompt-Clash   | 76.9     | 77.1      | 78.3   | 76.6     |
| Liu et al. (2022)      | Bi-LSTM            | 73.0     | 71.8      | 71.7   | 71.7     |
| Lemmens et al. (2020)   | CNN-LSTM Ensemble  | -        | 75.6      | 75.2   | 75.2     |
| Baruah et al. (2020)    | BERT (5-fold CV)   | -        | 74.4      | 74.8   | 74.3     |
| **Proposed Model**          | **Double BERT**    | **83.4** | **83.8**  | **84.1**| **84.1** |


 Reddit Dataset Comparison
| System                      | Model                   | Accuracy | Precision | Recall | F1-Score |
|-----------------------------|-------------------------|----------|-----------|--------|----------|
| Srivastava et al. (2020)| BERT+BERT-Bi-LSTM       | 63.7†    | -         | -      | -        |
| Lemmens et al. (2020)  | CNN-LSTM Ensemble       | -        | 63.4      | 64.0   | 63.8     |
| Potamias et al. (2021) | Lexical+Deep Learning   | 85.0     | 78.0      | 78.0   | 78.0     |
| Baruah et al. (2020)     | BERT (5-fold CV)        | -        | 65.8      | 65.8   | 65.8     |
| **Proposed Model**          | **Double BERT**         | **83.6** | **80.8**  | **88.1**| **84.4** |


 Mixed Dataset Comparison
| System                 | Model                              | Accuracy | Precision | Recall | F1-Score |
|------------------------|------------------------------------|----------|-----------|--------|----------|
| Li et al. (2021)  | Attention Mechanism with Bi-LSTM   | 88.0     | 86.5      | 87.0   | 86.7     |
| Tomás et al. (2023)| GANs + BERT                        | 90.5     | 89.8      | 90.0   | 89.9     |
| **Proposed Model**     | **Double BERT**                    | **91.0** | **90.5**  | **90.5**| **91.0** |

## 5 Conclusion
**Key Performance Metrics Summary**:

| Metric               | Value  |
|----------------------|--------|
| Validation Accuracy  | 91.0%  |
| Weighted F1-Score    | 0.91   |
| Training Loss (Final)| 0.0003 |
| Validation Loss      | 0.2912 |
| Adversarial Success  | 76.9%  |

- 91% accuracy in sarcasm detection
- Superior handling of contextual nuances
- Robustness across demographic/cultural contexts
- Limitations in exaggerated expressions (future work)


 **Journal Submission**:
  
[![DOI](https://zenodo.org/badge/DOI/10.2139/ssrn.5063579)](https://dx.doi.org/10.2139/ssrn.5063579)
