# Sexism Detection with Large Language Models (LLMs)

This repository contains the solution for **Assignment 2** of the NLP course. The project addresses the **EDOS Task B** (Explainable Detection of Online Sexism) using open-source Large Language Models (LLMs) through prompting techniques.

**Credits:** Federico Ruggeri, Eleonora Mancini, Paolo Torroni

## 📋 Project Overview

The goal of this project is to perform **multi-class classification** on textual data to detect and categorize sexism. Unlike traditional fine-tuning approaches, this assignment explores the capabilities of pre-trained LLMs using **Zero-Shot** and **Few-Shot** prompting strategies.

### Task:
Given an input sentence, the model must classify it into one of the following 5 categories:
1.  **Not Sexist**
2.  **Threats** (Intent or desire to harm)
3.  **Derogation** (Derogatory description)
4.  **Animosity** (Slurs or insults)
5.  **Prejudiced Discussion** (Support for mistreatment/stereotypes)

##  Methodology

The project is structured into several tasks:

1.  **Model Setup**: Loading models from the Hugging Face Hub using 8-bit quantization (`bitsandbytes`) to fit within GPU memory constraints.
2.  **Prompt Engineering**: Designing structured system and user prompts to instruct the LLM on the definitions of the sexist categories.
3.  **Inference**:
    * **Zero-Shot**: Asking the model to classify text without seeing examples.
    * **Few-Shot**: Providing balanced demonstration examples (2 per class) in the context window to improve performance.
4.  **Evaluation**: Computing metrics (Accuracy, Macro F1-Score) and generating confusion matrices.

### Models Evaluated
The following open-source models were implemented and tested in this notebook:
* **Microsoft Phi-3-mini-4k-instruct**
* **Mistral-7B-Instruct-v0.3**

##  Dataset

The project uses a subset of the EDOS dataset provided by the course instructors:
* `a2_test.csv`: Test set (300 balanced samples).
* `demonstrations.csv`: Pool of examples used for few-shot prompting.

## Observations
-Mistral-7B benefited significantly from few-shot prompting, improving Accuracy by ~10%.

-Phi-3-mini showed robust zero-shot performance but did not gain significantly from few-shot examples in this specific setup.

## Project Structure
The notebook nlp2.ipynb is organized into the following tasks:
* Task 1: Model Setup - Downloads and loads quantized models (Phi-3 & Mistral-7B).

* Task 2: Prompt Setup - Defines templates for instructing the LLMs.

* Task 3: Zero-Shot Inference - Runs the models on test data without examples.

* Task 4: Metrics - Parses responses and computes Accuracy and F1-Score.

* Task 5: Few-Shot Inference - Builds prompts with dynamic examples and re-evaluates models.

* Task 6: Error Analysis - Generates confusion matrices and summarizes model behaviors.

* Task 7: Report - Guidelines for summarizing the experiment.

## License
This project is created for academic purposes. The dataset and task definition are based on the EDOS Challenge.








