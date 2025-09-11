---
title: Tasks & Data
permalink: tasks
---

## Task Overview

HIPE-2026 is a shared task on **person–place relation extraction** from **multilingual historical texts**. The goal is to assess whether a relation holds between a person and a place mentioned in a document — and to classify that relation with respect to its **temporal scope**.

Participants are asked to build systems that, given a historical document and a set of
entities, will classify all possible `(person, place)` pairs into one of **three
evidence-based labels** for each of two relation types. The task is designed to be
tackled by generative AI systems/LLMs as well as more traditional classification approaches.

---

## Relation Types

Two relation types are to be evaluated independently:

- **`at`** – Did the person ever reside in or visit the place prior to the document's publication?
- **`isAt`** – Is the person located at the place in the **immediate temporal context** of the document?

This design supports different downstream goals — from **spatial biographies** to **historical event contextualization**.

---

## Input and Output Format

Each document will be provided with:

- Full article text (OCR with possible errors)
- A list of **person entities** (de-duplicated by surface form or linked ID)
- A list of **place entities**
- Metadata (e.g., document language, publication date)

Participants must return a classification for each possible `(person, place, relation)` triple using:

- `true`: strong textual evidence supports the relation
- `plausible`: plausible inference can be made from context
- `false`: no evidence or explicitly contradicted

---

## Evaluation Profiles

To reflect different research and application priorities, HIPE-2026 will offer two profiles:

1. **Accuracy Profile**:  
   Ranking based on standard classification metrics (Precision, Recall, F1) per relation type.

2. **Efficiency Profile**:  
   Ranking based on a composite metric balancing accuracy with:
   - Model size
   - Inference time
   - Hardware usage
   - Availability as open-source or low-cost system

---

## Datasets

We will release two datasets for the task:

### 🧪 Development & Test Set A

- Derived from the HIPE-2022 dataset
- Languages: **French, German, English, Luxembourgish**
- Contains manually validated relation labels for pre-annotated person/place entities
- Includes metadata for temporal reasoning

### 🎭 Surprise Test Set B

- Literary corpus from the **16th–18th century**
- French-language texts annotated for NER and now enriched with relation labels
- Designed to evaluate **domain generalization**

All data will be released under **CC-BY 4.0** and distributed via **Zenodo**, with mirrored repositories and notebooks on **GitHub** and **Hugging Face**.

---

## Baselines and Starter Code

We will provide:

- Input/output templates
- Scoring script
- A baseline system
- Pre-built notebooks for data exploration

Details and links will be added here once released.

---

## Questions?

Please post to the [mailing list](https://groups.google.com/g/hipe-2026).
