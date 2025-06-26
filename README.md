# SarcasmDoubleBert_mixed-and-twitter-code
# Advancing Sarcasm Detection with a Double BERT Architecture: Insights and Performance Analysis

**Author**: Ramakrishna Bodige  
**Email**: ramakrishnamail4u@gmail.com  
**Institution**: Department of Computer Science, SR University, Warangal, Telangana, India
# Project Statement
Sarcasm detection is a critical challenge in natural language processing (NLP) due to its dependence on contextual, emotional, and cultural nuances. Detecting sarcasm accurately is essential for improving the understanding of human communication, especially in online interactions. This paper aims to propose an effective model for sarcasm detection with the Double BERT approach, addressing the challenges of capturing contextual, demographic diversity, cultural variance and emotional patterns from text. Existing sarcasm detection models often struggle with handling diverse linguistic features and contextual variations, leading to suboptimal performance across different datasets and domains.We developed a robust sarcasm detection model using Double BERT, trained on a mixed dataset consisting of 149,480 samples.
**Keywords**: Sarcasm detection, contextual understanding, NLP, BERT, adversarial study
### Contributions
1. Implemented Double BERT combining contextual embedding and classification
2. Trained/tested on mixed datasets across demographic/cultural contexts
3. Evaluated robustness via adversarial examples
4. Achieved **91.4% accuracy** and **91.2 weighted F1-score**
# Method Overview

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

### 3.1 Text Embedding with BERT
**Process**:
1. WordPiece tokenization
2. Triple embedding:
   - **Word Embeddings**: 30522×768 dimensions
   - **Position Embeddings**: 512×768 dimensions
   - **Token Embeddings**: 2×768 dimensions

### 3.2 Classification BERT
Processes contextual embeddings using:
- Self-attention mechanism
- Feed-forward network
- Layer normalization

## 4 Dataset

**Sources**:
- SemEval-2020 (structured annotations)
- Reddit (conversational sarcasm)
- The Onion (cultural satire)
- Twitter (emotional/spontaneous sarcasm)

**Class Distribution**:
- Sarcastic: 47.2%
- Non-sarcastic: 52.8%

## 5 Results
### 5.1 Performance Metrics
| Class         | Precision | Recall | F1-Score | Support |
|---------------|-----------|--------|----------|---------|
| Sarcasm       | 0.89      | 0.90   | 0.90     | 2103    |
| Non-Sarcasm   | 0.92      | 0.91   | 0.92     | 2607    |
| **Weighted Avg** | 0.91    | 0.91   | **0.91** | 4710    |



## 6 Conclusion
Our Double BERT model demonstrates:
- 91% accuracy in sarcasm detection
- Superior handling of contextual nuances
- Robustness across demographic/cultural contexts
- Limitations in exaggerated expressions (future work)

## References
[//]: # (Include formatted references here)
Chauhan et al. (2020), Babanejad et al. (2020), Liu et al. (2022), ... Helal et al. (2024)
```


 **Journal Submission**:
   
  [![DOI]([http://dx.doi.org/10.2139/ssrn.5063579])]

