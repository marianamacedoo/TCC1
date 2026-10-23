<p align="right">🇺🇸 English · [🇧🇷 Português](README.pt.md)</p>

# Automatic Classification of Programming Error Messages

**Using Machine Learning to Support Educational Recommendation Systems**

Monograph I · Computer Science · Federal University of Ouro Preto (UFOP) · 2026
Advisor: Prof. Reinaldo Silva Fortes

> This repository brings together the **first stage of my Undergraduate Thesis (Thesis 1)**. Here you will find the initial experiments and preliminary results. The research continues in **Thesis 2**, which expands upon the work and concludes the degree program.

## About

Compiler error messages are often difficult for beginner programmers to understand, and it is not always clear which course topic the error is related to.

This work develops a model that classifies C program error messages into **seven Introduction to Programming topics**. The goal is for this classification to serve as the foundation for an **educational recommendation system**, capable of suggesting study materials based on each student's errors.

| Class | Topic |
|---|---|
| C1 | Data types, variables, and constants |
| C2 | Expressions and operators |
| C3 | Conditional and loop structures |
| C4 | Modularization (functions and procedures) |
| C5 | Homogeneous and heterogeneous data structures |
| C6 | Strings |
| C7 | Pointers and dynamic memory allocation |

## Methodology

- **Data:** real student compilation errors adapted from the *Targeted Example Generation for Compilation Errors* dataset (He et al., 2020). A sample of about 800 messages was manually labeled.
- **Preprocessing:** extraction of the first error reported by the Clang compiler and text cleaning.
- **Model:** Logistic Regression with TF-IDF representation.

Three input formats were compared for the model:

| Approach | Accuracy |
|---|---|
| Error message only | **94%** |
| Error message + tokenized source code | 51% |
| Error message + original source code | 66% |

The error message alone, when properly processed, was the most informative input. Adding source code introduced noise to a linear model. Classes with few examples (C5, C6, and C7) remain the main challenge.

## Next Steps: Thesis 2

The results from Thesis 1 show that the idea is viable, but there is still plenty of room for progress. In Thesis 2, the plan is to:

- Expand the dataset and address class imbalance.
- Test more robust models, such as SVM, Random Forest, and transformers.
- Integrate the classification into an educational recommendation system.

## Notebooks

| File | Content |
|---|---|
| `ErrosEcodigos.ipynb` | Extraction, message cleaning, and sample preparation for labeling |
| `Classificacao.ipynb` | Approach 1: error message only |
| `Classificacao_ErrosCodigoLimpo.ipynb` | Approach 2: error message + tokenized code |
| `Classificacao_ErrosCodigoOriginal.ipynb` | Approach 3: error message + original code |

**Technologies:** Python · Pandas · scikit-learn · Matplotlib · Seaborn · Google Colab

## Author

**Mariana Macedo Santos** · [Portfolio](https://marianamacedoo.github.io) · [LinkedIn](https://www.linkedin.com/in/mariana-macedo-7b9ab3227)
