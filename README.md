# 🧬 CAFA-6 Baseline: Protein Function Prediction using k-mers + TF-IDF + Logistic Regression  
### Predicción de la función proteica mediante k-mers + TF-IDF + Regresión Logística

[![Competition](https://img.shields.io/badge/Kaggle-CAFA6_Protein_Function_Prediction-blue)](https://www.kaggle.com/competitions/cafa-6-protein-function-prediction)
[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Bioinformatics](https://img.shields.io/badge/Field-Bioinformatics-lightgrey)]()
[![Machine Learning](https://img.shields.io/badge/Approach-Machine_Learning-orange)]()

---

## 🧑‍💻 Author / Autor
**Francisco José de la Corte López**  
📍 *Huelva, Spain*  
GitHub: [@francorte](https://github.com/francorte)  
Kaggle: [Francorte](https://www.kaggle.com/francorte)

---

## 🎯 Objective / Objetivo

### 🇬🇧 English
This notebook develops a **baseline model** for the **CAFA-6 Protein Function Prediction** challenge.  
The goal is to predict **Gene Ontology (GO)** terms — *Molecular Function (MF)*, *Biological Process (BP)*, and *Cellular Component (CC)* — for each protein based solely on its amino acid sequence.

It implements a **bag-of-k-mers representation** of sequences, applies **TF-IDF vectorization**, and trains a **multi-label Logistic Regression** classifier per ontology.  
The notebook also includes **hierarchical GO propagation** and **F-max threshold optimization**.

### 🇪🇸 Español
Este cuaderno desarrolla un **modelo base (baseline)** para la competición **CAFA-6 Protein Function Prediction**.  
El objetivo es predecir los términos de la **Gene Ontology (GO)** — *Función Molecular (MF)*, *Proceso Biológico (BP)* y *Componente Celular (CC)* — de cada proteína a partir de su secuencia de aminoácidos.

Implementa una **representación de secuencias mediante k-mers**, vectorización **TF-IDF** y un clasificador **multietiqueta de Regresión Logística** por subontología.  
También incluye la **propagación jerárquica real (DAG GO)** y el ajuste de umbral **F-max**.

---

## ⚙️ Pipeline Overview / Flujo del modelo

```mermaid
flowchart TD
    A[Input FASTA & Annotations] --> B[Parse + Clean + Merge]
    B --> C[k-mer Encoding (k=3..4)]
    C --> D[TF-IDF Vectorization]
    D --> E[One-vs-Rest Logistic Regression per Ontology]
    E --> F[Threshold Optimization (F-max)]
    F --> G[Hierarchical Propagation (GO DAG)]
    G --> H[Submission TSV]
