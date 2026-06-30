# 🚦 Fine-Tuning a Lightweight Large Language Model for Intersection Safety Assessment Reporting

## Overview

This repository presents a complete framework for developing and evaluating a lightweight Large Language Model (LLM) capable of generating professional transportation safety assessment reports from structured intersection characteristics.

The project addresses the challenge of automating transportation engineering reporting by creating a synthetic instruction-tuning dataset and adapting a lightweight LLM through parameter-efficient fine-tuning using Low-Rank Adaptation (LoRA) within the Unsloth framework.

The developed system learns to interpret roadway geometric, operational, environmental, and safety-related characteristics and automatically generates engineering-style safety assessments, identifies critical deficiencies, evaluates risk levels, and recommends countermeasures.

The workflow consists of:

1. Synthetic transportation safety dataset generation.
2. Risk-based safety assessment logic.
3. Instruction dataset preparation.
4. LoRA-based model fine-tuning.
5. Quantitative and qualitative evaluation.
6. Automated generation of transportation safety reports.

---

## Project Highlights

* Generated **300 synthetic intersection safety assessment cases**.
* Created instruction-following datasets in **CSV**, **JSON**, and **Alpaca JSONL** formats.
* Applied **LoRA fine-tuning** using the Unsloth framework.
* Evaluated performance using **46 unseen test cases**.
* Achieved substantial improvements over the base model.
* Demonstrated the feasibility of lightweight transportation-domain LLMs for engineering report generation.

---

## Transportation Features Included

Each intersection scenario contains transportation-specific attributes including:

### Geometric Characteristics

* Intersection type
* Left-turn lane availability
* Right-turn slip lane availability
* Bicycle facilities
* Pedestrian facilities

### Traffic Characteristics

* Traffic volume
* Posted speed limit
* Heavy vehicle share

### Environmental Characteristics

* Lighting conditions
* Visibility conditions
* Surface condition

### Safety Characteristics

* Roadside condition
* Traffic signage and pavement markings
* Signal operation status
* Observed traffic conflicts
* Crash history

---

## Dataset Development

A synthetic instruction-based transportation safety dataset was generated programmatically.

Each sample consists of:

### Instruction

Generate a professional intersection safety assessment report.

### Input

Structured transportation and roadway characteristics.

### Output

Expert-style safety assessment report containing:

* Safety risk summary
* Operational concerns
* Key deficiencies
* Recommended countermeasures
* Risk classification

### Dataset Size

| Dataset        | Samples |
| -------------- | ------: |
| Total Dataset  |     300 |
| Training Set   |     210 |
| Validation Set |      45 |
| Testing Set    |   45–46 |

---

## Risk Assessment Framework

The synthetic report generator incorporates transportation engineering reasoning through a rule-based risk scoring framework.

Risk scores are influenced by:

* High traffic demand
* Elevated operating speeds
* Missing turn lanes
* Inadequate pedestrian facilities
* Bicycle facility discontinuity
* Poor lighting conditions
* Restricted visibility
* Inadequate signage
* Roadside hazards
* Recorded crash history

Generated reports include corresponding engineering recommendations for each identified safety concern.

---

## Model Fine-Tuning

The lightweight LLM was fine-tuned using:

* Hugging Face Transformers
* PEFT
* TRL
* LoRA
* Unsloth

The objective was to teach the model transportation-specific reasoning rather than generic text generation.

---

## Evaluation Methodology

Performance was evaluated using a rubric-based assessment framework.

Evaluation dimensions:

1. Relevance
2. Completeness
3. Clarity
4. Overall Quality

The base model and fine-tuned model were compared on 46 unseen test cases.

---

## Quantitative Results

| Metric          | Base Model | Fine-Tuned Model |
| --------------- | ---------: | ---------------: |
| Relevance       |       2.17 |             4.90 |
| Completeness    |       4.31 |             5.00 |
| Clarity         |       4.52 |             5.00 |
| Overall Quality |       3.66 |             4.97 |

### Improvement

| Metric          | Improvement |
| --------------- | ----------: |
| Relevance       |     +125.8% |
| Completeness    |      +16.0% |
| Clarity         |      +10.6% |
| Overall Quality |      +35.8% |

The largest improvement was observed in relevance, indicating that the fine-tuned model learned to focus on transportation safety concerns and generate reports aligned with roadway safety engineering practices.

---

## Qualitative Findings

Compared with the base model, the fine-tuned model:

* Better identifies transportation safety deficiencies.
* Produces more engineering-oriented reasoning.
* Links roadway conditions to crash risk.
* Generates clearer recommendations.
* Creates professional report structures similar to transportation safety audit documentation.

Example issues correctly identified by the model include:

* Turning conflicts
* Rear-end crash potential
* Bicycle safety deficiencies
* Pedestrian exposure risks
* Inadequate lighting
* Roadside hazards
* Insufficient traffic control devices

---

## Repository Contents

```text
.
├── Intersection_safety_assessment_LLM.ipynb
├── datasets/
│   ├── intersection_safety_dataset.csv
│   ├── intersection_safety_dataset.json
│   └── intersection_safety_dataset_alpaca.jsonl
│
├── results/
│   ├── base_vs_finetuned_evaluation.csv
│   ├── qualitative_examples.csv
│   └── methodology_summary.txt
│
├── models/
│   └── fine_tuned_model/
│
└── README.md
```

---

## Author

**Biruhi Tesfaye Abeje**

PhD Researcher

Transportation Engineering | Traffic Safety | Explainable Artificial Intelligence | Intelligent Transportation Systems

---


