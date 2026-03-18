# Multilingual Aspect-Based Sentiment Analysis (ABSA) with Audio-Text Integration

[cite_start]This repository contains the implementation of a comprehensive ABSA framework designed for low-resource Indian languages, specifically Hindi, Marathi, and Telugu[cite: 4, 7]. [cite_start]The system integrates both textual and speech inputs, leveraging state-of-the-art models for transcription and translation[cite: 5, 7].

## 🚀 Project Overview
Traditional sentiment analysis often misses the nuances of specific attributes. [cite_start]This project implements a two-stage machine learning pipeline using TF-IDF feature extraction and Support Vector Machine (SVM) classifiers to identify both the **aspect** (e.g., Camera, Design) and the **sentiment** associated with it[cite: 6, 18, 19].

### Key Features
* [cite_start]**Multimodal Processing**: Transcribes audio inputs using OpenAI's **Whisper ASR**[cite: 5, 31].
* [cite_start]**Language Detection**: Automatically identifies the input language via **FastText**[cite: 5, 32].
* [cite_start]**Cross-Lingual Augmentation**: Uses **IndicTrans v2** to generate Marathi and Telugu datasets from Hindi corpora, addressing the "low-resource" data scarcity[cite: 7, 41].
* [cite_start]**Robust Classification**: Combines word-level and character-level TF-IDF features to handle noisy text and spelling variations[cite: 71, 72].

---

## 🛠️ Tech Stack
* [cite_start]**ASR Model**: OpenAI Whisper [cite: 5]
* [cite_start]**Translation**: IndicTrans v2 (Hugging Face) [cite: 7, 41]
* [cite_start]**Language Detection**: FastText [cite: 5, 16]
* [cite_start]**Classifiers**: Scikit-learn (SVM) [cite: 6, 52]
* [cite_start]**Features**: TF-IDF Vectorization [cite: 6, 34]

---

## 📊 Pipeline Architecture
[cite_start]The system follows a structured pipeline to process inputs efficiently[cite: 12]:

1. [cite_start]**Transcription**: Audio files are converted to text using Whisper[cite: 31].
2. [cite_start]**Preprocessing**: Normalization and noise removal[cite: 32].
3. [cite_start]**Detection**: FastText identifies the source language[cite: 16, 32].
4. [cite_start]**Translation**: IndicTrans v2 ensures consistency for low-resource languages[cite: 33, 41].
5. [cite_start]**Feature Engineering**: Extraction of Word and Character n-grams[cite: 71, 72].
6. [cite_start]**Inference**: Dual SVM classifiers predict the Aspect and Sentiment[cite: 35, 36].

---

## 📈 Experimental Results
[cite_start]The system was evaluated on a curated mobile review dataset[cite: 38]. 

### Classification Performance (Macro Averages)
| Task | Precision | Recall | F1-Score |
| :--- | :---: | :---: | :---: |
| **Aspect Detection** | 0.75 | 0.72 | 0.73 |
| **Sentiment Analysis** | 0.79 | 0.77 | 0.78 |

[cite_start]*Note: The model performs best on the **Specification** category due to explicit keyword triggers [cite: 74][cite_start].* [cite: 59, 81]

---

## 📂 Dataset Statistics
| Language | Samples | Source | Type |
| :--- | :---: | :--- | :--- |
| Hindi | 1800 | Academic Repository | [cite_start]Original [cite: 45] |
| Marathi | 1800 | IndicTrans v2 | [cite_start]Translated [cite: 45] |
| Telugu | 1800 | IndicTrans v2 | [cite_start]Translated [cite: 45] |

---

## ⚠️ Limitations
* [cite_start]**Semantic Noise**: Automated translation can sometimes lead to semantic inconsistencies[cite: 100].
* [cite_start]**Code-Mixing**: The current pipeline does not effectively handle code-mixed text (e.g., Hinglish)[cite: 103].
* [cite_start]**Context**: Classical ML models (SVM) may not capture deep context as effectively as Transformer-based architectures[cite: 102].

## 👥 Contributors
* [cite_start]**Mihir Hajare** - SVNIT, Surat [cite: 2, 3]
* [cite_start]**Meraj Alam** - SVNIT, Surat [cite: 2, 3]
* [cite_start]**Anshul Reddy Kotha** - SVNIT, Surat [cite: 2, 3]
