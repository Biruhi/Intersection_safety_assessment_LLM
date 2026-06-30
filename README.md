# Intersection Safety Assessment Reporting using a Fine-Tuned Lightweight Large Language Model (LLM)

## Overview

This project develops and evaluates a lightweight Large Language Model (LLM) for automated intersection safety assessment reporting. The framework generates transportation-engineering safety reports from structured intersection characteristics and operational observations.

The study creates a synthetic instruction-following dataset representing diverse intersection conditions and uses parameter-efficient fine-tuning techniques to train a lightweight model capable of producing expert-style safety assessment reports.

The workflow includes:

* Synthetic transportation safety dataset generation
* Data preparation for instruction tuning
* LoRA-based fine-tuning using the Unsloth framework
* Quantitative and qualitative evaluation
* Comparison of base and fine-tuned model performance

---

## Project Objectives

The primary objectives of this project are to:

1. Generate a realistic transportation safety assessment dataset.
2. Create instruction-input-output examples suitable for LLM fine-tuning.
3. Fine-tune a lightweight language model using LoRA.
4. Produce professional intersection safety reports automatically.
5. Compare base-model and fine-tuned-model performance using engineering-focused evaluation criteria.

---

## Methodology

### 1. Synthetic Dataset Generation

A transportation-oriented synthetic dataset was generated programmatically using realistic combinations of roadway and traffic characteristics.

Variables include:

* Intersection type
* Area type
* Traffic volume
* Speed limit
* Left-turn lane availability
* Right-turn slip lanes
* Pedestrian facilities
* Bicycle facilities
* Lighting conditions
* Visibility conditions
* Roadside conditions
* Pavement surface conditions
* Traffic signage quality
* Signal operation status
* Observed traffic conflicts
* Crash history

Each generated record contains:

* **Instruction**
* **Structured Input**
* **Expert-style Safety Assessment Report**
* **Risk Score**
* **Risk Level**

---

### 2. Risk-Based Safety Assessment

The framework employs transportation-engineering logic to estimate safety risk.

Risk levels are determined from combinations of:

* High traffic exposure
* Poor visibility
* Inadequate pedestrian facilities
* Deficient signage
* Crash history
* Operational deficiencies
* Roadside hazards

The generated reports include:

* Overall safety assessment
* Key safety concerns
* Operational observations
* Recommended countermeasures
* Risk classification

---

### 3. Dataset Preparation

Generated samples are exported in multiple formats:

* CSV
* JSON
* Alpaca-style JSONL

Dataset split:

| Dataset    | Percentage |
| ---------- | ---------- |
| Training   | 70%        |
| Validation | 15%        |
| Testing    | 15%        |

Total generated samples:

**300 intersection safety assessment cases**

---

### 4. Fine-Tuning Framework

The project is designed for lightweight instruction tuning using:

* Hugging Face Transformers
* PEFT (Parameter-Efficient Fine-Tuning)
* LoRA (Low-Rank Adaptation)
* TRL
* Unsloth

Benefits include:

* Reduced computational requirements
* Faster training
* Lower memory consumption
* Efficient deployment

---

### 5. Model Evaluation

Performance is evaluated using a rubric-based framework comparing:

* Base model
* Fine-tuned model

Evaluation criteria:

1. Relevance
2. Completeness
3. Clarity
4. Overall Quality

Scores are measured on a 1–5 scale.

---

## Results Summary

The generated evaluation results demonstrate substantial improvement after fine-tuning.

### Evaluation Metrics

The following metrics were used:

* Relevance (1–5)
* Completeness (1–5)
* Clarity (1–5)
* Overall Quality (1–5)

The fine-tuned model consistently achieved higher scores than the base model across all evaluation dimensions.

### Qualitative Findings

Compared with the base model, the fine-tuned model:

* Produces more transportation-specific language.
* Identifies critical safety deficiencies more accurately.
* Provides clearer engineering recommendations.
* Generates reports with improved structure and readability.
* Demonstrates stronger alignment with professional intersection safety assessment practices.

Example outputs indicate that the fine-tuned model produces detailed descriptions of:

* Traffic operational issues
* Safety risks
* Pedestrian deficiencies
* Crash-related concerns
* Recommended engineering interventions

---

## Project Structure

```text
project_outputs/
│
├── data/
│   ├── dataset.csv
│   ├── dataset.json
│   └── dataset_alpaca.jsonl
│
├── models/
│   └── fine_tuned_model/
│
├── results/
│   ├── base_vs_finetuned_evaluation.csv
│   ├── qualitative_examples.csv
│   └── methodology_summary.txt
│
└── notebooks/
    └── Intersection_safety_assessment_LLM.ipynb
```

---

## Software Requirements

Python Packages:

```bash
pandas
numpy
scikit-learn
matplotlib
tqdm
transformers
datasets
accelerate
peft
trl
sentencepiece
bitsandbytes
unsloth
```

Install dependencies:

```bash
pip install pandas numpy scikit-learn matplotlib tqdm
pip install transformers datasets accelerate peft trl sentencepiece bitsandbytes
pip install unsloth
```

---

## Applications

Potential applications include:

* Road safety audits
* Intersection safety assessment
* Transportation engineering education
* Safety reporting automation
* Traffic engineering decision support
* Research in transportation-focused LLMs
* Explainable transportation AI systems

---

## Future Work

Future extensions may include:

* Integration with real crash databases.
* Incorporation of traffic simulation outputs.
* Use of aerial imagery and GIS information.
* Explainable AI for report justification.
* Multi-modal transportation safety assessment.
* Deployment as a web-based safety assessment tool.

---

## Author

**Biruhi Tesfaye Abeje**

PhD Researcher

Transportation Engineering, Traffic Safety, Explainable Artificial Intelligence, and Intelligent Transportation Systems Research

---

## Citation

If you use this project in academic research, please cite:

> Abeje, B.T. Intersection Safety Assessment Reporting Using a Fine-Tuned Lightweight Large Language Model (LLM), 2026.
