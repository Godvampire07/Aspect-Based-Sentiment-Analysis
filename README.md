# Multilingual Aspect-Based Sentiment Analysis (ABSA) with Audio-Text Integration

This repository contains the implementation of a robust ABSA framework designed for low-resource Indian languages, specifically Hindi, Marathi, and Telugu. The system integrates both textual and speech inputs, leveraging state-of-the-art models for transcription, language detection, and translation-based data augmentation.

## 🚀 Project Overview
Traditional sentiment analysis often misses the nuances of specific attributes. This project implements a two-stage machine learning pipeline using TF-IDF feature extraction and Support Vector Machine (SVM) classifiers to identify both the **aspect** (e.g., Camera, Design) and the **sentiment** associated with it.

### Key Features
* **Multimodal Processing**: Transcribes audio inputs using OpenAI's **Whisper ASR**.
* **Language Detection**: Automatically identifies the input language via **FastText**.
* **Cross-Lingual Augmentation**: Uses **IndicTrans v2** to generate Marathi and Telugu datasets from Hindi corpora, addressing data scarcity in low-resource languages.
* **Robust Classification**: Combines word-level and character-level TF-IDF features to handle noisy text, morphological richness, and spelling variations.

---

## 🛠️ Tech Stack
* **ASR Model**: OpenAI Whisper
* **Translation**: IndicTrans v2 (Hugging Face)
* **Language Detection**: FastText
* **Classifiers**: Scikit-learn (SVM)
* **Features**: TF-IDF Vectorization (Word & Character n-grams)

---

## 📊 Pipeline Architecture
The system follows a structured pipeline to process inputs efficiently:

1. **Transcription**: Audio files are converted to text using Whisper.
2. **Preprocessing**: Text cleaning, tokenization, and noise removal.
3. **Detection**: FastText identifies the source language.
4. **Translation**: IndicTrans v2 ensures consistency for low-resource language processing.
5. **Feature Engineering**: Extraction of Word and Character n-grams to capture semantic and structural info.
6. **Inference**: Dual SVM classifiers predict the **Aspect** and then the **Sentiment** polarity.

---

## 📈 Experimental Results
The system was evaluated on a curated mobile review dataset across Hindi, Marathi, and Telugu.

### Classification Performance (Macro Averages)
| Task | Precision | Recall | F1-Score |
| :--- | :---: | :---: | :---: |
| **Aspect Detection** | 0.75 | 0.72 | 0.73 |
| **Sentiment Analysis** | 0.79 | 0.77 | 0.78 |

*Note: The model demonstrates peak performance on the **Specification** category due to explicit keyword triggers.*

---

## 📂 Dataset Statistics
| Language | Samples | Source | Type |
| :--- | :---: | :--- | :--- |
| Hindi | 1800 | Academic Repository | Original |
| Marathi | 1800 | IndicTrans v2 | Translated |
| Telugu | 1800 | IndicTrans v2 | Translated |

---

## ⚠️ Limitations
* **Semantic Noise**: Automated translation can introduce minor semantic inconsistencies.
* **Code-Mixing**: The current pipeline is not optimized for code-mixed text (e.g., Hinglish).
* **Context**: Classical ML models (SVM) may not capture deep context as effectively as Transformer-based architectures in highly complex sentences.

## 👥 Contributors
* **Mihir Hajare** - SVNIT, Surat
* **Meraj Alam** - SVNIT, Surat
* **Anshul Reddy Kotha** - SVNIT, Surat
