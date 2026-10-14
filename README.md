# Detecting Hallucinations in Large Language Model Responses

Machine Learning project for **IT461 - Practical Machine Learning** at King Saud University.

## Project Overview

Large Language Models (LLMs) can generate fluent and convincing responses, but some responses may contain incorrect, unsupported, or contradictory information. This problem is known as **hallucination**.

This project addresses hallucination detection as a **supervised binary classification** task. The model receives:

- Knowledge / reference context
- Question
- Candidate answer

and predicts whether the answer is:

- **0 - Faithful:** Supported by the provided knowledge
- **1 - Hallucinated:** Unsupported or inconsistent with the provided knowledge

## Dataset

This project uses the **HaluEval QA subset**, which contains 10,000 original question-answering records derived from HotpotQA.

Each original record contains:

- `knowledge`
- `question`
- `right_answer`
- `hallucinated_answer`

Each record is restructured into two labeled instances:

- `right_answer` → Label 0 (Faithful)
- `hallucinated_answer` → Label 1 (Hallucinated)

After restructuring, the dataset contains:

- **20,000 total instances**
- **10,000 Faithful responses**
- **10,000 Hallucinated responses**
- **50/50 class balance**

## Data Split

The original records are split before restructuring to reduce train-test leakage.

- Training: 80%
- Testing: 20%

After restructuring:

- **16,000 training instances**
- **4,000 testing instances**

The training and testing sets are also checked to ensure there is no question overlap.

## Repository Structure

```text
Hallucination-Detection/
│
├── README.md
│
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   ├── 01_data_preprocessing.ipynb
│   ├── 02_model_training.ipynb
│   └── 03_evaluation.ipynb
│
├── data/
│   └── README.md
│
├── results/
│   ├── figures/
│   └── tables/
│
├── report/
│
└── presentation/

## Evaluation Metrics

The machine learning models will be evaluated using:

- Accuracy
- Precision
- Recall
- F1-score

## Team Members

- **Aisha Fahad Alonizy** - 445200424
- **Remas Eid Almutairi** - 445200445
- **Dalal Ghumlas AlGhumlas** - 445200220

## Supervisor

**Dr. Afshan Jafari**

## Course

**IT461 - Practical Machine Learning**  
College of Computer and Information Sciences  
King Saud University
