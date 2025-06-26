# SarcasmDoubleBert_mixed-and-twitter-code
# Advancing Sarcasm Detection with a Double BERT Architecture: Insights and Performance Analysis

**Author**: Ramakrishna Bodige  
**Email**: ramakrishnamail4u@gmail.com  
**Institution**: Department of Computer Science, SR University, Warangal, Telangana, India
# Project Statement
Sarcasm detection is a critical challenge in natural language processing (NLP) due to its dependence on contextual, emotional, and cultural nuances. Detecting sarcasm accurately is essential for improving the understanding of human communication, especially in online interactions. This paper aims to propose an effective model for sarcasm detection with the Double BERT approach, addressing the challenges of capturing contextual, demographic diversity, cultural variance and emotional patterns from text. Existing sarcasm detection models often struggle with handling diverse linguistic features and contextual variations, leading to suboptimal performance across different datasets and domains.We developed a robust sarcasm detection model using Double BERT, trained on a mixed dataset consisting of 149,480 samples
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

---

## Text Embedding with BERT

**Process**:  
```mermaid
graph LR
A[Raw Text] --> B[WordPiece Tokenizer]
B --> C[Subword Units]
