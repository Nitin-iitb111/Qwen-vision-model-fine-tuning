# Qwen-vision-model-fine-tuning

This project demonstrates how to fine-tune a pre-trained vision-language model (specifically, `unsloth/Qwen2-VL-2B-Instruct-bnb-4bit`) for Optical Character Recognition (OCR) on Gujarati text. The goal is to improve the model's ability to accurately extract text from images containing the Gujarati script.

## Table of Contents

- [Project Overview](#project-overview)
- [Results](#results)
- [Installation](#installation)
- [Usage](#usage)
  - [1. Data Preparation](#1-data-preparation)
  - [2. Baseline OCR with Tesseract](#2-baseline-ocr-with-tesseract)
  - [3. Fine-tuning the Vision-Language Model](#3-fine-tuning-the-vision-language-model)
  - [4. Evaluation](#4-evaluation)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

This project tackles the challenge of OCR for the Gujarati language. While general-purpose OCR tools like Tesseract exist, they may not always provide the best accuracy for specific languages or document types. This project explores the use of a powerful vision-language model and fine-tunes it on a dataset of Gujarati text images to enhance its text extraction capabilities.

The key steps in this project are:
1.  **Environment Setup**: Installing all necessary libraries, including `transformers`, `unsloth`, `pytesseract`, and `jiwer`.
2.  **Data Preparation**: Loading and splitting the image dataset into training and testing sets.
3.  **Baseline OCR**: Using Tesseract to establish a baseline for OCR performance.
4.  **Model Loading and Configuration**: Loading a pre-trained vision-language model and configuring it for fine-tuning with LoRA (Low-Rank Adaptation).
5.  **Fine-tuning**: Training the model on the Gujarati text image dataset.
6.  **Evaluation**: Comparing the performance of the fine-tuned model against the baseline using Word Error Rate (WER) and Character Error Rate (CER).

## Results

The fine-tuning process resulted in a notable improvement in the model's performance, particularly in the Character Error Rate (CER).

| Model | Average WER | Average CER |
|---|---|---|
| Baseline (Untrained) | 1.000 | 0.989 |
| Fine-tuned (Trained) | 1.001 | 0.982 |

**Observations:**

*   **WER (Word Error Rate):** The fine-tuned model achieved a similar WER compared to the baseline model.
*   **CER (Character Error Rate):** The fine-tuned model shows a lower CER, signifying better performance in recognizing individual characters.

**Conclusion:**

Fine-tuning the vision-language model led to a reduction in CER, demonstrating the effectiveness of the training process in enhancing text extraction capabilities for the Gujarati language. The WER remained similar, which could be due to the nature of the errors or the evaluation metrics.

## Installation

To run this project, you need to install the required Python libraries. You can install them using pip:
